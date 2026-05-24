---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2026-05-23T22:48
---
---



Here is the complete, compiled master blueprint for your project. You can copy and paste this into your new chat as the single source of truth for the architecture, branding, security, and roadmap.

# The `plug` Blueprint: MCP Server Package Manager

### 1. Project Identity & Nomenclature

- **App/CLI Name**: `plug`
- **Domain**: `useplug.dev` or `plughq.dev`
- **NPM Package**: `@plug/cli` or `plug-cli`
- **Manifest File**: `plug.json` (Server-side configuration)
- **Unified Config File**: `plugconfig.json` (Local machine installed state)

### 2. Architecture & Tech Stack

We are prioritizing **shipping speed in Phase 1** by using the MERN/TypeScript stack you already know, delaying the rewrite in Go until Phase 3 when the daemon requires it.

- **Monorepo Strategy**: Turborepo + `pnpm` workspaces (`apps/cli`, `apps/web`, `apps/api`, `packages/shared`, `packages/db`).
- **Web App**: Next.js hosted on Vercel (Free tier).
- **Registry API**: Express.js hosted on Railway or Render + Redis (Upstash) for caching search queries.
- **Database**: Supabase PostgreSQL (Free tier).
- **Storage**: Cloudflare R2 (Phase 2), bypassing GitHub IP rate limits.
- **CLI**: TypeScript compiled to a standalone native binary using `bun build --compile`.

### 3. The `plug.json` Specification

The manifest enforces a strict **12-category controlled vocabulary** to keep the marketplace organized. A server must belong to 1 or 2 of these:

1. Code & Version Control
2. Databases
3. Cloud & Infrastructure
4. Web & Browser
5. Files & Storage
6. Communication
7. Productivity & Knowledge
8. AI & Memory
9. Security
10. Finance
11. Media & Creative
12. Other

- `runtimes` must be an array (to support multi-runtime environments).
- `env` variables marked `"secret": true` are never saved in plain text; they are prompted securely and saved to the native OS keychain via `keytar`.

### 4. Database Schema (Phase 1)

Three core tables to enable the "Data Moat":

1. **`packages`**: `id`, `name`, `repository_url`, `categories` (indexed), `tier`.
2. **`versions`**: `package_id`, `version` (strict semver), `manifest_json`, `tarball_url`, `tarball_sha256`, `yanked`.
3. **`install_events`**: Tracks anonymous CLI telemetry (`client_id_hash`, `os`, `runtime`) to rank search results.

### 5. The CLI Install Flow (12 Steps)

To avoid bandwidth waste and partial install corruption, `plug add [server]` executes in this exact sequence:

1. **Fetch Manifest**: From the Registry API.
2. **Runtime Detection**: Check local `node --version` or `python` before downloading anything.
3. **Download Tarball**: Fetch `.tar.gz` to a temporary `~/.cache/plug/tmp` directory.
4. **Verify Integrity**: Compare SHA-256 hash against the DB. Abort if mismatched.
5. **Extract (Extractor Engine)**: Unpack tarball into the temporary directory safely.
6. **Install Dependencies**: Run native package manager (e.g., `npm ci --ignore-scripts`).
7. **Atomic Move**: Rename the tmp folder to the final `env-paths` data directory (prevents broken state if `Ctrl+C` is pressed).
8. **Collect Secrets**: Prompt user and store in OS keychain.
9. **Inject Config**: Safely modify Anthropic/Cursor configs.
10. **Telemetry**: Send silent POST request to `install-events`.
11. **Local State Update**: Update `plugconfig.json`.
12. **Success**: Print clean summary.

### 6. Security Mitigations (The Extractor Engine)

Based on our vulnerability analysis, the CLI must enforce these strict rules to prevent malware during installation:

- **Path Traversal (S1)**: Parse tarball headers manually. If any path starts with `/` or contains `..`, abort install immediately.
- **Entry Point Injection (S2)**: Validate `entry` strings using regex. Never use `child_process.exec()`; use `spawn()` to prevent shell operator injection.
- **Symlink Attacks (S3)**: Drop all symlinks during tarball extraction to prevent SSH key theft.
- **NPM Postinstall Scripts (S4)**: Always run `npm ci --ignore-scripts`. If it fails, halt and ask the user for explicit permission to run scripts.
- **File Locking (C1)**: Wrap the install pipeline in `proper-lockfile` to prevent parallel installs from corrupting local state.
- **Config File Fragility (C6)**: Never use `JSON.parse()/stringify()` on Claude/Cursor configs. Use an AST parser (`jsonc-parser`) to inject variables without destroying user comments or unknown fields. Always backup `config.bak` first.

### 7. Phased Roadmap

- **Phase 1 (The Directory that Installs)**: Build TS/Bun CLI, Web search, and API. DB seeded manually with 50 hand-curated servers. No open publishing yet.
- **Phase 2 (Open Registry)**: Launch `plug publish`. Tarballs are hosted on Cloudflare R2. Users can publish via CLI. Introduce Community reporting.
- **Phase 3 (Quality, Trust & Go Rewrite)**: Rewrite the CLI/Daemon in **Go** for 5ms startup and high-concurrency 24/7 background proxying. Daemon intercepts AI-to-Server stdio messages to enforce permission profiles (blocking undeclared network/file access).
- **Phase 4 (Enterprise)**: Private registries, SSO, Analytics dashboards, and the Desktop App GUI.
  


Here is the second compiled document: **The Extended Playbook**. It captures the deeper mechanics we discussed—security edge cases, the business model, the launch strategy, and the advanced daemon architecture that were not in the first technical blueprint.

You can paste this right below the first blueprint in your new chat.

---

# The `plug` Extended Playbook: Strategy, Security, and Business

### 1. The Three-File Configuration Mental Model

To avoid architectural confusion, `plug` strictly separates configuration into three layers:

1. **`plug.json` (Server Manifest):** Lives in the server author's GitHub repo. Describes what the server IS (version, runtimes, permissions).
2. **`plugconfig.json` (Unified Config):** Lives at `~/.plug/plugconfig.json`. Managed entirely by your CLI/Daemon. It is the single source of truth for what is INSTALLED on the user's machine.
3. **`claude_desktop_config.json` (Client Configs):** Proprietary files for Anthropic/Cursor. In Phase 1, the CLI translates `plugconfig.json` into these formats. In Phase 3, the Daemon intercepts connections, hopefully pushing clients to adopt `plugconfig.json` natively.

### 2. Quality Control: The Three Tiers

To solve the "10,000 garbage servers" problem without gatekeeping, `plug` uses a progressive trust system:

- **Community (Phase 2):** Open to anyone. Passes basic automated format checks (valid JSON, reachable URL). Meaning to user: _"Exists, but untested"_.
- **Verified (Phase 3):** Passes automated sandbox testing (installs, starts, responds to tools) + static analysis + a human spot-check of the README. Meaning to user: _"We tested this, it works safely"_.
- **Official (Phase 4):** Reserved for canonical creators (e.g., GitHub publishing the GitHub server). Requires manual identity verification. Meaning to user: _"From the actual company"_.

### 3. Extended Vulnerabilities & Edge Cases

Beyond the immediate extraction hacks, you must build defenses for these critical roadblocks:

- **A1 - The Stdio Shim Problem (Hardest Tech Challenge):** To enforce permissions, the Daemon must trick AI clients into talking to _it_ instead of the server. It must aggregate all installed tools into one list, namespacing them (e.g., `github__create_issue`) to prevent collisions.
- **A3 - System Dependencies:** The CLI cannot natively `apt-get` system binaries like `ffmpeg`. For Phase 1, exclude any server from your curated 50 that requires system-level dependencies.
- **I3 - GitHub Rate Limits:** GitHub allows only 60 unauthenticated requests/hour per IP. If a whole office installs your tool, they will get blocked. You _must_ move to Cloudflare R2 tarball hosting before a massive launch.
- **P1 - Name Squatting:** Trolls will squat on `github`, `slack`, etc., on launch day. **Pre-register the top 50 obvious names yourself** before making your launch announcement.
- **P7 - The "Left-Pad" Rule:** Unpublishing is not allowed after 24 hours. You can only "yank" (flag as broken) a version, but the tarball remains permanently available to prevent breaking existing user setups.

### 4. The "Data Moat" & Competitive Defense

Existing directories (like `mcp.so` or `PulseMCP`) only track website page views, which is a useless vanity metric. Because `plug` operates via a CLI, every `plug add X` sends an anonymous telemetry ping (`client_id_hash`, `os`, `runtime`). This builds an irreproducible Data Moat:

- You know actual install velocity to rank trending servers.
- You know OS breakdown (e.g., "This server crashes on Windows").
- If the Linux Foundation launches a registry, they are starting from zero data. Developers will not abandon your CLI if it has the best search algorithm powered by 2 years of real install metrics.

### 5. Launch & Go-To-Market Strategy

The launch relies on demonstrating a frictionless Developer Experience (DX):

- **The Demo GIF:** Use a terminal recorder (like `vhs`) to create a 15-30 second, no-audio GIF showing `plug add github` → secure secrets prompt → Claude immediately using it.
- **Show HN:** Post "Show HN: `plug` – a package manager for MCP servers" on a weekday morning. Link directly to the demo GIF.
- **Twitter/X Thread:** Post a Before (manual JSON editing) vs. After (1-line `plug` command) comparison.
- **Author Outreach:** DM the authors of your 50 curated servers. Inform them they are featured and ask if you can PR a `plug.json` file into their repo.

### 6. Startup Path & Monetization

You will use the **Open Core Model** (like GitLab or HashiCorp). The CLI and public registry remain free forever. Do not raise venture capital early; build Phase 1-2 solo.

- **Phase 1-2 Infrastructure:** Fund via free tiers (Vercel, Railway, Supabase).
- **OSS Credits:** Apply for Cloudflare OSS and AWS Open Source credits once you have real GitHub stars.
- **Revenue 1 - Private Registries:** Sell access for companies to host internal, proprietary MCP servers safely behind your infrastructure.
- **Revenue 2 - Enterprise Features:** Charge for SSO integration, audit logs, SLAs, and Cloud-Hosted Daemons.
- **Legal:** When enterprise contracts begin, register a Private Limited Company in India to handle invoicing and compliance.

---

**Are you ready to wrap this up and take these two blueprints over to your fresh chat to start building Phase 1?**


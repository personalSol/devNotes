---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2026-05-17T17:33
---
---





# MCP Hub — Project Discovery Document

> A living document capturing all thinking, decisions, open questions, and architecture for the MCP Hub project. Last updated: May 2026 | Status: Pre-development / Exploration phase

---

## 1. What Is This Project?

MCP Hub aims to be the **npm of MCP servers** — a registry, discovery platform, CLI tool, and desktop agent that makes finding, installing, managing, and publishing MCP servers as easy as `npm install`.

Currently no such thing exists in a complete form. The project has the potential to become the de facto standard before the Linux Foundation ships its official registry.

---

## 2. Background — What Is MCP?

**Model Context Protocol (MCP)** is an open standard created by Anthropic (November 2024) and donated to the Linux Foundation (December 2025). It is now co-sponsored by OpenAI, Google, and Microsoft.

MCP is a standard communication language that lets AI models (like Claude, GPT-4, Gemini) talk to external tools and services. Before MCP, every AI needed custom integrations for every tool. MCP standardizes this into one protocol.

An **MCP server** is a small program that speaks the MCP language on behalf of a tool — your filesystem, GitHub, Slack, a database, etc. When an MCP server is running, an AI can use it to take real actions in the world.

**Why this matters for this project**: There are 10,000+ MCP servers publicly available as of early 2026, with 97 million monthly SDK downloads. Every developer using these needs to find, install, configure, and manage them. No good tooling exists for this. That is the gap.

---

## 3. The Problem Statement

### 3.1 Current State of MCP Discovery

Several directories exist today:

|Platform|Servers|What it actually is|
|---|---|---|
|mcp.so|~21,000|Community-submitted list, manual|
|PulseMCP|~15,000|Updated directory with visitor stats|
|LobeHub MCP|Hundreds|Tied to their own AI client|
|Conare|~1,500|Directory with setup notes|
|mcpmarket.com|~1,000|Browse by category|

**The critical insight**: These are all fancy lists. Developers submit MCP servers by opening a GitHub issue. The marketplace owner manually updates a database row (name, description, GitHub URL, category). Nobody hosts any code — they just store links. When a new version of a server comes out, either the marketplace owner updates the listing manually or the server's author submits another issue. There is no install mechanism, no version tracking, no quality signal, no automation, and no canonical hosted copy of anything.

### 3.2 The Real Gaps (What Nobody Has Built)

1. **No quality signal** — You cannot tell if an MCP server is production-ready or a 30-minute toy demo. With 10,000+ servers where most are low quality, this makes discovery worse, not better.
    
2. **No install mechanism** — There is no `mcp install X` command. You clone repos manually, figure out dependencies yourself, and edit JSON config files by hand for each AI client you use.
    
3. **No config standardization** — Claude Desktop, Cursor, VS Code Copilot, and every other MCP client stores its config in a different JSON file in a different location. Adding one MCP server often means editing 3–4 separate files.
    
4. **No version management** — MCP servers have no standard versioning. You cannot pin a version, roll back, or get notified of updates.
    
5. **Security is untested** — MCP servers run locally and have access to your filesystem and network by default. No existing directory scans or audits any of them.
    
6. **Context bloat problem** — In production, having too many MCP servers connected at once eats massive amounts of AI context window (one team burned 72% of their context window just on tool definitions). No tooling helps manage this.
    

---

## 4. The Vision

### 4.1 What MCP Hub Will Be

Three things that work together — exactly like npm:

```
npmjs.com            →   mcphub.dev          (website: browse, search, read docs)
registry.npmjs.org   →   registry.mcphub.dev (database: all registered servers + metadata)
npm CLI              →   mcp CLI             (your computer: install, publish, update, manage)
```

Plus one new thing npm doesn't have:

```
                         MCP Hub Desktop     (local daemon: manages all MCP clients from one place)
```

### 4.2 The Upgrade Idea — MCP Hub Desktop

**This is an original idea that does not exist anywhere.**

Instead of each AI client (Claude, Cursor, etc.) managing its own MCP config separately, MCP Hub Desktop is a local application that:

- Runs as a background service on your computer
- Maintains ONE master list of your installed MCP servers
- Exposes a local API (or uses a key/token system) that any AI client can connect to
- When a client needs to use an MCP server, it routes through MCP Hub Desktop instead of managing servers directly
- The user installs and manages everything in one place — MCP Hub Desktop — and all their AI tools just work

This solves the config fragmentation problem completely. It also means:

- You update one server once, all AI clients get the update
- You can see which AI client is using which server and when
- You can enable/disable servers per client from one UI
- Security scanning can happen at this layer

**Analogy**: Think of it like a VPN or a local proxy. Your apps don't each manage their own network settings — they route through a central layer that handles it.

### 4.3 The Config Standardization Idea — `mcpconfig`

**Another original idea.**

Propose and build a standard: one config file (e.g., `~/.mcp/mcpconfig.json`) that lives in one place on your machine. All MCP clients that adopt the standard read from this file. MCP Hub Desktop writes to this file.

This is how SSH works (`~/.ssh/config`) and how many CLI tools share config. If MCP Hub Desktop gets adoption, pushing this standard alongside it is natural.

---

## 5. Current Landscape — What Already Exists

### 5.1 The Official Registry

The Linux Foundation (which governs MCP) has an official registry on its 2026 roadmap. As of May 2026, no code is publicly available. It is a stated intention, not a shipped product.

**Implication**: There is a window to become the de facto community standard before the official one is good enough to compete. This window is estimated at 6–18 months.

**Precedent**: Homebrew became the dominant Mac package manager before Apple shipped an official equivalent. npm became dominant for JavaScript before any official Node.js governance formalized it.

### 5.2 How Existing Directories Work

Developers submit servers by opening GitHub issues. Maintainers add them manually. No install mechanism. No version tracking. No automation. No quality checks.

---

## 6. Core Architecture

### 6.1 The Registry

The registry is a database that stores metadata about every MCP server registered on MCP Hub. It does NOT necessarily host the code (more on this in hosting decisions below).

Each registered server entry contains:

- Name, description, category, tags
- Author / organization
- Source repository URL (GitHub, GitLab, etc.)
- Supported environments (Node.js version, Python version, Docker, etc.)
- Version history
- Install manifest (how to install it — see 6.3)
- Quality tier (Community / Verified / Official)
- Compatibility matrix (which MCP clients it works with)
- Security scan status
- Download/install count

### 6.2 The Website

A web interface for:

- Browsing and searching servers
- Viewing server detail pages (docs, versions, install command, reviews)
- Publishing/registering a new server
- Developer dashboards (manage your published servers)
- Quality tier information

### 6.3 The CLI — `mcp`

The command-line tool users install once. Written independently — does NOT rely on `npm install` under the hood.

```bash
mcp install github-server       # install a server by name
mcp install github-server@1.2.0 # install specific version
mcp remove github-server        # uninstall
mcp update                      # update all servers
mcp list                        # see installed servers
mcp publish                     # publish your server to registry
mcp search "github"             # search the registry
mcp enable github-server        # enable for current AI client
mcp disable github-server       # disable without uninstalling
```

**How `mcp install` works (without npm):**

The CLI fetches the server's install manifest from the registry. The manifest specifies:

- What runtime is needed (Node.js 18+, Python 3.10+, Docker, etc.)
- Where to fetch the code from (GitHub release, direct download, etc.)
- What dependencies to install (using the native tool for that runtime: `pip`, `cargo`, etc.)
- How to configure it (environment variables, config file locations)
- Which MCP client config files to update

The CLI handles each runtime differently but the USER only ever runs `mcp install X`. The complexity is hidden.

**Handling multi-runtime servers** (e.g., a server with both Node and Python versions):

- The manifest declares both options
- The CLI detects what's available on the user's machine
- Defaults to the more common runtime, or asks the user to choose
- This is a solvable problem and can be improved over time

### 6.4 MCP Hub Desktop (Future)

A local background application that acts as a **policy enforcement and routing layer** between AI clients and MCP servers.

```
AI Client (Claude, Cursor, etc.)
        ↓
MCP Hub Desktop   ← checks permissions, logs calls, blocks violations
        ↓
MCP Server (filesystem, github, slack, etc.)
```

**Key capabilities**:

- Acts as a central router for all MCP server connections
- Exposes a standard local API (e.g., `http://localhost:PORT`) that AI clients connect to
- AI clients connect via API key or token instead of managing servers directly
- Maintains the `mcpconfig` standard file
- Provides a UI for managing all servers across all AI clients
ask me any and all possible questions you need to know before generating a better answer. correct me anywhere needed and add any possible tips, suggestions or advices you can
**Permissions layer** (novel, nobody else is building this):

Every installed MCP server gets a permission profile. MCP Hub Desktop inspects every message passing between the AI client and the server. If a request violates the permission profile, it is blocked before reaching the server.

Example permission profiles:

```yaml
github-server:
  allowed:
    - read_repos
    - list_issues
    - read_pull_requests
  blocked:
    - delete_repo
    - push_code
    - manage_secrets

filesystem-server:
  allowed:
    - read: /home/user/documents
    - read: /home/user/projects
  blocked:
    - read: /home/user/.ssh
    - read: /home/user/.env
    - write: anywhere
```

This is technically feasible because MCP is a defined protocol — every message has a known structure that can be inspected and filtered. This is similar to how a firewall inspects network packets. Users can set permissions when installing a server or adjust them later via the UI.

**Why this is a major differentiator**: No AI client, no existing directory, and not even the planned Linux Foundation registry is building permission management at this layer. This directly addresses the security gap where MCP servers currently get unrestricted access to whatever their code asks for.

---

## 7. Quality Control — Options & Trade-offs

This is the most important design decision. Quality is what differentiates MCP Hub from being just another directory.

### Option A — Manual Review Only (GitHub PR model)

Every server submission is reviewed by a human maintainer before listing.

**Pros:**

- Highest quality bar
- Human judgment catches things automation can't
- No infrastructure needed to build

**Cons:**

- Does not scale. At 100+ submissions/day you cannot keep up alone.
- Creates a bottleneck that frustrates developers
- Slow time-to-listing kills momentum
- You become a single point of failure

**Verdict**: Fine for Phase 1 when you have 50 servers. Unsustainable by Phase 2.

---

### Option B — Automated Testing Pipeline Only

Every submission runs through an automated test suite. If it passes, it gets listed.

**Pros:**

- Scales to any volume
- Consistent and objective
- Fast (minutes, not days)

**Cons:**

- Hard to build well — what do you test for?
- Can be gamed (pass the tests, still be low quality)
- False positives (good servers that fail edge case tests)
- Significant infrastructure cost to run tests at scale

**Verdict**: Right direction but insufficient alone.

---

### Option C — Community Signals (Stars, Downloads, Reports)

List everything. Let usage data surface quality. GitHub stars, weekly installs, abuse reports drive visibility.

**Pros:**

- Zero gatekeeping, maximum inclusivity
- Scales automatically
- Popular = trusted (roughly)

**Cons:**

- New good servers are invisible until they get traction
- Popularity ≠ quality or safety
- Can be gamed with fake stars/installs
- Does nothing about security

**Verdict**: A useful signal but not a quality system on its own.

---

### Option D — Tiered System (Recommended)

Three tiers, earned progressively:

|Tier|Who|How earned|What it means|
|---|---|---|---|
|**Community**|Anyone|Submit via CLI/web|Listed, no guarantees|
|**Verified**|Active developers|Pass automated tests + manual spot check|Works correctly, maintained|
|**Official**|Server's own creator (company/org)|Identity verified, SLA commitment|Canonical, trusted|

**Pros:**

- Scales (Community tier is open, Verified is automated+spot-check)
- Clear signal to users without gatekeeping
- Creates a natural progression for server authors
- Mirrors how npm (unverified) vs npm trusted publishers works

**Cons:**

- More complex to build and communicate
- Need to define exactly what "Verified" tests for
- Risk of Verified tier being gamed if criteria are weak

**Verdict**: This is the right long-term model. Start with Community only, add Verified in Phase 2.

---

### Option E — Automated + Human Hybrid (Ideal end state)

Automated pipeline runs first (catches crashes, obvious security issues, malformed manifests). Passes to a lightweight human spot-check queue. Community reports feed back into re-review.

**Verdict**: Where you want to be in Phase 3+. Too much to build on day one.

---

### Recommended Quality Strategy by Phase

- **Phase 1**: Manual review (you curate a small, excellent starting set of ~50–100 servers). Quality by curation.
- **Phase 2**: Open submissions + Community tier. Add automated basic checks (does it install? does it start?).
- **Phase 3**: Verified tier with proper automated test suite + spot checks.
- **Phase 4**: Official tier with identity verification.

---

## 8. Versioning

Versioning is what makes a registry serious vs. a directory. Without it, developers cannot pin dependencies, reproduce environments, or safely update.

**Proposed standard**: Semantic Versioning (semver) — `MAJOR.MINOR.PATCH`

- Breaking changes → bump MAJOR
- New features → bump MINOR
- Bug fixes → bump PATCH

The registry stores every published version. `mcp install github-server@1.2.0` installs exactly that version. `mcp install github-server` installs the latest stable.

**How authors publish versions**:

```bash
mcp publish          # publishes current version from manifest
mcp publish --patch  # auto-bumps patch version
```

The CLI reads a server's `mcp.json` manifest file (equivalent of `package.json`) which declares the version.

---

## 9. Hosting & Infrastructure

### 9.1 What Makes a Real Registry vs a Fancy Directory

This is the most important infrastructure question.

**A directory** stores metadata (name, description, GitHub URL) and points users to the author's GitHub. If the author deletes their repo or changes a release, users are broken. This is what all current MCP marketplaces are.

**A real registry** (like npm) owns the canonical copy of every published version. When you `npm publish`, your code is packaged into a tarball and uploaded to npm's servers permanently. When you `npm install`, you download from npm — not from GitHub. The author's GitHub repo is irrelevant to the install. This is why npm packages survive even if the author's GitHub account is deleted.

**The left-pad lesson**: In 2016 a developer unpublished a tiny npm package. Thousands of projects depending on it broke instantly. npm responded by making unpublishing impossible after 24 hours. The lesson: a registry must own the canonical copy, and it must be immutable once published.

**MCP Hub must own the tarballs.** At publish time:

1. Author runs `mcp publish`
2. CLI packages the server code into a tarball
3. Tarball is uploaded to MCP Hub's object storage
4. A SHA-256 hash of the tarball is stored in the registry database
5. When anyone runs `mcp install X@1.2.0`, the tarball is downloaded from MCP Hub's storage and the hash is verified

GitHub is now just where the author develops. It has no role in installs.

### 9.2 How Other Registries Handle Hosting Cost

- **npm**: Hosts all code themselves. Funded through GitHub (Microsoft acquisition).
- **PyPI**: Hosts code. Funded by Python Software Foundation + donated storage from AWS and Fastly.
- **Homebrew**: Does NOT host code — stores install scripts (formulas) in GitHub repos, actual binaries come from original sources. Near-zero cost, but also the weakest reliability guarantee.
- **Cargo (Rust)**: Metadata on crates.io, tarballs stored on their own servers, funded by Mozilla and later the Rust Foundation.

### 9.3 Recommended Approach for MCP Hub

**Phase 1**: Metadata + GitHub source (accept the directory limitation temporarily). Near-zero cost. Gets the CLI working.

**Phase 2**: Snapshot tarballs on publish using Cloudflare R2 object storage. R2 has no egress fees (unlike AWS S3) and a generous free tier. This is what makes you a real registry.

**Cost reality**: 10,000 MCP servers × ~5MB average tarball × 5 versions = ~250GB storage. On Cloudflare R2 this costs roughly $4/month. Extremely manageable.

### 9.4 OSS Cloud Credits

Major cloud providers donate free infrastructure to open source projects. You apply, explain the project's public benefit, and if accepted receive credits. This is how most OSS infrastructure is funded early.

Relevant programs:

- **Cloudflare**: Extremely generous for OSS. R2 storage, Workers, Pages — often free indefinitely for OSS projects.
- **AWS Open Source**: Up to $100k/year in credits for qualifying projects.
- **Google Cloud**: Similar program for OSS.
- **GitHub**: Free Actions (CI/CD), Packages, Pages for all public repos — already available to you.
- **Fly.io / Render / Railway**: All have OSS sponsorship tiers for hosting the registry API.

PyPI (Python's entire package index) runs almost entirely on infrastructure donated by AWS and Fastly. You apply for these once you have something real to show — typically after Phase 1 or 2.

---

## 10. Phased Build Plan

### Phase 1 — The Directory That Installs (Solo, 2–3 months)

Goal: Be better than every existing directory AND actually install servers.

- [ ] Website with search, categories, server detail pages
- [ ] Manual submission system (GitHub PR or web form)
- [ ] `mcp install X` CLI — works for the top 50 most popular servers
- [ ] Basic `mcp.json` manifest spec
- [ ] Semver support
- [ ] Handles Node.js and Python servers (the two most common runtimes)
- [ ] Updates the right config file for Claude Desktop and Cursor (the two most popular clients)
- [ ] Launch with ~50 hand-curated, high-quality servers

**Success metric**: Developers start using `mcp install` instead of manually cloning.

---

### Phase 2 — Open Registry (3–6 months after Phase 1)

Goal: Any developer can publish their MCP server.

- [ ] `mcp publish` CLI command
- [ ] `mcp.json` manifest validation
- [ ] Open submission system on website
- [ ] Community tier goes live
- [ ] Basic automated checks (installs? starts? doesn't crash?)
- [ ] Abuse/report system
- [ ] Version history pages
- [ ] More MCP clients supported in config injection

**Success metric**: 500+ servers registered. External developers actively publishing.

---

### Phase 3 — Quality & Trust (6–12 months)

Goal: Be the trusted registry, not just the biggest one.

- [ ] Verified tier with automated test pipeline
- [ ] Security scanning (static analysis on server code)
- [ ] Content hash verification on all installs
- [ ] MCP Hub Desktop (local daemon + unified config)
- [ ] `mcpconfig` standard proposal submitted to Linux Foundation
- [ ] Community reviews and ratings
- [ ] Dependency graph (server X requires runtime Y)

---

### Phase 4 — Platform (12 months+)

Goal: Infrastructure that the MCP ecosystem depends on.

- [ ] Official tier with identity verification
- [ ] Analytics dashboard for server authors
- [ ] Enterprise features (private registries, SSO)
- [ ] API for third-party clients to query the registry
- [ ] Formal governance / contributor structure

---

## 11. Open Questions (To Be Resolved)

These are unresolved decisions that need more thinking:

1. **Name**: "MCP Hub" is a placeholder. Domain availability and GitHub org need checking.
    
2. **Multi-runtime handling**: If a server has both Node.js and Python versions, how does the CLI choose? Auto-detect based on what's installed? Always ask? Preference in user config?
    
3. **What exactly does `mcp install` do for Docker-based servers?** Does MCP Hub require Docker to be installed? Does it pull the image? This needs a concrete answer.
    
4. **How does MCP Hub Desktop connect to AI clients?** API key? Local socket? Each client would need to support it. This might require contributing to those clients' codebases or petitioning them to support a standard.
    
5. **Governance**: Who reviews Verified tier applications? Is this the founder forever? A community committee? A DAO-style model?
    
6. **Monetization**: The project needs to be sustainable. Options: donations, cloud credits, enterprise private registries, sponsored listings (carefully). This affects trust — needs to be thought through carefully.
    
7. **Official registry relationship**: When the Linux Foundation ships its official registry, do you compete, federate, or position as the community layer on top?
    
8. **How do you handle servers that get abandoned?** Author stops maintaining. Security vulnerability is found. Who patches it? Who pulls it?
    

---

## 12. Competitive Positioning

||Existing directories|Linux Foundation registry|MCP Hub|
|---|---|---|---|
|Install mechanism|❌|Likely ✅|✅|
|Quality tiers|❌|Unknown|✅|
|Version management|❌|Likely ✅|✅|
|Security scanning|❌|Unknown|✅ (Phase 3)|
|Desktop client|❌|Unlikely|✅ (Phase 3)|
|Config standardization|❌|Possibly|✅ (Phase 3)|
|Community-first|✅|Probably not|✅|
|Speed of shipping|N/A|Slow (committee)|Fast|

---

## 13. Notes, Principles & Reminders

- **Don't be just a fancier directory.** The install mechanism and quality signal are what make this real.
- **Ship Phase 1 before the Linux Foundation ships anything.** Mindshare (developer habit and awareness) is won by being first and being good.
- **Mindshare** = the developer ecosystem's default choice. Like how developers instinctively type `npm install` without thinking. You want `mcp install` to feel that natural.
- **Start small, curate ruthlessly.** 50 excellent servers beats 5,000 mediocre ones.
- **The desktop app and config standard are differentiators** that no directory or the official registry is likely to build. These are worth protecting as ideas and shipping as unique features.
- **You do not need to be a Linux Foundation to win.** Homebrew, npm, and many other tools became dominant through community trust, not institutional authority.
- **Cloud costs are manageable early.** Start metadata-only + GitHub source. Apply for OSS cloud credits as you grow. Storage costs come much later.

---

_This document will be updated as the project evolves. Major decisions should be recorded here with rationale._
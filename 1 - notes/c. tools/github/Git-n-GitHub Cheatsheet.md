---
status: newBorn
related-links:
  - "[[Cheatsheets-MOC]]"
created: 2025-03-30T21:10
updated: 2025-04-11T10:40
---
---
### **Basics**

- `git init`: Initialize a local repo.
- `git clone <url>`: Clone a remote repo.
- `git config --global user.name "Name"`: Set global username.
- `git config --global user.email "email"`: Set global email.

---

### **Workflow**

- `git status`: Show changed/untracked files.
- `git add <file>`: Stage a file.
- `git add .`: Stage all changes.
- `git commit -m "message"`: Commit staged changes.
- `git commit -am "message"`: Stage tracked files & commit (skips `git add`).
- `git diff`: Show unstaged changes.
- `git diff --staged`: Show staged changes.

---

### **Branching**

- `git branch`: List branches.
- `git branch <name>`: Create a branch.
- `git checkout <branch>`: Switch to branch.
- `git checkout -b <branch>`: Create & switch to branch.
- `git merge <branch>`: Merge branch into current branch.
- `git branch -d <branch>`: Delete a branch.
- **Merge Conflict**: Edit conflicted files → `git add` → `git commit`.

---

### **Remote (GitHub)**

- `git remote add origin <url>`: Link local repo to remote.
- `git push -u origin <branch>`: Push branch to remote (set upstream).
- `git push`: Push changes to remote.
- `git pull`: Fetch + merge changes from remote.
- `git fetch`: Download remote changes (no merge).
- `git remote -v`: List remote URLs / also used to check which repo is it connected to

---

### **Undoing Changes**

- `git restore <file>`: Discard unstaged changes.
- `git restore --staged <file>`: Unstage a file.
- `git reset --soft HEAD~1`: Undo last commit (keep changes staged).
- `git reset --hard HEAD~1`: Discard last commit & changes.
- `git revert <commit-id>`: Create a new commit undoing a previous commit.
- `git clean -df`: Delete untracked files/directories.
- `git `

---

### **Stashing**

- `git stash`: Temporarily save uncommitted changes.
- `git stash pop`: Restore most recent stash (and delete it).
- `git stash list`: List all stashes.

---

### **Log & History**

- `git log`: Show commit history.
- `git log --oneline`: Compact commit history.
- `git log --graph`: Visualize branch history.
- `git reflog`: Show ALL actions (helps recover lost commits).

---

### **GitHub Specific**

- **Pull Request (PR)**: Propose changes from a fork/branch.
- **Fork**: Copy a repo to your GitHub account.
- `git clone <fork-url>`: Clone your fork locally.
- `git remote add upstream <original-url>`: Link to original repo.
- `git fetch upstream`: Sync with original repo.
- `git merge upstream/main`: Merge changes from original repo.

---

### **Advanced**

- `git rebase <branch>`: Reapply commits on top of another branch.
- `git cherry-pick <commit-id>`: Apply a specific commit to current branch.
- `git tag <tag-name>`: Create a lightweight tag.
- `.gitignore`: File to exclude files/dirs (e.g., `node_modules/`, `.env`).


# Reference
`related tags + notes + source + link(if any)`
 

- 


---
status: newBorn
related-links:
  - "[[git-and-github-MOC]]"
created: 2025-03-02T01:07
updated: 2025-03-03T18:21
---
---

**initialize:**
- to set git in a repo: `git init` ( created .git file )
- to remove .git from any directory: `rem -rf .git`

**history:**
- for commit history + all the ones behind the current commit ( not ones after it ) + only shows named branch: `git log`[^1]
- for all commit history ( including the ones after the current one ): `git log --all`


**alias:**
- to create command aliases: `git config --global alias.<alias-name> "full-command"`
	- ex: `git config --global alias.cm "commit -m`
	- ex: `git config --global alias.co "checkout"`
- 



**graph:**
- to see git graph of all commits in terminal: `git log --all --graph`

# Reference
`related notes + source + link(if any)`
 

[^1]: un-name branch is when we checkout to a previous commit and without creating a new branch start to make new commit from there. 
- this creates new unnamed branch of commit which gets lost if we jump to main or other named branch before naming this one
- we can still access commits of this unnamed branch after switching to main branch only if we have commit hash of that unnamed branch.
---
status: newBorn
related-links:
  - "[[git-and-github-MOC]]"
created: 2025-03-31T20:44
updated: 2025-04-07T00:05
---
---

There are mainly two methods
- http method
- ssh keys method


### ssh keys method

- to generate ssh keys: `ssh-keygen -t ed25519 -C "your_email@example.com"`
- list all the existing ssh keys: `ls -la ~/.ssh/`
- to remove old ssh keys from ssh agent: `ssh-add -D`
	- removing ssh keys with rm or directly deleting them are the same things

![[ssh agent]]


# Reference
`related tags + notes + source + link(if any)`
 
- [[tG not-tagged]]
- 
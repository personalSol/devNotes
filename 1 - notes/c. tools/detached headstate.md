---
status: newBorn
related-links:
  - "[[git-and-github-MOC]]"
created: 2025-03-02T08:33
updated: 2025-03-03T18:24
---
---

detached head state creates a condition of unnamed branch

- when we checkout to a commit then we get detached from any branch
- in that case our head is on a commit and when we create new commits from that previous commit without being on any branch
- then that commit belongs to no branch and that's why we can't see that commit in git log ( as git log only shows commits in a branch ) after we leave that commit and switch to another branch
- to make sure it isn't lost, we have to create another branch of that commit

# Reference
`related tags + notes + source + link(if any)`
 
- [[tG github]]
- [[tG github detached head state]]
- 
# Troubleshooting

## Fixing Fork Issues

After reading the previous sections, you are now realizing your PRs and forked repo
are a little messy. Don't worry, you can clean up your main branch by following the
guide below and create a new, beautiful, PR.

### Guide

1. Create a branch from your current main branch so you don't lose any 
  changes.
   ```console
   git branch oldmain
   ```

2. Clean up your main branch by performing a hard reset from upstream's main. This
   will equalise upstream and origin - their histories will be the same. Anything
   not on upstream will be lost.
   ```console
   git fetch upstream
   git reset --hard upstream/main
   ```

3. Force-push your changes to origin
   ```console
   git push -f
   ```

4. Create a new branch for your changes/work (called `temp` below):
   ```console
   git switch -c temp
   ```

5. Then, cherry-pick your changes into your temporary branch:
   ```console
   git cherry-pick <commit>...
   ```
   - Where `<commit>...` will be the SHA's of the commits you want to bring over
   - For example, if you wanted to cherry-pick `1337abc`, `eb722ec`, `c00eba4`,
     your command will be:
     ```console
     git cherry-pick 1337abc eb722ec c00eba4
     ```
   - Don't worry - you're not expected to know cherry-picking or regularly use
     it.
   - For now, trust that this command will take your changes and store them on 
     your temporary branch. 
   - If you're interested, you can find out more about how/why this works 
     in the [Pro Git Book](https://git-scm.com/docs/git-cherry-pick).

6. ***Optionally***, if you have more than one commit, you can squash them into 
   one commit if you know how, but if not, the maintainers can squash and 
   merge your commits into the upstream repo.
   - The easiest way to squash commits is to perform an interactive rebase

After cleaning up your fork, you can now create a clean pull request from your
branch.

---

## Issues and Questions

- Nobody’s perfect, which means there may be errors and questions on component
  modules, git documentation, etc. 

- If you see a problem or have a question, ask the team and/or open a new issue 
  on GitHub using [these guidelines](https://github.com/NYU-Processor-Design/.github/blob/main/.github/CONTRIBUTING.md). 

- You should also use this contribution guide when submitting a design notebook 
  entry.

## Additional Support

- You are all talented and intelligent – that’s why you’re here – but team 
  members will join the VIP with different levels of experience and knowledge.

- The best part of working collaboratively is learning from one another and  
  supporting each other. 
  
- If you see someone struggling or learning something new, offer your assistance
  in a helpful and respectful way.


---

[^ff]: [Fast-forwarding](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging) is 
when git moves the head pointer forward to the tip of the target. You don't
have to actually "merge" the branches.

[^name]: We implore you to choose good branch names. Names like `temp`, `fix`, 
etc. are not descriptive. For example, if you're working on a UART, name your 
branch `uart`.

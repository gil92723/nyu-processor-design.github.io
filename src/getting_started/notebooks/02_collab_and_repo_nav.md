# Working Collaboratively

---
## Purpose

Collaboration is an essential part of working in any team. Much of our work is 
shared and built upon each others’ contributions - whether it is the components 
themselves, editing documentation, or making improvements to this website. 

Additionally, as team members join the team with different 
areas of expertise, it is important to support one another in the learning and 
development process.

---

## Terminology
- `upstream`: The main repository owned by the organisation
- `origin`: Your fork of the repository

---

## Team Repositories

- Team members should have access to the [NYU Processor Design GitHub organization](https://GitHub.com/NYU-Processor-Design). 

- Throughout the project, you will need to work on the shared repos - for 
  example, adding a design notebook entry to [our website](https://GitHub.com/NYU-Processor-Design/nyu-processor-design.GitHub.io), or editing a component of the [AMBA](https://GitHub.com/NYU-Processor-Design/nyu-amba) or 
  [core](https://GitHub.com/NYU-Processor-Design/nyu-core). 

- To work efficiently, you want to:
  1. fork the appropriate repo and make a branch 
  on your fork. 
  2. *After making changes*, create a pull request to merge your changes to the team’s
  repository by following [this guide](03_first_pr.md). 
  3. Once your changes have been merged, delete your branch and update your fork.

---

## Working on Forks

- When working on your fork of a active and constantly updating repository, 
  you want to avoid working directly on the main branch of your fork. 

- This keeps `main` clean to fast-forward[^ff] any changes from upstream. 

- If you work on `main`, merging changes from upstream will cause "merge" commits,
  making `upstream` and `origin` have different histories

- It also creates extra work for the maintainers because they have to clean 
  your fork before merging your changes.

- Working on `main` will also create messy pull requests with merge commits and 
  other commits that aren't associated with your work. 

- This 'pollution' makes it harder for git to incorporate changes from upstream
  and may cause merge conflicts, which will have to be fixed

- **Before you start working**, make sure to update your fork's main branch to 
  match the team's upstream repo. 
  - You can use the "Sync fork" button on GitHub 
  <img src="/images/sync-fork-github.jpg" width="90%" style="margin-left: auto; margin-right: auto; display: block;" />
  
  - Or, locally with the following commands:
    ```console
    git pull upstream main
    git push origin main
    ```

- Make the changes you need by [contributing with your repo](#Contributing with Your Repo), then, follow the [Your First Pull Request](03_first_pr.md) guide. 

---

# Contributing with Your Repo

---

## Purpose

While some developers prefer to use `git` purely from the command line, others
enjoy using the interface built in to their IDE. This is purely a
preference-based decision. In this section, we'll demonstrate how do work
through some common `git` operations using both the command line, and how do to
the equivalent operation using the Source Control tab on VSCode and Anubis. Note that most of these features are provided by the *GitLens* plugin for VSCode and Anubis. 

There is far, far more to `git` than could be productively covered here. It is
highly recommended that you seek guidance from
[the Git Book](https://git-scm.com/book/en/v2) for a complete discussion of both
basic and advanced operations.

## Initializing a Repository

**Using git:** Inside a new empty folder, you can create a new `git` repo using the command

```
git init
```

**Using source control:** Click the "Initialize Repository" button in the Source Control
tab, which can be found after clicking on the third icon on the far left ribbon.

<img src="/images/git/init.webp" width="50%" style="margin-left: auto; margin-right: auto; display: block;" />

## Staging Files

**Using git:** When a new file is added to the project, or changes are made to a file, you can
inform `git` about those changes with the command:

```
git add [file_or_folder_names]
```

This command adds the files to "staging", which is what we call the set of file
changes that we're going permanently track in the repository.

A common pattern is to use:

```
git add .
```

Where the `.` is a Unix filesystem convention for refering to the current
folder. This command tells `git` to add all files that have been added or
changed to "staging".

**Using source control:** The equivalent in the Source Control tab is to use the plus and minus signs on the right of a file when hovered over to move
files in and out of "staging":

<img src="/images/git/staging.png" width="50%" style="margin-left: auto; margin-right: auto; display: block;" />

## Making a Commit

To make the collection of changes in staging permanent, we make a _commit_.
Every commit is accompanied by a message. You are encouraged, by not required,
to follow the [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/)
guidelines for what to write in this message. The czar of a given repo may
require this or some other commit message format if you eventually want them to
incorporate your changes "upstream".

**Using git:** The commands to make a commit message depend on how long your message is,
commits with short messages can be made with the following:

```
git commit -m "docs(example): This is a commit message"
```

If a longer message is needed, the same command without the `-m` can be used:

```
git commit
```

`git` will open an editor to be filled with the commit message, when the file
is saved and the editor is exited, `git` will open that file and read the
commit message.

**Using source control:** Add a commit message at the top bar that says "Message", then click the blue commit box to commit your *staged changes* (do make sure your changes are staged in order to be committed):

<img src="/images/git/commit.png" width="50%" style="margin-left: auto; margin-right: auto; display: block;" />

## Pushing Changes

Once changes have been made to a local repo, they can be pushed to tracked
remotes 

**Using git:** Utilize the command

```
git push
```
**Using source control:** Click the blue "Sync Changes" box, which would then push your changes to your branch and confirm the push pull that will occur when prompted

<img src="/images/git/sync.png" width="50%" style="margin-left: auto; margin-right: auto; display: block;" />

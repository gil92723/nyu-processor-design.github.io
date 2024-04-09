# Working With Your Repo

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
**Using source control:** Click the blue "Sync Changes" box, which would then push your changes to main

<img src="/images/git/sync.png" width="50%" style="margin-left: auto; margin-right: auto; display: block;" />

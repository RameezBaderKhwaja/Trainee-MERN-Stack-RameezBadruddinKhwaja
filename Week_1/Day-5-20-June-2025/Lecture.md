#### What is Git?

* A distributed version control system (DVCS) created in 2005 by Linus Torvalds 
* Tracks files, stores full project history locally, and supports offline work 
* Enables safe collaboration via branching, merging, and conflict handling 

#### What is GitHub?

* A cloud-based platform built on Git for hosting code repositories 
* Adds collaboration tools: pull requests, issues, code reviews, CI/CD, and web-based editing .
* Hosts over 100 million developers and 420+ million repositories 

### Core Concepts and Workflow

#### Repository

* Folder tracked by Git; stores all files and history.

#### Commits

* Snapshots of changes with metadata; uniquely identified.

#### Branches

* Independent lines of development; default branch often named `main` or `master`.

#### Local vs Remote

* Local: full copy on your machine.
* Remote: hosted on platforms like GitHub; synced via push/pull.

### Common Git Commands

```
git init                     # initialize local repo
git clone <url>             # copy remote repo locally
git status                  # show tracked/untracked files
git add <file>/.<folder>    # stage changes
git reset HEAD -- <file>    # unstage a file
git commit -m "message"     # save snapshot
git log                     # list commit history
git diff                    # show changes
git rm <file>               # delete file
git mv <old> <new>          # rename file

git branch                  # list local branches
git branch -r               # list remote branches
git branch <name>           # create branch
git checkout <name>         # switch branch
git checkout -b <name>      # create + switch
git merge <branch>          # merge into current branch
git branch -d <branch>      # delete branch

git remote add <name> <url> # add remote alias
git remote -v               # list remotes
git fetch <name>            # fetch updates without merging
git pull                    # fetch + merge
git push <name> <branch>    # send commits to remote
git stash                   # temporarily save changes
git stash pop               # restore stashed changes
```


### Branching & Collaboration

1. Create or fork a repo on GitHub.
2. Create a feature branch:
   `git checkout -b feature-name`.
3. Make changes → `git add` → `git commit`.
4. Push branch:
   `git push origin feature-name`.
5. Open a pull request on GitHub for review.
6. Merge PR and delete branch 


### Undoing Changes

* `git reset HEAD <file>` to unstage.
* `git revert <commit>` to undo (creates a new commit).
* `git reset --hard <commit>` to reset head and working tree.

### Configuration & Setup

```
git config --global user.name "Name"
git config --global user.email "email@example.com"
git config --global color.ui auto
git config --list
```

### Benefits of Git & GitHub

* Git enables version control, collaboration, and reliable branching/merging
* GitHub adds remote hosting, issue tracking, pull requests, CI/CD, and social coding features 
* Supports distributed work, backup, and project visibility

### Recommended Workflow Summary

1. `git init` or `git clone <url>`
2. `git branch feature`
3. `git checkout feature`
4. `git add .`
5. `git commit -m "message"`
6. `git push origin feature`
7. Open pull request → review → merge
8. Delete branch

# Git Branching Basics

- Create a branch: `git branch branch-name`
- Switch branches: `git switch branch-name` or `git checkout branch-name`
- Rename branch: `git branch -m new-name`
- Delete local branch: `git branch -d branch-name`
- Delete remote branch: `git push origin --delete branch-name`

# Publishing and Tracking

- Publish a branch: `git push -u origin branch-name`
- Track a remote branch: `git branch --track local remote/branch`
- After tracking, use `git push` and `git pull` without extra options.

# Merge and Rebase

- Merge a branch: `git merge feature`
- Squash commits into one: `git merge --squash feature`
- Rebase: `git rebase main`
- Apply feature commits on top of main for a clean history.

# Merge Conflicts

- Conflicts happen when changes affect the same lines.
- Git marks conflicts with `<<<<<<<`, `=======`, `>>>>>>>`.
- Edit manually to keep or combine changes.
- Resolve steps:
  - Edit and save file
  - `git add .`
  - `git rebase --continue` or commit
  - Push changes (`--force` if rebasing)

# Git Productivity Tips

- Combine add and commit: `git commit -am "msg"`
- Alias: `git config --global alias.ac 'commit -am'`
- Amend last commit: `git commit --amend -m "new msg"`
- Revert a commit: `git revert <commit_id>`
- Open GitHub repo in browser: press `.`
- Use GitHub Codespaces for remote editing

# Stashing Changes

- Save changes: `git stash`
- Name stash: `git stash save "msg"`
- Apply stash: `git stash apply stash@{0}`
- Remove after apply: `git stash pop`

# Git Log and Search

- Cleaner log: `git log --graph --oneline --decorate`
- Find bug commit: `git bisect start`, `bad`, `good <commit>`

# Squashing Commits

- Interactive: `git rebase -i main`
- Use `squash` or `fixup` to combine commits

# Git Hooks

- Automate tasks with `husky`:
  ```bash
  npm install husky --save-dev

# Reset and Clean

* Reset to remote:

  ```bash
  git fetch
  git reset --hard origin/main
  git clean -fd
  ```
* Delete Git: remove `.git` folder

# Quick Tips

* Go to last branch: `git checkout -`


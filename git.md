# Git Cheatsheet

Quick Git commands for everyday work.

## Setup

```sh
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

git config --global --list
```

## Create / Clone

```sh
# Initialize a repository
git init

# Initialize with main as the default branch
git init -b main

# Clone a repository
git clone <url>

# Clone into a specific directory
git clone <url> <directory>
```

## Status

```sh
git status

# Compact status
git status --short
```

## Staging

```sh
# Stage one file
git add file

# Stage everything
git add .

# Unstage a file
git restore --staged file
```

## Commits

```sh
git commit -m "feat: add feature"

# Amend latest commit
git commit --amend

# Amend without changing the message
git commit --amend --no-edit
```

## Branches

```sh
# List branches
git branch

# Create branch
git branch feature

# Create and switch
git switch -c feature

# Switch branch
git switch main

# Rename current branch
git branch -M main

# Delete branch
git branch -d feature
```

## Remote

```sh
git remote -v

git remote add origin <url>

git remote set-url origin <url>
```

## Push / Pull

```sh
git push

git pull

# First push
git push -u origin main

# Fetch without merging
git fetch
```

## Diff

```sh
# Unstaged changes
git diff

# Staged changes
git diff --staged

# Compare branches
git diff main..feature
```

## Log

```sh
git log

git log --oneline

git log --oneline --graph --decorate --all
```

## Restore

```sh
# Restore file from HEAD
git restore file

# Unstage
git restore --staged file
```

> Be careful: restoring files can discard local changes.

## Stash

```sh
git stash

git stash list

git stash pop

git stash apply

git stash drop
```

## Tags

```sh
git tag

git tag v1.0.0

git push origin v1.0.0

git push origin --tags
```

## Useful

```sh
# Show tracked files
git ls-files

# Show latest commit
git show

# Show current branch
git branch --show-current

# Clean merged local branches
git branch --merged
```

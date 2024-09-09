# Git-PRACTICE
Understand to use of git command and practice it

# Git Commands and Troubleshooting Guide

## Overview

This document provides a list of common Git commands with brief explanations, as well as a guide for handling and preventing merge issues.

## Common Git Commands

### Basic Commands

- **`git init`**
  - Initializes a new Git repository in the current directory.
  
- **`git clone <repository-url>`**
  - Creates a local copy of a remote repository.

- **`git add <file>`**
  - Stages changes to a file for the next commit. Use `git add .` to stage all changes.

- **`git commit -m "<message>"`**
  - Commits staged changes with a descriptive message.

- **`git status`**
  - Shows the status of the working directory and staging area.

- **`git log`**
  - Displays the commit history.

- **`git diff`**
  - Shows changes between commits, commit and working directory, etc.

- **`git branch`**
  - Lists all branches or creates a new branch if used with a name.

- **`git checkout <branch>`**
  - Switches to the specified branch.

- **`git merge <branch>`**
  - Merges changes from the specified branch into the current branch.

- **`git pull origin <branch>`**
  - Fetches and merges changes from the remote branch into the current branch.

- **`git push origin <branch>`**
  - Pushes the current branch’s commits to the remote repository.

- **`git fetch origin`**
  - Downloads changes from the remote repository without merging.

- **`git reset --hard <commit>`**
  - Resets the working directory and index to a specific commit, discarding changes.

- **`git stash`**
  - Temporarily saves changes that are not ready to be committed.

- **`git stash pop`**
  - Restores the most recently stashed changes.

### Advanced Commands

- **`git rebase <branch>`**
  - Re-applies commits from the current branch on top of the specified branch.

- **`git cherry-pick <commit>`**
  - Applies changes from a specific commit onto the current branch.

- **`git revert <commit>`**
  - Creates a new commit that undoes changes made in a specified commit.

- **`git tag <tagname>`**
  - Creates a tag with the specified name.

- **`git remote -v`**
  - Lists the remote repositories associated with the local repository.

- **`git remote add <name> <url>`**
  - Adds a new remote repository with a given name.

- **`git push --force`**
  - Forces the push to overwrite the remote branch, potentially losing commits.

## Handling Merge Issues

### Scenario

You attempted to push changes from your `development` branch to the `features/walkthrough` branch but encountered a "non-fast-forward" error.

### Resolution Steps

1. **Fetch and Review Remote Branch:**
   ```bash
   git fetch origin
   git checkout <branch name>
   git merge origin/<branch name>

# Git Operations and Strategies

## Resolving Conflicts

1. **Manually resolve conflicts** in your files.

2. **Stage the resolved files**:
    ```bash
    git add <file>
    ```

3. **Commit the resolved changes**:
    ```bash
    git commit -m "Resolved merge conflicts"
    ```

## Pushing the Merged Branch

1. **Checkout to the development branch**:
    ```bash
    git checkout <branch name>
    ```

2. **Push the merged branch**:
    ```bash
    git push origin <from this branch name>:<to this branch name>
    ```

## Prevention Strategies

1. **Regularly Pull and Merge**:
    Frequently pull changes from remote branches to keep your local branches up-to-date and avoid conflicts.
    ```bash
    git pull origin <branch name>
    ```

2. **Check Remote Branch Status**:
    Before pushing, verify if your branch is behind the remote branch.
    ```bash
    git fetch origin
    git status
    ```

3. **Use Pull Requests**:
    Use pull requests (PRs) on platforms like GitHub or GitLab to review and integrate changes. This helps prevent issues by ensuring code reviews and integration checks.

4. **Avoid Force Pushes**:
    Avoid using `git push --force` unless absolutely necessary, as it can overwrite important changes on the remote branch.

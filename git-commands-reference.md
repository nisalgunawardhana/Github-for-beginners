# 📋 Git Command Reference Guide

This file serves as a quick reference for Git commands. Feel free to practice by adding your own notes and examples!

## 🚀 Basic Commands

### Repository Setup
```bash
# Clone a repository
git clone https://github.com/username/repository.git

# Initialize a new Git repository
git init

# Add remote repository
git remote add origin https://github.com/username/repository.git

# View remote repositories
git remote -v
```

### Checking Status and History
```bash
# Check repository status
git status

# View commit history
git log

# View commit history in one line format
git log --oneline

# View specific number of commits
git log -5

# Show changes between commits
git diff
```

## 🌿 Branch Operations

### Creating and Switching Branches
```bash
# List all branches
git branch

# Create new branch
git branch branch-name

# Switch to branch
git checkout branch-name

# Create and switch to new branch (shortcut)
git checkout -b branch-name

# Switch to main/master branch
git checkout main
```

### Branch Management
```bash
# Rename current branch
git branch -m new-branch-name

# Delete branch (safe - won't delete if unmerged)
git branch -d branch-name

# Force delete branch
git branch -D branch-name

# Push branch to remote
git push origin branch-name

# Delete remote branch
git push origin --delete branch-name
```

## 📝 Making Changes

### Staging and Committing
```bash
# Add specific file to staging area
git add filename.txt

# Add all changes to staging area
git add .

# Add all files with specific extension
git add *.md

# Remove file from staging area
git reset filename.txt

# Commit staged changes
git commit -m "Your commit message"

# Add and commit in one step (for tracked files)
git commit -am "Your commit message"

# Amend last commit message
git commit --amend -m "New commit message"
```

### Undoing Changes
```bash
# Discard changes in working directory
git checkout -- filename.txt

# Discard all local changes
git checkout -- .

# Reset to last commit (keep changes in working directory)
git reset --soft HEAD~1

# Reset to last commit (discard changes)
git reset --hard HEAD~1

# Revert a commit (creates new commit)
git revert commit-hash
```

## 🔄 Synchronizing with Remote

### Pulling Changes
```bash
# Fetch changes from remote (doesn't merge)
git fetch

# Fetch from specific remote
git fetch origin

# Pull changes and merge
git pull

# Pull from specific branch
git pull origin main

# Pull with rebase
git pull --rebase
```

### Pushing Changes
```bash
# Push to remote repository
git push

# Push to specific remote and branch
git push origin branch-name

# Push and set upstream tracking
git push -u origin branch-name

# Force push (use carefully!)
git push --force
```

## 🔀 Merging and Rebasing

### Merging
```bash
# Merge branch into current branch
git merge branch-name

# Create merge commit even for fast-forward
git merge --no-ff branch-name

# Abort merge if conflicts arise
git merge --abort
```

### Rebasing
```bash
# Rebase current branch onto main
git rebase main

# Interactive rebase for last 3 commits
git rebase -i HEAD~3

# Continue rebase after resolving conflicts
git rebase --continue

# Abort rebase
git rebase --abort
```

## 🏷️ Tags and Releases

```bash
# Create lightweight tag
git tag v1.0.0

# Create annotated tag
git tag -a v1.0.0 -m "Version 1.0.0"

# List all tags
git tag

# Push tags to remote
git push origin --tags

# Delete tag
git tag -d v1.0.0

# Delete remote tag
git push origin --delete v1.0.0
```

## 📦 Stashing

```bash
# Stash current changes
git stash

# Stash with message
git stash save "Work in progress on feature X"

# List all stashes
git stash list

# Apply most recent stash
git stash apply

# Apply specific stash
git stash apply stash@{2}

# Pop most recent stash (apply and remove)
git stash pop

# Drop most recent stash
git stash drop

# Clear all stashes
git stash clear
```

## 🔍 Searching and Blame

```bash
# Search for text in files
git grep "search term"

# Show who changed each line of a file
git blame filename.txt

# Show commit that introduced a bug
git bisect start
git bisect bad
git bisect good commit-hash
```

## ⚙️ Configuration

### Global Configuration
```bash
# Set global username
git config --global user.name "Your Name"

# Set global email
git config --global user.email "your.email@example.com"

# Set default branch name
git config --global init.defaultBranch main

# Set default editor
git config --global core.editor "code --wait"

# View all global configuration
git config --global --list
```

### Repository-Specific Configuration
```bash
# Set username for current repository only
git config user.name "Your Name"

# Set email for current repository only
git config user.email "your.email@example.com"

# View repository configuration
git config --list
```

## 🎯 Practice Exercises

### Exercise 1: Basic Workflow
1. Create a new branch: `git checkout -b practice-branch`
2. Make changes to this file
3. Stage changes: `git add .`
4. Commit: `git commit -m "Practice: Add notes to Git commands"`
5. Push: `git push origin practice-branch`

### Exercise 2: Viewing History
1. Run `git log --oneline` to see commit history
2. Run `git status` to check repository status
3. Run `git branch` to see all branches

### Exercise 3: Advanced Commands
1. Create a new branch and make some commits
2. Switch back to main: `git checkout main`
3. Merge your branch: `git merge your-branch-name`
4. Delete the merged branch: `git branch -d your-branch-name`

## 📝 Your Notes Section

**Practice Space:** Use this section to add your own notes, commands you've learned, or reminders for yourself.

### Commands I've Mastered
- [ ] `git clone`
- [ ] `git add` and `git commit`
- [ ] `git push` and `git pull`
- [ ] `git branch` and `git checkout`
- [ ] `git merge`
- [ ] `git status` and `git log`

### Commands I Want to Practice More
- [ ] `git rebase`
- [ ] `git stash`
- [ ] `git cherry-pick`
- [ ] `git bisect`

### My Personal Git Aliases
```bash
# Add your custom Git aliases here
# Example: git config --global alias.co checkout
```

### Common Mistakes I've Made
1. [Add your own learning experiences here]
2. 
3. 

### Helpful Tips I've Discovered
1. Always run `git status` before committing
2. Write descriptive commit messages
3. [Add your own tips here]

---

## 🆘 Emergency Commands

When things go wrong, these commands can help:

```bash
# "I made a mistake in my last commit message"
git commit --amend -m "Correct message"

# "I want to undo my last commit but keep the changes"
git reset --soft HEAD~1

# "I want to completely undo my last commit"
git reset --hard HEAD~1

# "I'm in the middle of a merge and want to cancel"
git merge --abort

# "I want to see what I'm about to push"
git diff origin/main

# "I want to unstage all files"
git reset
```

---

**Remember:** Git has many commands, but you don't need to memorize them all at once. Focus on the basics first, then gradually learn more advanced commands as you need them.

**Last updated:** [Add today's date when you modify this file]

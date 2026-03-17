# ⏪ Undoing Changes in Git

Made a mistake? Git has several ways to undo changes depending on **where** in the workflow the change is. This guide walks through each scenario clearly.

---

## 🗺️ The Git Workflow (Quick Recap)

Understanding where your changes live helps you choose the right undo command:


<p align="center">
    <img src="../images/guides/Workflow.png" alt="GitHub for Beginners banner" />
</p>


---

## 1. 🗑️ Discard Changes in Working Directory

**Scenario:** You edited a file but haven't staged it yet, and want to throw away those edits.

```bash
# Discard changes to a specific file (modern syntax)
git restore filename.txt

# Discard all unstaged changes
git restore .
```

> ⚠️ This is **permanent** — the changes will be lost and cannot be recovered.

**Old syntax (still works):**
```bash
git checkout -- filename.txt
```

---

## 2. 📤 Unstage a File (Remove from Staging Area)

**Scenario:** You ran `git add` but haven't committed yet, and want to un-add a file.

```bash
# Unstage a specific file (keeps your changes in the working directory)
git restore --staged filename.txt

# Unstage all staged files
git restore --staged .
```

**Old syntax (still works):**
```bash
git reset HEAD filename.txt
```

---

## 3. 📦 Stash Changes (Save for Later)

**Scenario:** You're not done with your changes but need to switch branches urgently. You don't want to commit unfinished work.

```bash
# Stash your current changes (saves them, cleans working directory)
git stash

# Stash with a descriptive message
git stash push -m "WIP: adding login feature"

# List all stashes
git stash list

# Apply the most recent stash (keeps it in stash list)
git stash apply

# Apply and remove the most recent stash
git stash pop

# Apply a specific stash
git stash apply stash@{2}

# Delete a specific stash
git stash drop stash@{0}

# Delete all stashes
git stash clear
```

---

## 4. ✏️ Amend the Last Commit

**Scenario:** You just committed but made a typo in the message, or forgot to include a file.

```bash
# Change the last commit message
git commit --amend -m "New correct commit message"

# Add a forgotten file to the last commit (without changing message)
git add forgotten-file.txt
git commit --amend --no-edit
```

> ⚠️ Only amend commits that **haven't been pushed** to GitHub yet. Amending pushed commits causes problems for others.

---

## 5. 🔄 git revert — Safely Undo a Commit

**Scenario:** You want to undo a specific commit but keep the history clean (safe for shared branches).

```bash
# Revert the most recent commit
git revert HEAD

# Revert a specific commit (use git log to find the hash)
git revert a1b2c3d

# Revert without opening a commit message editor
git revert HEAD --no-edit
```

`git revert` creates a **new commit** that undoes the changes — it does not delete history. This is the **safest** way to undo on shared branches.

---

## 6. 💣 git reset — Rewrite History (Use with Caution)

**Scenario:** You want to move your branch pointer back to a previous commit.

```bash
# --soft: undo commit, keep changes staged
git reset --soft HEAD~1

# --mixed (default): undo commit, keep changes in working directory (unstaged)
git reset HEAD~1

# --hard: undo commit AND discard all changes (PERMANENT)
git reset --hard HEAD~1
```

| Flag | Commit undone? | Staging area | Working directory |
|------|---------------|--------------|-------------------|
| `--soft` | ✅ Yes | Changes kept staged | Unchanged |
| `--mixed` | ✅ Yes | Changes unstaged | Unchanged |
| `--hard` | ✅ Yes | Cleared | Changes **deleted** |

> ⚠️ **Never use `git reset --hard` on commits already pushed to a shared branch.** It rewrites history and will cause conflicts for everyone else.

---

## 7. 🍒 Undo a Specific File to a Previous Version

**Scenario:** You want to revert just one file to how it looked in a previous commit.

```bash
# Find the commit hash using git log
git log --oneline

# Restore a specific file to the version in a specific commit
git restore --source a1b2c3d filename.txt

# Stage and commit the restored file
git add filename.txt
git commit -m "Restore filename.txt to previous version"
```

---

## 📊 Quick Decision Guide

```
Did you push to GitHub yet?
├── NO  → git reset is safe to use
└── YES → Use git revert (keeps history clean)

Is the file staged but not committed?
└── Use: git restore --staged filename.txt

Is the file only in your working directory (not staged)?
└── Use: git restore filename.txt

Need to switch branches without committing?
└── Use: git stash
```

---

## 🧪 Practice Exercises

### Exercise 1 — Discard unstaged changes
1. Edit `practice-file.md` with some random text
2. Run `git status` to confirm the change
3. Run `git restore practice-file.md` to discard it
4. Run `git status` again — the change should be gone

### Exercise 2 — Unstage a file
1. Edit `practice-file.md` and run `git add practice-file.md`
2. Run `git status` — it should be in the staging area
3. Run `git restore --staged practice-file.md`
4. Run `git status` — it should be back to unstaged

### Exercise 3 — Use git stash
1. Make some changes to any file
2. Run `git stash push -m "my practice stash"`
3. Run `git stash list` to see your stash
4. Run `git stash pop` to bring the changes back

---

## 📚 Further Reading

- [GitHub Docs — Undoing commits and changes](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/changing-a-commit-message)
- [Git Docs — git restore](https://git-scm.com/docs/git-restore)
- [Git Docs — git stash](https://git-scm.com/docs/git-stash)
- [Atlassian — Resetting, Checking Out & Reverting](https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting)

---

> ⬅️ Back to [README](../README.md) | 📖 Also see: [Merge Conflicts](merge-conflicts.md)

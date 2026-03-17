# 🔀 Understanding & Resolving Merge Conflicts

Merge conflicts are one of the most common things beginners find scary — but once you understand what they are, they're easy to fix!

---

## 📖 What is a Merge Conflict?

A **merge conflict** happens when Git tries to combine two branches but finds that the **same lines in the same file were changed differently** in each branch. Git doesn't know which version to keep, so it pauses and asks you to decide.

### When do conflicts happen?
- Merging a feature branch into `main`
- Pulling changes from a remote when you have local changes
- Cherry-picking commits
- Rebasing

---

## 👀 How to Spot a Merge Conflict

When a conflict occurs, Git will tell you:

```bash
Auto-merging filename.txt
CONFLICT (content): Merge conflict in filename.txt
Automatic merge failed; fix conflicts and then commit the result.
```

Running `git status` will also show conflicted files:

```bash
git status
# Both modified: filename.txt
```

---

## 🔍 Reading Conflict Markers

When you open a conflicted file, you'll see conflict markers that Git added:

```
<<<<<<< HEAD
This is the content from your current branch (HEAD).
=======
This is the content from the branch you're merging in.
>>>>>>> feature/other-branch
```

| Marker | Meaning |
|--------|---------|
| `<<<<<<< HEAD` | Start of your current branch's changes |
| `=======` | Divider between the two conflicting versions |
| `>>>>>>> branch-name` | End of the incoming branch's changes |

---

## 🛠️ How to Resolve a Conflict (Step by Step)

### Step 1: Identify conflicted files
```bash
git status
```

### Step 2: Open the conflicted file
Open the file in VS Code. You'll see the conflict markers clearly highlighted.

> 💡 **VS Code Tip:** VS Code shows "Accept Current Change", "Accept Incoming Change", "Accept Both Changes", and "Compare Changes" buttons above each conflict — click the one that matches what you want!

### Step 3: Edit the file to keep what you want

You have three options:
- **Keep your version** → delete everything from `=======` to `>>>>>>> branch-name` (and the `<<<<<<< HEAD` line)
- **Keep their version** → delete everything from `<<<<<<< HEAD` to `=======` (and the `>>>>>>> branch-name` line)
- **Keep both** → manually combine the two versions and remove all conflict markers

**Before resolution:**
```
<<<<<<< HEAD
Hello, I am Alice.
=======
Hello, I am Bob.
>>>>>>> feature/bob-intro
```

**After resolution (example — keeping both):**
```
Hello, I am Alice and Bob.
```

> ⚠️ Make sure to **remove all conflict markers** (`<<<<<<<`, `=======`, `>>>>>>>`) before saving.

### Step 4: Stage the resolved file
```bash
git add filename.txt
```

### Step 5: Complete the merge
```bash
git commit -m "Resolve merge conflict in filename.txt"
```

---

## 💻 Full Example Walkthrough

```bash
# You're on main, and want to merge feature/new-section
git checkout main
git merge feature/new-section

# Git reports a conflict in README.md
# CONFLICT (content): Merge conflict in README.md

# Open README.md, fix the conflict, save the file

# Stage the fixed file
git add README.md

# Complete the merge
git commit -m "Resolve merge conflict in README.md"
```

---

## 🚫 How to Abort a Merge

If you get into a conflict and want to go back to where you started:

```bash
git merge --abort
```

This cancels the merge and restores your branch to how it was before.

---

## 🌟 How to Prevent Conflicts

| Practice | Why it helps |
|----------|-------------|
| Pull from `main` frequently | Keeps your branch up to date |
| Work on separate files/sections | Avoids overlapping changes |
| Communicate with your team | Avoid two people editing the same lines |
| Make small, focused commits | Easier to track and merge |
| Use short-lived branches | Less drift from `main` |

---

## 🧪 Practice Exercise

1. Create two branches from `main`: `branch-a` and `branch-b`
2. Edit the **same line** in `practice-file.md` in both branches
3. Merge `branch-a` into `main`, then try to merge `branch-b`
4. Resolve the conflict that appears
5. Complete the merge with a commit message

---

## 📚 Further Reading

- [GitHub Docs — Resolving a merge conflict](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line)
- [VS Code — Merge conflict editor](https://code.visualstudio.com/docs/sourcecontrol/overview#_merge-conflicts)

---

> ⬅️ Back to [README](../README.md) | ➡️ Next: [Undoing Changes](undoing-changes.md)

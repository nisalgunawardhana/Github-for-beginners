## Step-by-Step Git Practice Guide

### 1. **Initialize Git **
```bash
git init
```

### 2. **Create and Switch to Your Practice Branch**
```bash
# Create a new branch
git branch practice/reezma-java-tips

# Switch to that branch
git checkout practice/reezma-java-tips

# Or do both in one command
git checkout -b practice/reezma-java-tips
```

### 3. **Make Your First Set of Changes**

Add your "My Contribution" section if you haven't already, and maybe add a Java code snippet:

```markdown
Java Code Snippet:
```java
// Simple Java program example
public class GitPractice {
    public static void main(String[] args) {
        System.out.println("Learning Git with Java!");
    }
}
```


### 4. **Stage and Commit - Challenge 1: Multiple Commits**

**Commit 1:**
```bash
git add "📝 Practice File for Git Exercises.md"
git commit -m "Add Java section with language description"
```

**Commit 2:** (Add a Java tip in the Tips section)
```bash
git add "📝 Practice File for Git Exercises.md"
git commit -m "Add Java best practices tip"
```

**Commit 3:** (Update the Last updated date and add your tip)
```bash
git add "📝 Practice File for Git Exercises.md"
git commit -m "Update last modified date and add personal Git tip"
```

### 5. **Practice Git Status and Log Commands**
```bash
# Check the state of your working directory
git status

# View your commit history
git log
git log --oneline  # Compact view
git log --graph    # Visual view
```

### 6. **Push Your Branch to GitHub**
```bash
# First, add your remote repository 
git remote add origin https://github.com/yourusername/your-repo.git

# Push your branch
git push -u origin practice/reezma-java-tips
```

### 7. **Create a Pull Request**
- Go to your repository on GitHub
- You'll see a yellow banner showing your recently pushed branch
- Click "Compare & pull request"
- Add a title: "Add Java section with tips and examples"
- Add a description explaining your changes
- Click "Create pull request"

### Additional Git Commands to Practice:

```bash
# See the differences before staging
git diff

# See only staged changes
git diff --staged

# Undo staging a file
git reset HEAD "📝 Practice File for Git Exercises.md"

# Amend your last commit (if you forgot something)
git commit --amend -m "Better commit message"

# View branches
git branch
git branch -a  # See all branches including remote

# Fetch latest changes
git fetch origin

# Pull changes from main branch
git checkout main
git pull origin main
```

### For Your "Commands I want to learn" Section:

**Practice git stash:**
```bash
# Save work in progress
git stash save "WIP: working on Java section"

# List stashes
git stash list

# Apply most recent stash
git stash apply

# Apply and drop
git stash pop
```

**Practice git merge:**
```bash
# Switch to main branch
git checkout main

# Merge your practice branch
git merge practice/reezma-java-tips
```

Keep practicing! The more you use Git, the more comfortable you'll become. 🌟

Last updated: 13 feb 2026

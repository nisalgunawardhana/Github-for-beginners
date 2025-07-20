# 🚀 GitHub Workflow Practice Repository

Welcome to the **GitHub for Beginners** practice repository! This repo is designed to help you learn and practice essential GitHub workflows including forking, cloning, branching, committing, pushing, and creating pull requests.

[![Follow me on GitHub](https://img.shields.io/github/followers/nisalgunawardhana?label=Follow&style=social)](https://github.com/nisalgunawardhana)
[![Star this repo](https://img.shields.io/github/stars/nisalgunawardhana/Github-for-beginners?style=social)](https://github.com/nisalgunawardhana/Github-for-beginners/stargazers)
## 📋 What You'll Learn

- ✅ Fork a repository
- ✅ Clone a repository to your local machine
- ✅ Create and switch between branches
- ✅ Make changes to files
- ✅ Stage and commit changes
- ✅ Push changes to GitHub
- ✅ Create Pull Requests
- ✅ Work with Issues
- ✅ Basic Git commands and GitHub workflow

## 🎯 Getting Started

### Step 1: Fork This Repository
1. Click the **"Fork"** button at the top right of this repository
2. This creates a copy of the repository in your GitHub account

### Step 2: Clone Your Fork
```bash
# Replace 'your-username' with your actual GitHub username
git clone https://github.com/your-username/Github-for-beginners.git

# Navigate to the project directory
cd Github-for-beginners
```
> 💡 **Tip:** To open the project in VS Code from your terminal, run:
> 
> ```bash
> code .
> ```
> Make sure you have the [VS Code command line tool](https://code.visualstudio.com/docs/editor/command-line) installed.

## 🌿 Branch Practice Exercises

### Exercise 1: Create Your First Branch
```bash
# Create and switch to a new branch with your name
git checkout -b feature/your-name-introduction

# Or alternatively
git branch feature/your-name-introduction
git checkout feature/your-name-introduction
```

### Exercise 2: Make Your First Changes
1. Open the `student-introductions.md` file
2. Add your introduction following the template
3. Save the file

### Exercise 3: Stage and Commit Changes
```bash
# Check what files have changed
git status

# Add your changes to staging
git add student-introductions.md

# Or add all changes
git add .

# Commit your changes with a descriptive message
git commit -m "Add introduction for [Your Name]"
```

### Exercise 4: Push Your Branch
```bash
# Push your branch to your fork
git push origin feature/your-name-introduction
```

### Exercise 5: Create a Pull Request
1. Go to your fork on GitHub
2. You'll see a prompt to create a Pull Request
3. Click **"Compare & pull request"**
4. Add a title and description
5. Click **"Create pull request"**

## 📝 Practice Exercises

### Beginner Level
- [ ] Fork and clone this repository
- [ ] Create a branch named `add-your-name`
- [ ] Add your name to the `student-introductions.md` file
- [ ] Commit and push your changes
- [ ] Create a pull request

### Intermediate Level
- [ ] Create a branch named `feature/add-new-section`
- [ ] Add a new section to the `practice-file.md`
- [ ] Create multiple commits for your changes
- [ ] Push and create a pull request
- [ ] Create an issue for a new feature suggestion

### Advanced Level
- [ ] Practice resolving merge conflicts
- [ ] Rebase your branch on the latest main
- [ ] Squash multiple commits into one
- [ ] Review someone else's pull request

## 🐛 Working with Issues

### Creating an Issue
1. Go to the **Issues** tab
2. Click **"New issue"**
3. Choose from our templates:
   - Bug Report
   - Feature Request
   - Question
   - Submission Review

### Issue Best Practices
- Use descriptive titles
- Provide detailed descriptions
- Add relevant labels
- Reference related issues or PRs using #number

## 🔄 Common Git Commands Reference

### Basic Commands
```bash
# Check repository status
git status

# View commit history
git log --oneline

# Check current branch
git branch

# Switch branches
git checkout branch-name

# Create and switch to new branch
git checkout -b new-branch-name

# Delete a branch
git branch -d branch-name
```

### Working with Changes
```bash
# Add specific files
git add filename.txt

# Add all changes
git add .

# Commit with message
git commit -m "Your commit message"

# Add and commit in one step
git commit -am "Your commit message"
```

### Synchronizing with Remote
```bash
# Push changes
git push origin branch-name

# Pull latest changes
git pull origin main

# Fetch updates without merging
git fetch upstream
```

## 🏆 Submission Guidelines

When you complete the exercises:

1. **Move to the main repository (original one)** by switching your remote to the upstream/main repo if needed.
2. **Create an issue on that branch** using the "Submission Review" template.
3. **Include the following information:**
    - Your GitHub username
    - Links to your pull requests
    - Screenshot of your contribution
    - Brief reflection on what you learned

## 📋 Checklist for Completion

- [ ] Successfully forked the repository
- [ ] Cloned to local machine
- [ ] Created at least 2 different branches
- [ ] Made commits with good commit messages
- [ ] Pushed branches to GitHub
- [ ] Created at least 1 pull request
- [ ] Created at least 1 issue on the main repository
- [ ] Added your introduction to the student introductions file

## 🤝 Contributing

This is a learning repository, and contributions are welcome! If you have suggestions for improvement:

1. Create an issue to discuss your idea
2. Fork the repository
3. Create a feature branch
4. Make your changes
5. Submit a pull request

## 📚 Additional Resources

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Interactive Git Tutorial](https://learngitbranching.js.org/)
- [GitHub Flow](https://guides.github.com/introduction/flow/)

## 📞 Need Help?

- Create an issue with the "Question" template
- Check existing issues for similar questions
- Review the documentation links above

## ⚖️ License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🌐 Connect with Me

Follow me on social media for updates and more learning resources:

[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?logo=twitter&logoColor=white&style=for-the-badge)](https://twitter.com/thenisals)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?logo=linkedin&logoColor=white&style=for-the-badge)](https://linkedin.com/in/nisalgunawardhana)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?logo=instagram&logoColor=white&style=for-the-badge)](https://instagram.com/thenisals)

**Happy Learning! 🎉**

Remember: Making mistakes is part of learning. Don't be afraid to experiment and try new things!

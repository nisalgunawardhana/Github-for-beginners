## ⚠️ Git Configuration Error (First-Time Setup)

When using Git for the first time on Windows, you may see the following error:


### ❌ Error
![Git Error](/images/error1.png)

### ✅ Reason
Git requires a **user name** and **email** to identify commits. These are not set by default.

### 🔧 Solution
Run the following commands in Git Bash or Command Prompt:

```bash
git config --global user.name "Your Name"

```

or

```bash
git config --global user.email "youremail@example.com"
```



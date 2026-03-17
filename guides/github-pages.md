# 🌐 Deploying with GitHub Pages

GitHub Pages lets you host a website **for free** directly from a GitHub repository. No server setup, no hosting fees — just push your files and your site is live.

---

## 📖 What is GitHub Pages?

GitHub Pages is a static site hosting service that reads HTML, CSS, and JavaScript files directly from a GitHub repository and publishes them as a website.

### What you can host:
- Personal portfolio websites
- Project documentation
- Simple HTML/CSS/JS sites
- Blogs (with Jekyll)
- Landing pages

### What GitHub Pages is **not** for:
- Sites with a backend / server-side code (PHP, Node.js, Python, etc.)
- Sites with databases
- High-traffic commercial applications

---

## 🌍 Types of GitHub Pages Sites

| Type | URL Format | How to enable |
|------|-----------|---------------|
| User site | `username.github.io` | Repo named `username.github.io` |
| Organization site | `orgname.github.io` | Repo named `orgname.github.io` |
| Project site | `username.github.io/repo-name` | Any repo, from any branch/folder |

---

## 🚀 Method 1: Deploy from a Branch (Easiest)

### Step 1: Create or use an existing repository

Make sure your repository has an `index.html` file at the root (or in a `/docs` folder).

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First GitHub Pages Site</title>
</head>
<body>
    <h1>Hello, GitHub Pages! 🎉</h1>
    <p>My first website hosted on GitHub.</p>
</body>
</html>
```

### Step 2: Enable GitHub Pages
1. Go to your repository on GitHub
2. Click **Settings** (top navigation)
3. Scroll down to **Pages** in the left sidebar
4. Under **Source**, select your branch (e.g., `main`)
5. Choose the folder: **/ (root)** or **/docs**
6. Click **Save**

### Step 3: Visit your site
After a minute or two, your site will be live at:
```
https://your-username.github.io/your-repo-name/
```

> 💡 GitHub will show you the URL at the top of the Pages settings page.

---

## 🚀 Method 2: Create a Personal Portfolio Site (username.github.io)

This creates your main site at `https://your-username.github.io`.

### Step 1: Create the special repo
1. Create a new repository named exactly: `your-username.github.io`
   - Example: if your username is `johndoe`, name it `johndoe.github.io`
2. Make it **Public**

### Step 2: Add your site files
```bash
# Clone the repo
git clone https://github.com/your-username/your-username.github.io.git
cd your-username.github.io

# Create your home page
echo "<h1>Hello World!</h1>" > index.html

# Push to GitHub
git add .
git commit -m "Initial site"
git push origin main
```

### Step 3: Visit your live site
Your site is automatically published at:
```
https://your-username.github.io
```

---

## 📁 Recommended Project Structure

```
my-portfolio/
├── index.html          ← Main page (required)
├── about.html          ← About page
├── projects.html       ← Projects page
├── css/
│   └── style.css
├── js/
│   └── main.js
└── images/
    └── profile.jpg
```

---

## 🔄 Updating Your Site

Every time you push a commit to the deployed branch, GitHub Pages automatically rebuilds and redeploys your site.

```bash
# Make a change to index.html, then:
git add index.html
git commit -m "Update homepage content"
git push origin main
# Wait ~1 minute for GitHub to redeploy
```

---

## ✅ Deploying from a `/docs` Folder

A common approach is to keep source files in root but put publishable files in `/docs`:

```
my-project/
├── src/             ← source code
├── docs/            ← what GitHub Pages serves
│   ├── index.html
│   └── style.css
└── README.md
```

Then in Settings → Pages, set the source folder to `/docs`.

---

## 🎨 Adding a Theme with Jekyll

GitHub Pages supports [Jekyll](https://jekyllrb.com/), a static site generator. You can add a theme to a plain markdown site with a single config file:

### Step 1: Create `_config.yml` in your repo root
```yaml
theme: minima
title: My GitHub Pages Site
description: Learning GitHub Pages
```

### Available themes (no extra setup needed):
- `minima`
- `cayman`
- `slate`
- `midnight`
- `architect`
- `tactile`

---

## 🌐 Custom Domain (Optional)

You can use your own domain (e.g., `www.yourname.com`) with GitHub Pages:

1. Buy a domain from a registrar (e.g., Namecheap, GoDaddy)
2. In your repo, create a file called `CNAME` with your domain:
   ```
   www.yourname.com
   ```
3. In your domain registrar's DNS settings, add a CNAME record pointing to `your-username.github.io`
4. In Settings → Pages, enter your custom domain and enable **Enforce HTTPS**

---

## 🔍 Troubleshooting

| Problem | Solution |
|---------|----------|
| Site shows 404 | Make sure `index.html` exists at the root (or `/docs`) |
| Changes not showing | Wait 1-2 minutes; clear browser cache |
| Pages not enabled | Check Settings → Pages → ensure source branch is set |
| CSS/JS not loading | Check file paths — use relative paths |
| Build failed | Check the Actions tab for error logs |

---

## 🧪 Practice Exercise

1. Create a new public repo called `my-first-site`
2. Add an `index.html` with your name and a welcome message
3. Add a `style.css` and link it — give the page a background color
4. Enable GitHub Pages from the `main` branch
5. Share your live link with someone!

**Bonus:** Add a second page (`about.html`) and link it from your homepage.

---

## 📚 Further Reading

- [GitHub Docs — GitHub Pages](https://docs.github.com/en/pages)
- [GitHub Pages Examples](https://github.com/collections/github-pages-examples)
- [Jekyll Docs](https://jekyllrb.com/docs/)

---

> ⬅️ Back to [README](../README.md) | 📖 Also see: [GitHub Profile README](github-profile-readme.md)

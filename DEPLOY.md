# Deploy Your Portfolio with Git (GitHub Pages)

Your portfolio is set up to deploy automatically when you push to GitHub.

---

## Step-by-step: Deploy to GitHub Pages

### 1. Create a GitHub repository

1. Go to [github.com/new](https://github.com/new)
2. Name it (e.g. `qa-portfolio` or `agilesh-portfolio`)
3. Choose **Public**
4. **Do not** add README, .gitignore, or license (we already have these)
5. Click **Create repository**

### 2. Push your portfolio

Open Terminal/PowerShell in this folder and run:

```bash
cd d:\portfolio

git init
git add .
git commit -m "QA Portfolio 2026"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
git push -u origin main
```

Replace `YOUR_USERNAME` and `REPO_NAME` with your GitHub username and repo name.

### 3. Enable GitHub Pages

1. In your repo on GitHub, go to **Settings** → **Pages**
2. Under **Build and deployment** → **Source**, select **GitHub Actions**
3. Save (the workflow will run automatically)

### 4. Your live URL

After the workflow runs (about 1–2 minutes), your site will be at:

**`https://YOUR_USERNAME.github.io/REPO_NAME/`**

Example: If your repo is `agilesh-qa/qa-portfolio`, the URL is:  
`https://agilesh-qa.github.io/qa-portfolio/`

---

## After setup

Each time you push to `main`, the site will redeploy automatically:

```bash
git add .
git commit -m "Update portfolio"
git push
```

---

## Other deploy options

- **Netlify Drop**: [app.netlify.com/drop](https://app.netlify.com/drop) – drag folder for instant URL
- **Vercel**: [vercel.com](https://vercel.com) – import this repo for automatic deploys

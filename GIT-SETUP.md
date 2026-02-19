# Step-by-Step: Upload Portfolio to GitHub and Maintain It

Follow these steps in order. Use **PowerShell** or **Command Prompt** (or Git Bash).

---

## Part 1: One-Time Setup

### Step 1: Install Git (if you don’t have it)

1. Download: [https://git-scm.com/download/win](https://git-scm.com/download/win)
2. Run the installer and use the default options.
3. Close and reopen your terminal. Check:
   ```bash
   git --version
   ```
   You should see something like `git version 2.x.x`.

---

### Step 2: Configure Git with your name and email (one time per PC)

Replace with your real name and the email you use on GitHub:

```bash
git config --global user.name "Agilesh D"
git config --global user.email "agileshd115@gmail.com"
```

---

### Step 3: Create a GitHub account and a new repository

1. Go to [https://github.com](https://github.com) and sign up or log in.
2. Click the **+** (top right) → **New repository**.
3. Fill in:
   - **Repository name:** `qa-portfolio` (or any name you like)
   - **Description:** (optional) e.g. `QA Portfolio 2026`
   - **Public**
   - Leave **Add a README**, **.gitignore**, and **license** unchecked.
4. Click **Create repository**.
5. Keep the page open; you’ll need the repository URL (e.g. `https://github.com/agileshdeva-05/qa-portfolio.git`).

---

### Step 4: Initialize Git in your portfolio folder and push

Open PowerShell or Command Prompt and run these commands **one by one**.  
Replace `YOUR_USERNAME` and `qa-portfolio` with your GitHub username and repo name if different.

```bash
cd d:\portfolio
```

```bash
git init
```

```bash
git add .
```

```bash
git status
```
(You should see all your files listed. This is optional but good to check.)

```bash
git commit -m "Initial commit - QA Portfolio 2026"
```

```bash
git branch -M main
```

```bash
git remote add origin https://github.com/Agileshdeva/ProtfolioAD.git
```

```bash
git push -u origin main
```

- If asked to sign in, use your GitHub username and a **Personal Access Token** (not your password).  
- To create a token: GitHub → **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)** → **Generate new token**. Give it a name, check **repo**, then generate and copy the token. Use it as the password when `git push` asks.

After this, your portfolio code is on GitHub.

---

## Part 2: Enable GitHub Pages (so you get a URL)

1. On GitHub, open your repository (e.g. `qa-portfolio`).
2. Click **Settings** → in the left sidebar click **Pages**.
3. Under **Build and deployment** → **Source**, choose **GitHub Actions**.
4. Save. The first deployment may take 1–2 minutes.
5. Your site URL will be:  
   **`https://agileshdeva.github.io/ProtfolioAD/`**

---

## Part 3: Maintain the Portfolio (when you make changes)

Whenever you change files in `d:\portfolio` (e.g. in Cursor), do this to update GitHub and the live site:

### Step 5: Open terminal in the portfolio folder

```bash
cd d:\portfolio
```

### Step 6: See what changed

```bash
git status
```

### Step 7: Stage all changes

```bash
git add .
```

(To stage one file: `git add index.html`)

### Step 8: Commit with a short message

```bash
git commit -m "Update about section"
```
Use a message that describes the change (e.g. “Add new project”, “Fix contact link”).

### Step 9: Push to GitHub

```bash
git push
```

After the push, GitHub Actions will redeploy your site in 1–2 minutes. No need to run anything else.

---

## Quick reference: daily workflow

| What you do | Commands |
|-------------|----------|
| Made edits and want to update the site | `cd d:\portfolio` → `git add .` → `git commit -m "Your message"` → `git push` |
| Check if you have uncommitted changes | `cd d:\portfolio` → `git status` |
| See your commit history | `git log --oneline` |

---

## Troubleshooting

**“remote origin already exists”**  
- You already added the remote. Use:  
  `git remote set-url origin https://github.com/Agileshdeva/ProtfolioAD.git`  
  then `git push -u origin main` again.

**“Authentication failed” or “Support for password authentication was removed”**  
- Use a **Personal Access Token** instead of your GitHub password when `git push` asks for a password. Create one: GitHub → Settings → Developer settings → Personal access tokens.

**“Failed to push” / “rejected”**  
- Your repo already has a README. Run:  
  `git pull origin main --allow-unrelated-histories`  
  (Save and close the merge editor if it opens.)  
  Then: `git push -u origin main`

**Site not updating**  
- Wait 1–2 minutes after `git push`.  
- Check: Repo → **Actions** tab. The latest workflow run should be green (success).

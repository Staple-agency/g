# STAPLE Website - Deployment Guide

This guide will help you deploy your STAPLE website to GitHub Pages.

## Prerequisites

- A GitHub account ([Sign up here](https://github.com/join))
- Git installed on your computer ([Download here](https://git-scm.com/downloads))
- Basic command line knowledge

---

## Step-by-Step Deployment

### 1. Create a GitHub Repository

1. Log into your GitHub account
2. Click the **+** icon in the top right corner
3. Select **New repository**
4. Repository settings:
   - **Name**: `staple-website` (or your preferred name)
   - **Description**: "STAPLE Digital Agency Website"
   - **Visibility**: Public (required for free GitHub Pages)
   - **DO NOT** check "Initialize with README"
5. Click **Create repository**

### 2. Prepare Your Local Files

Open Terminal (Mac/Linux) or Command Prompt (Windows) and navigate to the folder containing your website files:

```bash
cd /path/to/your/website/files
```

### 3. Initialize Git Repository

```bash
# Initialize a new Git repository
git init

# Add all files to staging
git add .

# Create your first commit
git commit -m "Initial commit: STAPLE Digital Agency website"
```

### 4. Connect to GitHub

Replace `YOUR-USERNAME` and `staple-website` with your actual GitHub username and repository name:

```bash
# Add GitHub repository as remote
git remote add origin https://github.com/YOUR-USERNAME/staple-website.git

# Rename branch to main (GitHub's default)
git branch -M main

# Push to GitHub
git push -u origin main
```

**Note**: If prompted, enter your GitHub credentials. If you have 2FA enabled, you may need to use a [Personal Access Token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) instead of your password.

### 5. Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/YOUR-USERNAME/staple-website`
2. Click **Settings** (tab at the top)
3. Scroll down and click **Pages** in the left sidebar
4. Under **Source**:
   - Select **Deploy from a branch**
   - Choose **main** branch
   - Select **/ (root)** folder
5. Click **Save**
6. Wait 1-2 minutes for deployment

### 6. Access Your Website

Your website will be live at:
```
https://YOUR-USERNAME.github.io/staple-website/
```

The URL will also appear in a green banner on the Pages settings page.

---

## Making Updates

After making changes to your website:

```bash
# Check what files changed
git status

# Add all changed files
git add .

# Commit with a descriptive message
git commit -m "Updated contact information"

# Push to GitHub
git push
```

GitHub Pages will automatically rebuild and update your site within 1-2 minutes.

---

## Custom Domain Setup (Optional)

### If you want to use your own domain (e.g., www.stapleagency.com):

#### A. Configure DNS with Your Domain Provider

Add one of these configurations:

**Option 1: CNAME Record (Recommended for www subdomain)**
```
Type: CNAME
Host: www
Value: YOUR-USERNAME.github.io
TTL: 3600
```

**Option 2: A Records (For apex/root domain)**
```
Type: A
Host: @
Value: 185.199.108.153
TTL: 3600

Type: A
Host: @
Value: 185.199.109.153
TTL: 3600

Type: A
Host: @
Value: 185.199.110.153
TTL: 3600

Type: A
Host: @
Value: 185.199.111.153
TTL: 3600
```

#### B. Add CNAME File to Repository

1. Rename `CNAME.example` to `CNAME`
2. Edit the file to contain only your domain:
   ```
   www.stapleagency.com
   ```
3. Commit and push:
   ```bash
   git add CNAME
   git commit -m "Add custom domain"
   git push
   ```

#### C. Configure in GitHub

1. Go to repository **Settings** → **Pages**
2. Under **Custom domain**, enter your domain
3. Click **Save**
4. Wait for DNS check (green checkmark)
5. Enable **Enforce HTTPS** once available

**Note**: DNS propagation can take 24-48 hours.

---

## Troubleshooting

### Website Not Loading

1. Check GitHub Pages is enabled in Settings
2. Ensure you pushed to the `main` branch
3. Check repository is public
4. Wait a few minutes after pushing changes

### 404 Error

1. Verify `index.html` is in the root of your repository
2. Check file names are correct (case-sensitive)
3. Try clearing browser cache

### Changes Not Appearing

1. Wait 1-2 minutes after pushing
2. Hard refresh: `Ctrl+Shift+R` (Windows/Linux) or `Cmd+Shift+R` (Mac)
3. Clear browser cache
4. Check Actions tab on GitHub for build status

### Custom Domain Not Working

1. Verify DNS settings with your provider
2. Use [DNS Checker](https://dnschecker.org) to verify propagation
3. Ensure CNAME file contains only the domain (no http://)
4. Wait up to 48 hours for DNS propagation

---

## Useful Commands

```bash
# Check repository status
git status

# View commit history
git log --oneline

# Undo uncommitted changes
git checkout -- filename.html

# View remote repository URL
git remote -v

# Pull latest changes from GitHub
git pull

# Create a new branch
git checkout -b feature-name

# Switch between branches
git checkout main
```

---

## Best Practices

1. **Commit Often**: Make small, frequent commits with clear messages
2. **Test Locally**: Preview changes before pushing
3. **Backup**: Keep a local backup of your files
4. **Descriptive Messages**: Use clear commit messages like "Updated team photos" instead of "changes"
5. **Version Control**: Use branches for major changes

---

## Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Git Basics Tutorial](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)
- [Markdown Guide](https://www.markdownguide.org/) (for editing README)
- [GitHub CLI](https://cli.github.com/) (alternative to command line Git)

---

## Support

If you encounter issues:

1. Check the [GitHub Pages Status](https://www.githubstatus.com/)
2. Search [GitHub Community](https://github.community/)
3. Review [GitHub Pages Documentation](https://docs.github.com/en/pages)
4. Contact STAPLE team: staple.enquiry@gmail.com

---

**Congratulations! Your STAPLE website is now live! 🎉**

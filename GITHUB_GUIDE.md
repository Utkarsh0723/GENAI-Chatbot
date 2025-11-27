# How to Push Your Chatbot to GitHub

## Prerequisites
1. **GitHub Account**: Make sure you have a GitHub account at https://github.com
2. **Git Installed**: Check if Git is installed by running:
   ```bash
   git --version
   ```
   If not installed, download from: https://git-scm.com/downloads

---

## Step-by-Step Guide

### Step 1: Initialize Git Repository (if not already done)
```bash
cd C:\Users\tripa\OneDrive\Desktop\chatbot
git init
```

### Step 2: Add All Files to Git
```bash
git add .
```

### Step 3: Create Your First Commit
```bash
git commit -m "Initial commit: GenAI Chatbot with React, FastAPI, and Groq"
```

### Step 4: Create a New Repository on GitHub
1. Go to https://github.com/new
2. Repository name: `genai-chatbot` (or any name you prefer)
3. Description: "AI-powered chatbot with PDF RAG capabilities using React, FastAPI, and Groq"
4. Choose **Public** or **Private**
5. **DO NOT** check "Initialize with README" (we already have one)
6. Click **Create repository**

### Step 5: Connect Your Local Repo to GitHub
Replace `YOUR_USERNAME` with your actual GitHub username:
```bash
git remote add origin https://github.com/YOUR_USERNAME/genai-chatbot.git
```

### Step 6: Push to GitHub
```bash
git branch -M main
git push -u origin main
```

---

## If You Get Authentication Errors

### Option 1: Use Personal Access Token (Recommended)
1. Go to GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Click "Generate new token (classic)"
3. Give it a name like "Chatbot Project"
4. Select scopes: `repo` (full control)
5. Click "Generate token"
6. **Copy the token** (you won't see it again!)
7. When pushing, use:
   ```bash
   git push -u origin main
   ```
   - Username: Your GitHub username
   - Password: Paste the token (not your GitHub password)

### Option 2: Use GitHub CLI
```bash
# Install GitHub CLI from https://cli.github.com/
gh auth login
gh repo create genai-chatbot --public --source=. --remote=origin --push
```

---

## Future Updates

After making changes to your code:
```bash
git add .
git commit -m "Description of changes"
git push
```

---

## Important Notes

✅ **Your `.env` file is protected** - It's in `.gitignore`, so your API key won't be uploaded
✅ **Virtual environment is excluded** - `venv/` won't be uploaded (saves space)
✅ **Node modules are excluded** - `node_modules/` won't be uploaded

⚠️ **Remember to update README.md** with setup instructions for others who clone your repo!

---

## Quick Commands Reference

```bash
# Check status
git status

# See what changed
git diff

# View commit history
git log --oneline

# Create a new branch
git checkout -b feature-name

# Switch branches
git checkout main
```

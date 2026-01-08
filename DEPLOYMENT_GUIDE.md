# Deployment Guide - Step by Step

Follow these steps to deploy your MLS vs CAMA Comparison Tool to Streamlit Cloud.

## Prerequisites

- A GitHub account (free)
- A Streamlit Cloud account (free) - sign up at https://streamlit.io/cloud

## Step 1: Upload Files to GitHub

### Option A: Using GitHub Web Interface (Easiest)

1. Go to [GitHub](https://github.com) and sign in
2. Click the "+" icon in the top right corner
3. Select "New repository"
4. Fill in the details:
   - Repository name: `mls-cama-comparison` (or your preferred name)
   - Description: "MLS vs CAMA property data comparison tool"
   - Select "Public" (required for free Streamlit hosting)
   - Check "Add a README file"
5. Click "Create repository"

6. **Upload your files**:
   - Click "Add file" → "Upload files"
   - Drag and drop these files:
     - `streamlit_app.py`
     - `requirements.txt`
     - `mls_cama_comparison.py` (optional)
     - `.gitignore`
   - Commit the changes

7. **Create .streamlit folder**:
   - Click "Add file" → "Create new file"
   - Name it: `.streamlit/config.toml`
   - Paste the contents from your config.toml file
   - Click "Commit new file"

### Option B: Using Git Command Line

```bash
# Navigate to your project folder
cd /path/to/your/project

# Initialize git (if not already done)
git init

# Add all files
git add .

# Commit files
git commit -m "Initial commit - MLS CAMA Comparison Tool"

# Create repository on GitHub, then link it:
git remote add origin https://github.com/YOUR_USERNAME/mls-cama-comparison.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Step 2: Deploy to Streamlit Cloud

1. **Go to Streamlit Cloud**:
   - Visit https://streamlit.io/cloud
   - Click "Sign in" and sign in with GitHub

2. **Create New App**:
   - Click "New app" button
   - Select "From existing repo"

3. **Configure Your App**:
   - **Repository**: Select your repository (e.g., `YOUR_USERNAME/mls-cama-comparison`)
   - **Branch**: `main`
   - **Main file path**: `streamlit_app.py`
   - **App URL**: Choose a custom subdomain (optional)

4. **Advanced Settings** (click to expand):
   - Python version: 3.11 (recommended)
   - Leave other settings as default

5. **Click "Deploy"**:
   - Wait 2-5 minutes for deployment
   - You'll see build logs in real-time

6. **App is Live!**:
   - Once deployed, you'll get a URL like: `https://YOUR_APP_NAME.streamlit.app`
   - Share this URL with your team

## Step 3: Test Your App

1. Visit your app URL
2. Upload sample MLS and CAMA files
3. Verify the comparison runs correctly
4. Test downloading the Excel reports
5. Check that hyperlinks work in the downloaded files

## Updating Your App

When you make changes:

### Option A: GitHub Web Interface
1. Navigate to the file on GitHub
2. Click the pencil icon to edit
3. Make changes
4. Commit changes
5. Streamlit will auto-deploy (takes 1-2 minutes)

### Option B: Git Command Line
```bash
# Make your changes to files locally

# Add and commit
git add .
git commit -m "Description of changes"

# Push to GitHub
git push origin main

# Streamlit will automatically redeploy
```

## Troubleshooting Deployment

### "App failed to build"
- Check the logs in Streamlit Cloud
- Verify all files are in the repository
- Ensure `requirements.txt` is correct

### "Module not found" errors
- Add missing package to `requirements.txt`
- Redeploy the app

### App is slow
- Check file upload sizes (max 200MB per file)
- Consider optimizing your data processing

### Can't find my repository
- Make sure repository is public (not private)
- Check that you're signed in with the correct GitHub account

## Repository Structure

Your GitHub repository should look like this:

```
mls-cama-comparison/
├── .streamlit/
│   └── config.toml
├── streamlit_app.py
├── requirements.txt
├── mls_cama_comparison.py (optional)
├── .gitignore
└── README.md
```

## Security Notes

⚠️ **Important**: 
- Don't commit actual MLS or CAMA data files to GitHub
- Don't commit any passwords or API keys
- The `.gitignore` file prevents accidental commits of data files

## Support Resources

- [Streamlit Documentation](https://docs.streamlit.io)
- [Streamlit Community Forum](https://discuss.streamlit.io)
- [GitHub Guides](https://guides.github.com)

## Next Steps

1. ✅ Deploy your app
2. ✅ Test with sample data
3. ✅ Share the URL with your team
4. ✅ Gather feedback and iterate

## Need Help?

If you run into issues:
1. Check the deployment logs in Streamlit Cloud
2. Review this guide carefully
3. Search the Streamlit forum
4. Open an issue on your GitHub repository

---

**Congratulations!** Your MLS vs CAMA Comparison Tool is now live on the web! 🎉

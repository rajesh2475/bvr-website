# BVR International CBSE School — Quick Hosting Guide

This repository is a small static website (HTML + CSS). The easiest way to make it publicly reachable for validation is to deploy to a free static-hosting service. Below are step-by-step options and exact PowerShell commands you can run locally.

## Option A — GitHub Pages (recommended)
- Create a GitHub repository and push this folder. You can then enable GitHub Pages to serve the site from the `main` branch (root).

Quick commands (PowerShell):

```powershell
# initialize local repo (if not already initialized)
git init
git add .
git commit -m "Initial commit — website"

# Create a remote repo on GitHub using gh (optional; install GitHub CLI)
# Replace <your-repo-name> with a name you prefer
gh repo create <your-repo-name> --public --source=. --push

# If you created the repo manually, add the remote and push:
# git remote add origin https://github.com/<your-username>/<your-repo-name>.git
# git branch -M main
# git push -u origin main
```

After pushing: go to the repository Settings → Pages → select `Branch: main` and `Folder: / (root)`, then save. GitHub will provide a `https://<your-username>.github.io/<your-repo-name>/` URL. If you create a repository named exactly `your-username.github.io` it will be published at `https://your-username.github.io/`.

Notes:
- No build step is required. Files at the repository root (like `index.html`) are served directly.
- If you want a bare-root site (no repo name in the URL), name the repository `your-username.github.io`.

## Option B — Netlify (very quick)
- Sign up at https://app.netlify.com. You can drag-and-drop the site folder to Netlify Drop, or connect a GitHub repo for continuous deploy.
- Netlify gives a free `*.netlify.app` subdomain (e.g., `hungry-lalande-12345.netlify.app`).

Steps (drag-and-drop):
1. Zip the repository (or select the folder).
2. Go to Netlify Drop: https://app.netlify.com/drop and drop the folder.
3. Netlify returns a URL immediately.

Or connect your GitHub repo for automatic deploys on push.

## Option C — Vercel / Cloudflare Pages
- Both services can connect to your GitHub repo and provide free hosting with auto-deploy on push.
- Vercel gives quick previews and a `vercel.app` domain. Cloudflare Pages gives a `pages.dev` domain.

## Other useful tips
- If you add images, place them under `images/` and reference with relative paths (e.g. `images/photo.jpg`).
- If you want a custom domain, you can configure DNS for GitHub Pages / Netlify / Vercel — most providers offer step-by-step guides.

---
If you want, I can:
- initialize the git repository locally and create the first commit, or
- run `gh repo create` for you (I will prompt for confirmation first), or
- prepare a ZIP suitable for Netlify Drop and show a quick upload command.

Tell me which option you prefer and whether you'd like me to run the local git commands now.

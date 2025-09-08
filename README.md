GitHub Pages deployment
=======================

This repository contains a static website (HTML/CSS/JS) that can be hosted using GitHub Pages.

Quick steps to publish from Windows PowerShell:

1. Initialize git (if not already):

   git init

2. Create a repository on GitHub (via website) and copy the remote URL (HTTPS or SSH).

3. Add, commit, and push to the `main` branch (or `gh-pages` if you prefer):

   git add .
   git commit -m "Initial site upload"
   git branch -M main
   git remote add origin <REMOTE_URL>
   git push -u origin main

4. Enable GitHub Pages:

- Go to the repository Settings → Pages.
- Choose branch `main` and folder `/ (root)` then Save.

Alternative: Use the included GitHub Action to automatically build and deploy to `gh-pages` branch. The Action will publish the repository root to the `gh-pages` branch when you push to `main`.

Notes:
- If you want a custom domain, add a file named `CNAME` to the repo root containing your domain and configure DNS accordingly. See the last section of this README for details.

Custom domain (quick):

- Put your domain (e.g. `www.example.com`) in the file named `CNAME` at the repository root and commit it.
- In your DNS provider, create a CNAME record for the record you want (e.g. `www`) pointing to `<your-github-username>.github.io`, or A records to GitHub Pages IPs for apex domains. See GitHub Pages docs for exact IPs.
- In the repository Settings → Pages, verify the custom domain is shown and enforce HTTPS after DNS propagates.

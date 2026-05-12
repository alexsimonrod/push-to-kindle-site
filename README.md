# push-to-kindle-site

Public static site for **Push-to-Kindle** OAuth branding: privacy policy and a minimal home page.

Built with [GitHub Pages](https://pages.github.com/) from the `/docs` folder.

After enabling **Settings → Pages → /docs** on this repository, the site URL will be:

`https://alexsimonrod.github.io/push-to-kindle-site/`

(Replace `alexsimonrod` / `push-to-kindle-site` if this repo is under another owner or name.)

## Connect remote (if you cloned or copied this folder)

```bash
cd ~/Documents/push-to-kindle-site
git remote add origin https://github.com/<OWNER>/<REPO>.git
git push -u origin main
git push -u origin feat/github-pages-docs
gh pr create --base main --head feat/github-pages-docs --title "Add GitHub Pages docs" --body "Privacy policy and home page for Google OAuth consent screen."
```

If `origin` already exists, use `git remote set-url origin …` instead of `add`.

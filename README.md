# push-to-kindle-site

Public static site for **Push-to-Kindle** OAuth branding: privacy policy and a minimal home page.

Built with [GitHub Pages](https://pages.github.com/) from the `/docs` folder.

After you merge the open PR, enable **Settings → Pages → Build and deployment → Deploy from a branch**, branch **`main`**, folder **`/docs`**. The site URL is usually:

`https://<github-username>.github.io/<repo-name>/`

GitHub shows the exact URL on the Pages settings page.

## Git layout (for opening a PR)

- **`main`**: initial README only (`chore: initial README for Pages site repo`).
- **`feat/github-pages-docs`**: adds [`docs/`](docs/) (`feat: add GitHub Pages static site (home + privacy policy)`).

## Connect `origin`, push, open PR

Replace `OWNER` and `REPO` with your GitHub user/org and the **existing** public repository name.

```bash
cd ~/Documents/push-to-kindle-site
gh auth login   # if needed

git remote add origin https://github.com/OWNER/REPO.git
# If origin already exists: git remote set-url origin https://github.com/OWNER/REPO.git

# If the empty GitHub repo has no commits, push both branches:
git push -u origin main
git push -u origin feat/github-pages-docs

gh pr create --base main --head feat/github-pages-docs \
  --title "Add GitHub Pages site (home + privacy)" \
  --body "Adds docs/ for GitHub Pages (/docs) and Google OAuth consent screen URLs."
```

### If GitHub already has a README commit (non-empty `main`)

```bash
git fetch origin
git checkout main
git pull origin main --rebase   # or merge; resolve conflicts if any
git checkout feat/github-pages-docs
git rebase main                 # optional: keep PR linear
git push -u origin feat/github-pages-docs
gh pr create --base main --head feat/github-pages-docs --fill
```

Merge the PR on GitHub, then enable Pages from **`/docs`** on **`main`**.

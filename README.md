# Portfolio — deployment guide

This is a single self-contained `index.html` file (no build step, no dependencies to
install). That makes GitHub Pages the simplest way to host it.

## 1. Before you publish — replace the placeholders

Search the file for these and swap in your real details:

| Placeholder | Where | Replace with |
|---|---|---|
| `anujabandararm@gmail.com` | Contact section | Your real email |
| `https://linkedin.com/in/anujabandara` | Contact section | Your LinkedIn URL |
| `https://github.com/SinethB` | GitHub section, Contact, footer | Your GitHub profile URL |
| `resume.pdf` | Résumé section | Your actual résumé file (see step 2) |
| GitHub project cards (`tile-layout-optimizer`, `geomarket-dashboard`, `cse-signal-bot`) | GitHub section | Links to your real public repos, or delete the ones you don't want to publish |

## 2. Add your résumé (optional but recommended)

Export your CV as a PDF, name it `resume.pdf`, and place it in the same folder as
`index.html`. The "Download résumé" button already links to it.

## 3. Push to GitHub

```bash
mkdir my-portfolio && cd my-portfolio
# copy index.html (and resume.pdf) into this folder
git init
git add .
git commit -m "Initial portfolio"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-username>.github.io.git
git push -u origin main
```

Two options for the repo name:

- **`<your-username>.github.io`** — deploys automatically at
  `https://<your-username>.github.io`. This is the standard choice for a personal
  portfolio.
- **Any other repo name** (e.g. `portfolio`) — deploys at
  `https://<your-username>.github.io/portfolio/`. Requires step 4 below.

## 4. Enable GitHub Pages

1. On GitHub, open the repo → **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Branch: `main`, folder: `/ (root)` → **Save**.
4. Wait 1–2 minutes, then visit the URL GitHub shows you.

## 5. Optional: custom domain

In the same **Settings → Pages** screen, add your domain under **Custom domain**,
then create a `CNAME` record at your DNS provider pointing to
`<your-username>.github.io`.

## Notes

- No frameworks, no `npm install` — just static HTML/CSS/JS, so it will keep working
  indefinitely with zero maintenance.
- All animations respect `prefers-reduced-motion`.
- The project write-ups are intentionally written to describe methodology and
  approach without exposing any proprietary company data, datasets, or figures —
  keep it that way if you add more.

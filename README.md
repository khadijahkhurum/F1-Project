# Pit Wall Adversary

Interactive portfolio site for *Mitigating Adversarial Machine Learning Threats in Formula 1 Telemetry Systems*.

Static site, zero build step, zero dependencies — just `index.html`. Every number in the dashboard is pulled directly from the project's notebooks (`03_baseline_model.ipynb`, `04_adversarial_attack.ipynb`, `05_defense_and_robust_training.ipynb`).

## Deploy to Vercel

**Option A — drag and drop (fastest, no account setup beyond signing in)**
1. Go to https://vercel.com/new
2. Choose "Deploy without Git" / drag the `deploy` folder (this folder) onto the page
3. Click Deploy — you'll get a live `*.vercel.app` URL in under a minute

**Option B — Vercel CLI**
```bash
npm i -g vercel     # one-time
cd deploy
vercel               # follow the prompts, accept defaults (static site, no build command)
vercel --prod         # promote to your production URL
```

**Option C — GitHub (best if you want auto-deploys on every push)**
1. Push this folder to a new GitHub repo (e.g. `f1-adversarial-portfolio`)
2. In Vercel: New Project → Import Git Repository → select the repo
3. Framework preset: "Other" (no build command needed) → Deploy

Once deployed, add it to your portfolio and, optionally, set a custom domain or subdomain in Vercel's project settings.

## Editing content

Everything lives in `index.html`:
- Hero stats and copy: search `<header class="hero">`
- Methodology pipeline steps: search `<div class="pipeline">`
- Interactive dashboard data: search `var sweep = [` and `var rangeData = [` near the bottom (all four epsilon values and probability stats are the real recorded results — update these if you rerun the notebooks with different data)
- About section: search `<section id="about">`
- "Read the paper" button: currently links out to the GitHub repo as a placeholder. Once you have a hosted PDF of the paper, replace the `href="#paper"` links (there are two, both with `id="paper-link"` / `id="paper-link-2"`) with the direct PDF URL and remove the click-handler override at the bottom of the `<script>` block.

No `npm install`, no framework, no CDN dependency besides Google Fonts (Oswald / IBM Plex Sans / IBM Plex Mono).

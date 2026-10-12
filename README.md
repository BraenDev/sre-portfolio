# SRE Portfolio — BraenDev

Employer-facing proof-of-capability site for Matthew Smith's transition into
Site Reliability Engineering / DevOps / Platform Engineering roles.

**Live site:** https://braendev.github.io/sre-portfolio/

## Principles

1. **Evidence over claims.** Every project page shows the problem, architecture, code,
   failure test, detection, recovery, and measured results — not a skills list.
2. **Lab work is labeled lab work.** Nothing here pretends a home lab was a production
   outage. Implementations are framed as *"implemented in my SRE lab to demonstrate…"*.
3. **Production-readiness, assessed.** Each project closes with what would change before
   real production. Judgment is the deliverable.

## Structure

```text
index.html                  # homepage
404.html                    # custom not-found page
assets/css/style.css        # site styles (no framework, no build step)
assets/js/main.js           # progressive-enhancement JS only
projects/                   # one folder per project page
  project-template.html     # the 12-section template — copy for new projects
.github/workflows/
  deploy-pages.yml          # build + deploy to GitHub Pages
  ci.yml                    # HTML validation on push/PR
  codeql.yml                # CodeQL analysis (JavaScript)
.github/dependabot.yml      # weekly GitHub Actions updates
```

## Adding a project page

1. Copy `projects/project-template.html` to `projects/<slug>.html`.
2. Fill in every section. Keep the *"implemented in my SRE lab"* framing.
3. Put diagrams and screenshots in `projects/<slug>/`.
4. Add a card for it on the homepage's Explore grid.
5. Open a PR — CI validates the HTML, Pages deploys on merge to `main`.

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Deployment

Pushes to `main` deploy automatically via the `deploy-pages.yml` workflow.
GitHub Pages must be set to **Deploy from GitHub Actions** under
Settings → Pages (one-time setup).

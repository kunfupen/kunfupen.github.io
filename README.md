# kunfupen.github.io

Personal site and portfolio for Khang Thai — M.S. Applied Data Science at USC.

Live: <https://kunfupen.github.io/>

## Stack

[Quarto](https://quarto.org) website with a custom dark theme.

| Path | What it is |
| --- | --- |
| `_quarto.yml` | Site config: navbar, footer, format defaults |
| `theme.scss` | The whole design system (tokens, layout, components) |
| `index.qmd` | Single-page home: hero, stats, about, experience, projects, skills, education, contact |
| `projects.qmd` | Project listing, with a year filter |
| `projects/*.qmd` | One write-up per project, plus its generated SVG cover |
| `head.html` | Font preloads and meta tags |
| `assets/` | Portrait, hero photo, self-hosted fonts, favicon, `site.js.html` |
| `_originals/` | Full-resolution source photos — kept in the repo, not deployed (Quarto skips `_` directories) |
| `.github/workflows/deploy.yml` | Renders the site and publishes it to GitHub Pages |

## Build

```bash
quarto preview     # local dev server with live reload
quarto render      # writes the static site to _site/
```

`_site/` is generated, not committed — CI rebuilds it on every push.

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which renders with
Quarto and publishes `_site/` to GitHub Pages. Pull requests run the render as a
check but do not publish. The Pages source must be set to **GitHub Actions**
under Settings → Pages.

Asset paths are relative rather than absolute, so the site renders correctly
from a domain root or a subpath without any config change.

Fonts are self-hosted, so the only third-party request at runtime is the Tableau
embed on the Airbnb project page.

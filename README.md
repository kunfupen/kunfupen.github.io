# khang-thai.netlify.app

Personal site and portfolio for Khang Thai — M.S. Applied Data Science at USC.

Live: <https://khang-thai.netlify.app/>

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

## Build

```bash
quarto preview     # local dev server with live reload
quarto render      # writes the static site to _site/
```

Netlify deploys `_site/`. Fonts are self-hosted, so the only third-party
request at runtime is the Tableau embed on the Airbnb project page.

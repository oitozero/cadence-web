# cadence/web

The landing page for [Cadence](https://github.com/oitozero/cadence) — a focus
timer for macOS.

It's a single static page: HTML, CSS, an SVG icon, and one screenshot. No
build step, no framework, no dependencies.

## Structure

```
.
├── index.html      # the page
├── styles.css      # dark theme, brand purple #5E6AD2 accent
├── icon.svg        # Cadence "C" mark (mirrors app/build/icons/tray-icon.svg)
└── images/
    └── screenshot.png
```

## Run it locally

Open the file directly:

```sh
open index.html
```

Or serve it (better for matching how a deploy behaves):

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy

Anywhere that serves static files. The simplest options:

- **Vercel** — `npx vercel --prod` from this folder
- **Netlify** — drag the folder onto app.netlify.com/drop
- **GitHub Pages** — push to a `gh-pages` branch, or point Pages at `/web`
- **Cloudflare Pages** — connect the repo, build command empty, output `/`

There is no build step, so the deploy command is the deploy.

## Updating the icon

The brand mark lives in the macOS app at `app/build/icons/tray-icon.svg`. If
the app icon changes, copy the new SVG into [icon.svg](icon.svg) so the site
stays in sync.

## Updating the screenshot

Replace [images/screenshot.png](images/screenshot.png). The hero is sized for
a portrait shot of the app window (~680 × 870 px works well).

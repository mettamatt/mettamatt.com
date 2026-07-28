# Dominex marketing site

Static marketing website for Dominex. Plain HTML and CSS — no build step, no dependencies.

- Copy source: `docs/marketing/features-and-benefits.md`
- Visual identity mirrors `design/tokens.css` (Ink & Parchment). Token values are copied by hand into
  `styles.css`; update both together.
- Fonts: Fraunces variable woff2, copied from `apps/web/src/assets/fonts/` (OFL-licensed; license at
  `design/fonts/Fraunces/OFL.txt`).
- Hero screenshot: resized from `derived/app-store/screenshots/dominex-map-hub-native.png`.

## Preview locally

```sh
npx serve apps/marketing
# or
python3 -m http.server -d apps/marketing 8080
```

## Before launch

- Replace the three `/play` CTA links in `index.html` with the production game URL (or add a Vercel rewrite
  so `/play` reaches the game).
- Set an absolute URL for the `og:image` meta tag once the domain is known.

## Deploying

The root `vercel.json` builds the game (`apps/web/dist`), so this site needs its own Vercel project:
create a second project on the same repo with root directory `apps/marketing`, no build command, and
output directory `.` — or serve it from any static host.

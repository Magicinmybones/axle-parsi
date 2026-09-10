# Axle — Hero

Static landing page ("Less friction. More possibility."), deployed on Cloudflare Pages.

## Structure

```
public/
  index.html                       the page
  assets/
    fonts/parsi-300.woff2          Parsi, weight 300 (was inlined as base64)
    fonts/parsi-400.woff2          Parsi, weight 400 (was inlined as base64)
    fonts/parsi-700.woff2          Parsi, weight 700 (was inlined as base64)
    images/scene.jpg               full-bleed scene photo (was inlined as base64, twice)
```

The source HTML shipped every asset as a base64 `data:` URI (527 KB single file).
All four were extracted to `public/assets/`, so `index.html` is now 85 KB and the
fonts and photo are cached separately by the browser. The photo was inlined twice —
once as the `--photo` CSS variable and once as the `<img>` source — and is now a
single shared file.

## Local preview

```bash
npm install
npm run dev
```

## Deploy

```bash
npm run deploy
```

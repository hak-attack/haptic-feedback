# Haptic here

A minimal Tailwind static page with a primary CTA that triggers best-effort haptics on mobile browsers. Designed to be easily hosted on GitHub Pages.

## Features
- Single CTA: "Haptic here"
- Responsive layout tuned for iPhone 12 and scales to other screens
- Tailwind via CDN (no build step)
- Haptics strategy:
  - Use `navigator.vibrate` where available (mostly Android)
  - iOS fallback: subtle Web Audio click + micro press animation

## Local usage
Open `index.html` in a browser. For mobile testing, serve over HTTPS (GitHub Pages provides this).

## Deploy to GitHub Pages
You can publish either a user site or a project site.

### Option A: User site (recommended)
1. Create a new public repo named exactly `<username>.github.io`.
2. Add these files to the repo root: `index.html`, `README.md`, optional `.nojekyll`.
3. Commit to `main` and push.
4. Visit `https://<username>.github.io/` after ~1 minute.

### Option B: Project site
1. Create a new public repo (any name).
2. Push files to `main`.
3. Repo Settings → Pages → Source: `main` / root folder.
4. Site URL: `https://<username>.github.io/<repo>/`.

## iOS Chrome note
iOS browsers use WebKit; system `navigator.vibrate` is typically unavailable. This page includes a graceful audio/visual fallback so taps still feel responsive. If/when WebKit enables vibration, it will work automatically via the existing code path.

## Files
- `index.html` – markup, Tailwind, haptics logic
- `.nojekyll` – optional, skip Jekyll processing on Pages

## License
MIT

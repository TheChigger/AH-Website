# Autumn Hendrix — Webador Theme (GitHub Pages)

Clean, version-controlled CSS override layer and branding asset host for **https://autumnhendrixauthor.com**.

## Key Layout Rules Included
- **Width-fitted, undistorted background**: `assets/backgrounds/site-background.png` (`Copy of AUTHOR WEBSITE TEMPLATE-4.png`) is rendered inside `body::before` using `background-size: 100% auto;` so it always fills the viewport width and crops vertically without squeezing or stretching.
- **All 5 Unwell Series cards styled**: Mapped directly to your real Webador `#jw-element-*` sections using your uploaded purple rose, petal wreath, and floral backdrops.
- **Mobile readability fixed**: Frosted high-contrast reading surfaces across `/my-shop`, `/my-books`, `/about-me`, and `/newsletter`, WCAG AA heading colors, and responsive `16px` mobile card padding.

## Repository Structure

```text
AH-Website/
├── .github/workflows/deploy.yml   # Auto-builds dist/theme.css & deploys GitHub Pages
├── assets/
│   ├── backgrounds/               # Site background + 5 book section backdrops
│   ├── books/                     # Unwell Series book covers (UW 1–5)
│   └── logos/                     # Autumn Hendrix wordmark & About Me avatar
├── src/
│   ├── tokens.css                 # Colors, spacing, surface opacity, asset URLs
│   ├── base.css                   # Width-fit 100% auto fixed backdrop & typography
│   ├── header-mobile.css          # Mobile top bar, hamburger, cart & drawer
│   ├── books.css                  # All 5 Unwell Series cards & responsive padding
│   ├── shop.css                   # Frosted reading cards for /my-shop & /product/*
│   └── modals.css                 # Solid white cart & popup overlays
├── dist/
│   └── theme.css                  # Compiled single-file stylesheet loaded by Webador
└── index.html                     # Status page for verifying deployment
```

## Step-by-Step Setup in Webador

1. Push this repository to GitHub at `https://github.com/thechigger/AH-Website`.
2. In your GitHub repo, go to **Settings → Pages → Source** and choose **GitHub Actions**.
3. Wait ~45 seconds for the workflow to finish, then open `https://thechigger.github.io/AH-Website/dist/theme.css` to confirm it loads.
4. In **Webador**, go to **Settings → Advanced → HTML in `<head>` tag**:
   - **Remove** the two old inline `<style>...</style>` blocks so they don't conflict with the new theme.
   - **Paste** this single line:

```html
<!-- Autumn Hendrix External Theme (Hosted on GitHub Pages) -->
<link rel="stylesheet" href="https://thechigger.github.io/AH-Website/dist/theme.css?v=1.0" />
```

5. Whenever you push a CSS update, bump `?v=1.0` to `?v=1.1` in Webador so mobile browsers fetch the latest styles right away.

## Mapped Branding Assets (14 files)

- `assets/backgrounds/site-background.png` ← `Copy of AUTHOR WEBSITE TEMPLATE-4.png` (Website Background)
- `assets/logos/autumn-hendrix-wordmark.png` ← `Copy of AUTHOR WEBSITE TEMPLATE-11.png` (Autumn Hendrix Hero Wordmark)
- `assets/logos/ah-avatar.png` ← `AH avatar V3.png` (Autumn Hendrix About Avatar)
- `assets/backgrounds/rainbow-torn-edge.png` ← `Copy of AUTHOR WEBSITE TEMPLATE-3.png` (Torn-Paper Rainbow Accent)
- `assets/books/uw-1-when-im-gone.png` ← `UW 1 - When I'm Gone.png` (UW 1 — When I'm Gone Cover)
- `assets/backgrounds/when-im-gone-background.jpg` ← `28E8E15E-85FE-422E-BCC7-4791FC7BD471.JPG` (When I'm Gone Card Background)
- `assets/books/uw-2-begin-again.png` ← `UW 2 - Begin Again ebook cover.png` (UW 2 — Begin Again Cover)
- `assets/backgrounds/begin-again-background.png` ← `Begin Again Background.png` (Begin Again Card Background)
- `assets/books/uw-3-broken-things.png` ← `UW 3 - Broken Things Cover.png` (UW 3 — Broken Things Cover)
- `assets/backgrounds/broken-things-background.png` ← `Broken Things Background.png` (Broken Things Card Background)
- `assets/books/uw-4-only-ever-you.png` ← `UW 4 - Only Ever You.png` (UW 4 — Only Ever You Cover)
- `assets/backgrounds/only-ever-you-background.png` ← `Only Ever You Background.png` (Only Ever You Card Background)
- `assets/books/uw-5-naughty-and-nice-list.png` ← `UW 5 Naughty and Nice List.png` (UW 5 — Naughty & Nice List Cover)
- `assets/backgrounds/naughty-list-background.png` ← `Naught List background.png` (Naughty List / Christmas Card Background)

> **Performance tip:** Several original print-resolution PNGs (like `Begin Again Background.png` at 14.5 MB and `Only Ever You Background.png` at 9.9 MB) can be compressed to WebP/JPG under 300 KB without visible quality loss for noticeably faster phone loading.

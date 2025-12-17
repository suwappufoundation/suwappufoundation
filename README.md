# Suwappu Foundation

A new way to swap — Suwappu is a revolutionary Layer 1 blockchain focusing on liquidity aggregation, swapping, lending, and building the largest stablecoin pools.

## Overview

This repository contains the Suwappu Foundation landing page: a retro terminal-style single-page site that presents the whitepaper in a typewriter animation.

### Features

- **Terminal aesthetic** — Retro green-on-black CRT look with ASCII art
- **Typewriter animation** — Content types out character-by-character
- **Interactive choices** — Users can press `J` to join or `S` to stay
- **Accessible** — Keyboard navigation, screen reader support, respects `prefers-reduced-motion`
- **Mobile-friendly** — Responsive layout with touch-friendly controls
- **Zero dependencies** — Single HTML file, no build step required

## View Locally

Simply open `index.html` in any modern browser:

```bash
# macOS
open index.html

# Linux
xdg-open index.html

# Windows
start index.html
```

Or use a local server (useful for testing CSP headers):

```bash
# Python 3
python -m http.server 8000

# Node.js (npx)
npx serve .

# Then visit http://localhost:8000
```

## Deploy

### GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Under **Source**, select the branch (e.g., `main`) and folder (`/ (root)`)
4. Click **Save** — your site will be live at `https://<username>.github.io/suwappufoundation/`

### Other Static Hosts

Upload `index.html` to any static hosting provider:

- **Vercel** — `vercel deploy`
- **Netlify** — Drag & drop the folder or connect the repo
- **Cloudflare Pages** — Connect the repo and deploy
- **IPFS** — Pin the file for decentralized hosting

## Customization

### Change the Whitepaper Text

Edit the `WHITEPAPER` constant inside the `<script>` tag in `index.html` (around line 230). The content is plain text with ASCII art formatting.

### Adjust Typing Speed

Modify the `speeds` object in the script:

```javascript
const speeds = {
    slow: { base: 60, variance: 40 },
    normal: { base: 15, variance: 20 },
    fast: { base: 2, variance: 5 }
};
```

- `base` — Minimum delay in milliseconds
- `variance` — Random additional delay

### Update Branding / Colors

All styles are in the `<style>` block. Key CSS variables to look for:

| Element | Property | Default |
|---------|----------|---------|
| Background | `background-color` | `#0a0a0a` |
| Text / Accent | `color`, `border-color` | `#00ff41` |
| Glow effect | `box-shadow` | `rgba(0, 255, 65, ...)` |

### Change the CTA Link

Find the Telegram link in the `handleChoice` function and update the URL:

```javascript
link.href = 'https://t.me/suwappucommunity';
```

### Add Meta / Social Images

Add an `og:image` and `twitter:image` meta tag in the `<head>`:

```html
<meta property="og:image" content="https://yourdomain.com/og-image.png">
<meta name="twitter:image" content="https://yourdomain.com/twitter-image.png">
```

## Accessibility Notes

- Users who prefer reduced motion see the full content instantly (no typing animation)
- All interactive elements are keyboard-accessible
- Screen readers announce content updates via `aria-live`
- Visual controls (Skip, Speed, Restart) complement keyboard shortcuts

## License

MIT

# Self-Care Tracker

A lightweight PWA for tracking morning and evening self-care habits on iPhone (or any mobile browser).

## What it does

- Set up 3–5 habits each for morning and evening
- Tick them off as you go, with a motivational prompt rotating from 100 built-in reasons
- Snooze or dismiss (with a reason: tired, demotivated, unwell, other)
- View a 14-day history of completions and dismissals
- Auto-detects morning or evening based on time of day, with manual override
- All data stored locally in IndexedDB (nothing leaves your device)

## Setup

1. Upload all files to the root of a GitHub Pages repo (or any static host)
2. Enable GitHub Pages in the repo settings (deploy from `main`, root directory)
3. Open the URL on your phone

### Adding to iPhone home screen

Safari's "Add to Home Screen" works, but the icon options are limited. For a custom icon, create an iOS Shortcut:

1. Open the Shortcuts app
2. Create a new shortcut with the "Open URL" action pointing to your GitHub Pages URL
3. Tap the shortcut name at the top, then "Add to Home Screen"
4. Tap the icon to choose your own image

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire app (single file, no build step) |
| `sw.js` | Service worker for offline support and PWA install |
| `manifest.json` | PWA manifest |
| `icon-180.png` | Apple touch icon |
| `icon-192.png` | PWA icon (192px) |
| `icon-512.png` | PWA icon (512px) |

## Tech

Single HTML file using Dexie.js (IndexedDB wrapper) loaded from CDN. No framework, no build process, no server. Fonts loaded from Google Fonts (Cormorant Garamond and DM Sans).

## Customisation

- **Habits**: managed in-app via the Setup tab
- **Motivational prompts**: edit the `REASONS` array in `index.html`
- **Time windows**: morning auto-detects 5am–12pm, evening 5pm–11pm (edit `detectMode()` in the script)
- **Theme**: CSS variables at the top of the `<style>` block

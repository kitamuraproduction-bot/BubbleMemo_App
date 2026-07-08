# BubbleMemo 🫧

**日本語版は[こちら](../README.md)。**

A playful, physics-driven memo app where your thoughts float as bubbles. Write an idea, watch it pop onto the board, and organize your thinking by dragging, grouping, inflating, and popping bubbles — all in a single HTML file that runs entirely in your browser.

> **Try it:** https://kitamuraproduction-bot.github.io/BubbleMemo_App/

![BubbleMemo screenshot](../screenshot_desktop.png)

## Features

- **Bubble memos** — Write a note and press Enter (on mobile, confirm the text then press return again) to turn it into a floating bubble. Use Shift+Enter, or the "newline" button next to the input bar, for multi-line notes. Drag bubbles around freely; they gently push each other out of the way.
- **Groups (big bubbles)** — Drop bubbles into a big bubble to group related ideas. Groups auto-resize to fit their contents, can be nested, and can be renamed with a tap.
- **Pump & pin modes** — Long-press with the pump 🚲 to inflate a bubble (make an idea bigger!), or with the pin 📌 to shrink it. Tap with the pin to pop a bubble. Works on groups too: shrinking a group automatically repacks the bubbles inside.
- **Connections** — Long-press a bubble and drag to another to link them with a line. Click the line (double-tap on mobile) to reveal a ❌ and remove it.
- **Multiple boards** — Keep separate boards for separate projects, with selectable backgrounds (plain grid, world map, Japan map). The free version supports up to 5 boards.
- **One-tap sharing** — Tap "Send this board" and a share link is copied to your clipboard. The entire board is compressed and embedded in the URL itself — when someone opens it, an independent copy is imported onto *their* device. No accounts, no server, no collaborative editing surprises.
- **JSON export / import** — Save or restore the entire board state as a JSON file. You can hand an exported JSON to an AI to reorganize or edit, then import the result back in.
- **Undo / redo (Ctrl+Z / Ctrl+Y), lasso selection, alignment tools** — and other small conveniences for tidying up your thoughts.

## Privacy & data

BubbleMemo is a **completely serverless** web app:

- All boards are stored in your browser's `localStorage`. Nothing is uploaded anywhere.
- Share links carry the board data in the URL **fragment** (`#board=...`), which browsers do not send to any server.
- There is no tracking, no analytics, and no account system.

⚠️ **Note for iOS Safari users:** Safari may delete site data (including your boards) if you don't visit a site for 7 days. Adding BubbleMemo to your home screen exempts it from this cleanup and is the recommended way to use it.

## Disclaimer

BubbleMemo is **not designed for storing confidential or sensitive information**. Please do not use it for passwords, personal data, trade secrets, or anything similar. Also note that share links contain the full board data — anyone who obtains a link can view its contents.

The author assumes **no responsibility or liability whatsoever** for information leakage, data loss, or any other damages arising from the use of this app. Use at your own risk.

## Running & deploying

BubbleMemo is a single `index.html` with zero dependencies and no build step.

- **Run locally:** just open `index.html` in a browser.
- **Deploy:** upload the file to any static host (GitHub Pages, Cloudflare Pages, Netlify, etc.). That's the entire deployment.

Because share links embed the full board data, links generated on one deployment URL will keep working as long as that URL stays alive — pick your final domain before sharing links widely.

## Tech notes

- Vanilla JavaScript, HTML, and CSS. No frameworks, no external libraries, no network requests.
- Custom soft-body-ish bubble physics with group packing and overlap resolution.
- Share links use `CompressionStream` (deflate) + base64url encoding, with an uncompressed fallback for older browsers.
- Custom in-app dialogs are used instead of `prompt()`/`confirm()` so the app also works inside WKWebView-based in-app browsers.

## Roadmap

- [ ] PWA manifest & offline install prompt
- [ ] Premium plan with unlimited boards
- [ ] More backgrounds and bubble themes

## License / Copyright

Copyright (c) 2026 kitamuraproduction. **All rights reserved.**

This repository is published for **viewing purposes only**. Unauthorized use, copying, modification, or redistribution of the source code — including publishing modified versions of this app — is **strictly prohibited** without the author's prior written permission.

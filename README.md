# MeterVision — Website

Marketing site and interactive dashboard for **MeterVision**, an end-to-end computer
vision pipeline that detects utility meters in photos and reads their displayed values.

The underlying ML pipeline (Faster R-CNN localizers + a segment-aware digit CNN) lives in a
separate repository: [Meter-reading-public](https://github.com/mathewray/Meter-reading-public).

## Contents

| File | Description |
|------|-------------|
| `index.html` | Landing page — pipeline overview, utility use-case, architecture, install guide |
| `dashboard.html` | Standalone React + Tailwind real-time monitoring dashboard (upload, animated pipeline, KPIs, history) |
| `style.css` | Styles for the landing page |
| `*.png` | Example meter photos and detection-overlay outputs used on the site |

## Running locally

Everything is static — no build step required. Serve the folder with any static server:

```bash
python3 -m http.server 3456
```

Then open:

- Landing page → http://127.0.0.1:3000/index.html?serverWindowId=cd333eb8-5f26-4867-924b-9ac926b578f0
- Live dashboard → http://127.0.0.1:3000/dashboard.html?serverWindowId=78455328-8ab2-4b15-afc6-2e2f3904abab

The dashboard loads React, Tailwind, and Babel from CDNs, so it runs straight from the file.
For production you'd precompile (e.g. Vite + Tailwind CLI) rather than using the CDN builds.

## Tech

- Static HTML + CSS landing page (Inter / JetBrains Mono, dark theme)
- `dashboard.html`: React 18 + Tailwind (CDN), inline Lucide-style SVG icons, mock inference data

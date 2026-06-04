# Alpha Bleed Fix

**[Try it live](https://gatekeeperdev.github.io/alpha-bleed-fix/)**

Fix dark edges on transparent images caused by bilinear interpolation — a common issue with Roblox image compression.

## What it does

When images with transparency are scaled using bilinear interpolation (as Roblox does), the GPU averages nearby pixel colors — including fully transparent pixels that often contain black RGB values. This causes dark edges and fringing around transparent boundaries.

Alpha bleeding fills the RGB values of transparent pixels with colors from their nearest opaque neighbors using a BFS flood-fill algorithm. This way, when interpolation occurs during rendering, the averaged values produce visually correct results while the alpha channel stays unchanged.

## Features

- Upload one or multiple images (PNG, WebP)
- Per-image card with its own controls and side-by-side before/after preview
- Rename each output file
- Resize the output (with optional aspect-ratio lock) — done in straight-alpha space so the bled RGB is preserved at any size
- Download fixed images individually or all at once as a ZIP
- Runs entirely in your browser — no server upload needed

## Usage

1. Drop or select your transparent images
2. For each image, optionally rename it and set the output width/height
3. Click **Fix Images**
4. Preview the before/after result on each card
5. Click **Download** on a card, or **Download All** for a ZIP

# Alpha Bleed Fix

**[Try it live](https://gatekeeperdev.github.io/alpha-bleed-fix/)**

Fix dark edges on transparent images caused by bilinear interpolation — a common issue with Roblox image compression.

## What it does

When images with transparency are scaled using bilinear interpolation (as Roblox does), the GPU averages nearby pixel colors — including fully transparent pixels that often contain black RGB values. This causes dark edges and fringing around transparent boundaries.

Alpha bleeding fills the RGB values of transparent pixels with colors from their nearest opaque neighbors using a BFS flood-fill algorithm. This way, when interpolation occurs during rendering, the averaged values produce visually correct results while the alpha channel stays unchanged.

## Features

- Upload one or multiple images (PNG, WebP)
- Adjustable bleed radius (1–64 pixels)
- Side-by-side before/after preview
- Download fixed images individually or as a ZIP
- Runs entirely in your browser — no server upload needed

## Usage

1. Drop or select your transparent images
2. Adjust the bleed radius if needed (default 8 works well for most cases)
3. Click **Fix Images**
4. Preview the results and click **Download All**

---
name: pixel-portrait
description: Generate pixel art from text descriptions using an 8x8 grid.
metadata:
  homepage: https://github.com/snuri00/ai-edge-gallery-skills
---

# Pixel Portrait

Create pixel art from descriptions. You draw on an 8x8 grid (64 pixels total).

## Triggers

- "Draw pixel art of a cat"
- "Pixel art sun"
- "Piksel çizim: kalp"

## Instructions

Call the `run_js` tool with a JSON data string containing these fields:

- title: What you drew (string)
- pixels: Array of exactly 64 hex color strings, row by row (8 rows, 8 columns). Use "#0" for transparent/empty pixels. Use short hex like "#F00" for red, "#0F0" for green, etc.

Think of the 8x8 grid as rows. Row 1 is the top, row 8 is the bottom. Fill each row left to right.

Tips for good pixel art:
- Use 4-6 colors only
- Use "#0" for background/empty
- Dark outline colors help define shapes
- Keep shapes simple and centered

Example for a red heart:
```
{"title":"Heart","pixels":["#0","#0","#0","#0","#0","#0","#0","#0","#0","#F22","#F22","#0","#F22","#F22","#0","#0","#F22","#F55","#F22","#F22","#F55","#F22","#F22","#0","#F22","#F22","#F22","#F22","#F22","#F22","#F22","#0","#0","#F22","#F22","#F22","#F22","#F22","#0","#0","#0","#0","#F22","#F22","#F22","#0","#0","#0","#0","#0","#0","#F22","#0","#0","#0","#0","#0","#0","#0","#0","#0","#0","#0","#0","#0"]}
```

DO NOT use any other tool. Return the webview and briefly describe what you drew.

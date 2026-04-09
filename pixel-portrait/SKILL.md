---
name: pixel-portrait
description: Generate pixel art from text descriptions using a compact 8x8 grid.
metadata:
  homepage: https://github.com/snuri00/ai-edge-gallery-skills
---

# Pixel Portrait

Create pixel art from descriptions on an 8x8 grid.

## Triggers

- "Draw pixel art of a cat"
- "Pixel art sun"
- "Piksel çizim: kalp"

## Instructions

Call the `run_js` tool with a JSON data string containing:

- title: What you drew
- colors: An object mapping single characters to hex colors. Use "." for empty/transparent.
- rows: An array of exactly 8 strings, each exactly 8 characters long. Each character maps to a color in the colors object.

Use only 3-5 color characters (A, B, C, D, E) plus "." for empty.

Example — a red heart:

```json
{"title":"Heart","colors":{"A":"#E33","B":"#F66",".":""},"rows":["..AA.AA.","ABBAABBA","ABBBBBBA","ABBBBBBA",".ABBBBA.",".AABBAA.","..ABBA..","...AA..."]}
```

Example — a yellow star:

```json
{"title":"Star","colors":{"A":"#FB0","B":"#F90","C":"#DA0",".":""},"rows":["...AB...","...AB...","..ABBA..",".ABCCBA.","ABCCCCBA",".ABCCBA.","..ABBA..","..A..A.."]}
```

Keep shapes simple, centered, and use darker colors for outlines.

DO NOT use any other tool. Return the webview and briefly describe what you drew.

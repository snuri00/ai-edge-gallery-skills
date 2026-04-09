---
name: pixel-portrait
description: Generate pixel art portraits and images from text descriptions. Describe anything and get a colorful pixel art rendition.
metadata:
  homepage: https://github.com/snuri00/ai-edge-gallery-skills
---

# Pixel Portrait - AI Pixel Art Generator

Generate beautiful pixel art from text descriptions. Describe a character, animal, object, scene, or anything — and get a unique pixel art image.

## Prompts / Triggers

- "Draw a pixel art cat"
- "Piksel portre: robot"
- "Pixel art of a sunset over mountains"
- "Make pixel art of Mario"
- "Draw a pixel heart"
- "Piksel çizim: uzay gemisi"

## Instructions

When the user asks for pixel art, generate a 16x16 pixel grid of hex color values that represents the described subject.

### How to generate the pixel grid:

Think of a 16x16 canvas. Each cell is one pixel with a hex color. Build the image row by row, from top-left to bottom-right.

**Rules:**
- Use a LIMITED palette of 8-12 colors maximum for a clean pixel art look.
- Use "#00000000" (transparent) for empty/background pixels.
- Think about the shape, outline, shading, and key features of the subject.
- Add a 1-pixel dark outline around the main subject for definition.
- Use lighter shades on top/left for highlights, darker on bottom/right for shadows.
- Keep it simple — pixel art is about recognizable shapes with minimal detail.

### Step-by-step process:

1. **Plan the palette**: Choose 6-10 hex colors that fit the subject (e.g., for a cat: #000000 outline, #ff9800 orange fur, #ffb74d light fur, #fff3e0 belly, #4caf50 green eyes, #f48fb1 pink nose).

2. **Build row by row**: Generate exactly 256 hex color strings (16 rows × 16 columns), listed left-to-right, top-to-bottom. Use "#00000000" for transparent/background pixels.

3. **Call the `run_js` tool** with:
   - data: A JSON string with these fields:
     - title: Short title of the artwork (e.g., "Orange Cat", "Space Robot")
     - palette: Array of the hex colors used (for display)
     - pixels: Flat array of exactly 256 hex color strings, row by row

Example data:
```json
{
  "title": "Red Heart",
  "palette": ["#e53935","#c62828","#f44336","#ff5252","#00000000"],
  "pixels": [
    "#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000",
    "#00000000","#00000000","#00000000","#e53935","#e53935","#00000000","#00000000","#00000000","#00000000","#e53935","#e53935","#00000000","#00000000","#00000000","#00000000","#00000000",
    "#00000000","#00000000","#e53935","#ff5252","#f44336","#e53935","#00000000","#00000000","#e53935","#ff5252","#f44336","#e53935","#00000000","#00000000","#00000000","#00000000",
    "#00000000","#e53935","#ff5252","#f44336","#f44336","#e53935","#e53935","#e53935","#e53935","#f44336","#f44336","#f44336","#e53935","#00000000","#00000000","#00000000",
    "#00000000","#e53935","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#e53935","#00000000","#00000000","#00000000",
    "#00000000","#e53935","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#e53935","#00000000","#00000000","#00000000",
    "#00000000","#00000000","#e53935","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#f44336","#e53935","#00000000","#00000000","#00000000","#00000000",
    "#00000000","#00000000","#00000000","#e53935","#e53935","#f44336","#f44336","#f44336","#f44336","#e53935","#e53935","#00000000","#00000000","#00000000","#00000000","#00000000",
    "#00000000","#00000000","#00000000","#00000000","#e53935","#c62828","#c62828","#c62828","#e53935","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000",
    "#00000000","#00000000","#00000000","#00000000","#00000000","#e53935","#c62828","#e53935","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000",
    "#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#e53935","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000",
    "#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000",
    "#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000",
    "#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000",
    "#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000",
    "#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000","#00000000"
  ]
}
```

DO NOT use any other tool, DO NOT call `run_intent`.

IMPORTANT: Return the webview and tell the user to tap the preview card to see their pixel art. You can also briefly describe what you drew.

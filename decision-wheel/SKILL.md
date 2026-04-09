---
name: decision-wheel
description: Spin a colorful wheel to randomly pick from a list of options for any decision.
metadata:
  homepage: https://github.com/snuri00/ai-edge-gallery-skills
---

# Decision Wheel

An interactive, animated spinning wheel that helps users make decisions by randomly selecting from their provided options. Works for any kind of choice — dinner, movies, games, travel destinations, or anything else.

## Examples

- "Help me decide between pizza, burger, sushi, and tacos"
- "Spin a wheel for movie night: action, comedy, horror, drama"
- "I can't choose between Istanbul, Paris, Tokyo, and New York for vacation"
- "Pick one: read a book, play games, watch TV, go for a walk"

## Instructions

When the user provides a list of options or asks for help deciding between choices, extract the options and call the `run_js` tool with the following exact parameters:
- data: A JSON string with the following fields:
  - options: An array of strings representing the choices (minimum 2, maximum 12).
  - title: A short title describing what the decision is about (e.g., "Dinner", "Movie Night", "Vacation").

DO NOT use any other tool, DO NOT call `run_intent`.

IMPORTANT: When the wheel is generated, DO NOT pick a winner for the user. Simply return the webview and tell the user to tap the preview card to spin the wheel and let fate decide.

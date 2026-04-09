---
name: uniwords
description: A word puzzle game where players find words from given letters. Supports Turkish and English.
metadata:
  homepage: https://github.com/snuri00/ai-edge-gallery-skills
---

# Uniwords - Word Puzzle Game

A fun and educational word puzzle game. The player is given a set of letters and must find as many valid words as possible.

## Prompts / Triggers

- "Let's play Uniwords"
- "Uniwords oynayalım"
- "Word puzzle game"
- "Kelime bulmaca oyunu"
- "Play a word game in Turkish"
- "Play a word game in English"

## Instructions

When the user wants to play Uniwords, determine the language (Turkish or English) from context or ask if unclear.

Then generate a puzzle:

1. Pick exactly 7 random letters that allow forming many words. For Turkish, include common Turkish letters (a, e, i, k, l, r, m, n, s, t, etc.) and optionally special characters (ç, ş, ğ, ı, ö, ü). For English, pick common English letters. Make sure the letters can form at least 15 valid words (3-7 letters long).

2. Generate ALL valid words (3 to 7 letters long) that can be formed using only the given letters. Each letter can only be used once per word (based on how many times it appears in the given letters). Be thorough — include common nouns, verbs, adjectives, and adverbs. Do NOT include proper nouns, abbreviations, or very obscure words. Aim for 15-40 valid words.

3. Pick one special "bonus word" that uses 6 or 7 of the given letters.

4. Call the `run_js` tool with the following exact parameters:
   - data: A JSON string with the following fields:
     - letters: An array of 7 uppercase letter strings (e.g., ["K","E","L","İ","M","A","S"])
     - words: An array of all valid words in lowercase (e.g., ["kelime","kale","elma",...])
     - bonus: The bonus word in lowercase
     - language: "tr" or "en"

DO NOT use any other tool, DO NOT call `run_intent`.

IMPORTANT: Do NOT reveal the words to the user. Just return the webview and tell the user to tap the preview card to start playing.

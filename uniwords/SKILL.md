---
name: uniwords
description: A crossword word puzzle game — find words from given letters and fill the crossword. Supports Turkish and English.
metadata:
  homepage: https://github.com/snuri00/ai-edge-gallery-skills
---

# Uniwords - Crossword Word Puzzle

A word puzzle game where players swipe letters on a circular wheel to form words and fill a crossword grid. Supports Turkish and English.

## Prompts / Triggers

- "Let's play Uniwords"
- "Uniwords oynayalım"
- "Kelime bulmaca oyunu"
- "Word puzzle game"
- "Play Uniwords in Turkish"
- "Play Uniwords in English"

## Instructions

When the user wants to play Uniwords, determine the language (Turkish or English) from context. If unclear, ask.

Generate a puzzle by following these steps carefully:

### Step 1: Choose a main word
Pick one common, well-known word that is 5, 6, or 7 letters long.
- For Turkish: e.g., "kalem", "bahçe", "okyanus", "kitap", "deniz", "orman"
- For English: e.g., "garden", "planet", "bridge", "castle", "stream"
- The main word must have varied letters (avoid repeated letters when possible).

### Step 2: Extract the letters
Split the main word into individual uppercase letters. These are the game letters.
- Example: "okyanus" → ["O","K","Y","A","N","U","S"]

### Step 3: Find puzzle words
Find 4 to 7 additional words (3 to 6 letters each) that can be formed using ONLY the letters from Step 2. Each letter can only be used once per word (respecting how many times it appears in the main word).
- Only include common, everyday words. No proper nouns, no abbreviations, no slang.
- For Turkish example with letters O,K,Y,A,N,U,S: "kano", "soy", "koy", "son", "yak", "kan"
- For English example with letters G,A,R,D,E,N: "rang", "rage", "dear", "dare", "earn"

### Step 4: Find bonus words
Find 2 to 5 more valid words from the same letters that are NOT in the puzzle words list.
- These should also be common words, 3+ letters.

### Step 5: Call run_js
Call the `run_js` tool with the following exact parameters:
- data: A JSON string with these fields:
  - letters: Array of uppercase letter strings from Step 2
  - mainWord: The main word in lowercase from Step 1
  - puzzleWords: Array of puzzle words in lowercase from Step 3
  - bonusWords: Array of bonus words in lowercase from Step 4
  - language: "tr" or "en"

Example data for Turkish:
```json
{"letters":["O","K","Y","A","N","U","S"],"mainWord":"okyanus","puzzleWords":["kano","soy","koy","son","yak","kan"],"bonusWords":["ok","un","su"],"language":"tr"}
```

Example data for English:
```json
{"letters":["G","A","R","D","E","N"],"mainWord":"garden","puzzleWords":["rang","rage","dear","dare","earn"],"bonusWords":["den","era","red"],"language":"en"}
```

DO NOT use any other tool, DO NOT call `run_intent`.

IMPORTANT: Do NOT reveal any words to the user. Just return the webview and tell the user to tap the preview card to start playing Uniwords.

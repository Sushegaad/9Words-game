# 10 WORDS — Hourly Word Puzzle

A fast-paced, browser-based word puzzle where you reassemble 10 scrambled words against the clock. A new puzzle is generated every hour, shared by all players worldwide via a deterministic seed.

---

## How to Play

1. **Select a fragment** from the Fragment Pool (click or drag).
2. **Place it** into an empty slot in the Word Assembly panel.
3. **Swap** fragments by clicking a filled slot, then clicking another.
4. **Double-click** a filled slot to return it to the pool.
5. **Drag and drop** is fully supported — drag fragments directly from the pool into any word slot.
6. Solve all 10 words before the 10-minute timer runs out.

### Scoring

| Score | Stars |
|-------|-------|
| 1 – 100 | ★☆☆☆☆☆ |
| 101 – 200 | ★★☆☆☆☆ |
| 201 – 300 | ★★★☆☆☆ |
| 301 – 400 | ★★★★☆☆ |
| 401 – 500 | ★★★★★☆ |
| 501 – 600 | ★★★★★★ |

If you solve all 10 words, your score equals the **seconds remaining** on the clock (max 600). If time runs out, your score equals `words solved × 30`.

---

## Features

- **Hourly puzzle seed** — everyone playing in the same hour gets the same 10 words.
- **10 unique word lengths** — one word per length from 6 to 15 letters, sorted shortest to longest in the assembly panel.
- **Drag & drop** — drag fragments from the pool directly into word slots; drag filled slots to swap them; drag a filled slot back onto a pool row to return it.
- **Light & dark theme** — toggle with the ☀/☾ button in the header; preference is saved locally.
- **Responsive** — works on mobile and desktop; panels stack vertically on small screens.
- **Social sharing** — share your score to Facebook, Twitter/X, WhatsApp, Reddit, or copy a link.
- **Confetti** — a small celebration when you solve a word, and a big one when you solve all 10.

---

## File Structure

```
10Words/
└── index.html   # Entire game — self-contained, no build step required
```

All CSS, JavaScript, and the word bank are inlined in `index.html`. There are no dependencies beyond a Google Fonts CDN link (the game is fully playable offline if the fonts fall back to system fonts).

---

## Running Locally

Just open `index.html` in any modern browser:

```bash
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

Or serve it with any static file server:

```bash
npx serve .
python3 -m http.server 8080
```

---

## Publishing to GitHub Pages

1. **Create a repository** at [github.com/new](https://github.com/new) (set it to Public).
2. **Upload `index.html`** — click *"uploading an existing file"* on the empty repo page, drag the file in, and commit.
3. **Enable GitHub Pages** — go to **Settings → Pages**, set Source to *"Deploy from a branch"*, select `main` / `(root)`, and click **Save**.
4. Your game will be live at:
   ```
   https://<your-username>.github.io/<repo-name>/
   ```

No build tools, no CI pipeline needed — just the single HTML file.

---

## Word Bank

The puzzle draws from a curated bank of ~700 common English words, grouped by length (6–15 letters). Each hour, one word is selected per length group using a seeded shuffle, ensuring the same puzzle for all players in that hour window.

---

## Browser Support

Works in all modern browsers (Chrome, Firefox, Safari, Edge). Drag-and-drop uses the native HTML5 Drag and Drop API; click-based interaction is also fully supported as a fallback.

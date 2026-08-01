 # Errsplain

A browser-based tool that explains raw Python and JavaScript error messages in plain English — what went wrong, why it happened, and how to fix it.

**Live demo:** https://soham-pa.github.io/Errsplain/

![Errsplain screenshot](screenshot.png)

## Why I built this

As a beginner, I kept pasting the same cryptic error messages into Google over and over. I wanted something that could give me an instant, plain-English answer instead of digging through five different Stack Overflow threads for the same `TypeError`.

## How it works

1. Paste a raw error message into the input box
2. The app searches a curated dataset (`errors.json`) for a matching error pattern using case-insensitive substring matching — so it still works even if your pasted error includes extra file paths or line numbers
3. If a match is found, it displays the explanation, likely cause, and a fix
4. If no match is found, it shows a fallback message instead of breaking

## Tech stack

- **HTML / CSS / JavaScript** — no frameworks, kept intentionally simple
- **Fetch API** — loads the error dataset client-side
- **Flat JSON file** — acts as a lightweight database, no backend required
- **GitHub Pages** — deployment

## Project structure

```
Errsplain/
├── index.html      # layout, styling, and matching logic
├── errors.json     # curated dataset of common Python/JS errors
└── README.md
```

## Running it locally

Because this project uses `fetch()` to load `errors.json`, opening `index.html` directly (`file://`) will fail silently due to browser security restrictions on local files. Instead:

**Option A — VS Code Live Server**
1. Install the "Live Server" extension
2. Right-click `index.html` → "Open with Live Server"

**Option B — Python's built-in server**
```bash
python3 -m http.server
```
Then open `http://localhost:8000` in your browser.

## What I learned

- Why `fetch()` behaves differently on `file://` vs a local server
- How to design a matching system that's forgiving of real-world, messy input rather than requiring exact string matches
- That writing accurate, beginner-friendly technical explanations is harder than it sounds — every entry in `errors.json` had to be fact-checked, not just written to sound plausible

## Roadmap

- [ ] Expand the error dataset to cover more languages and frameworks
- [ ] Explore a live AI-powered backend so it can explain errors beyond the pre-curated dataset
- [ ] Add a "browse common errors" dropdown for exploration without pasting

## Author

Built by Soham — [LinkedIn](www.linkedin.com/in/soham-paul-136778369) · [GitHub](https://github.com/soham-pa)

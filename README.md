# 📖 Indonesian Word Finder

A browser-based Indonesian word search app that lets you filter words by **prefix** and **suffix**, with an external wordlist (`wordlist.json`) covering common words, scientific terms, and words ending in **-x**.

---

## 📁 File Structure

```
Indonesian-word-connection/
├── kamus-awalan.html   # Main application
├── wordlist.json       # External supplementary wordlist
└── README.md           # This file
```

> **Important:** Both files must be in the same folder for `wordlist.json` to load correctly.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔍 Prefix Search | Find all words starting with a given letter or syllable |
| 🔚 Suffix Filter | Narrow results to words ending with a specific string |
| 🏷️ Category Filter | General, Chemistry, Physics, Biology, Math, Medical, Geography |
| 🔤 Sort Order | Alphabetical (A–Z) or by word length |
| 🟡 Highlighting | Matched prefix & suffix are color-coded in results |
| 📦 External Wordlist | Automatically fetches and merges `wordlist.json` on load |
| 📊 Live Counter | Shows total words and filtered result count in real time |

---

## 🚀 Getting Started

### Clone the Repository

```bash
git clone https://github.com/DevanTQ/Indonesian-word-connection.git
cd Indonesian-word-connection
```

Because the app uses `fetch()` to load `wordlist.json`, it **cannot be opened by double-clicking** the HTML file (`file://` protocol blocks fetch requests). Use one of the following:

**Option 1 — VS Code Live Server**
1. Install the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension
2. Right-click `kamus-awalan.html` → *Open with Live Server*

**Option 2 — Python HTTP Server**
```bash
python -m http.server 8000
# then open: http://localhost:8000/index.html
```

**Option 3 — Node.js**
```bash
npx serve .
```

**Option 4 — GitHub Pages**
Enable GitHub Pages in your repository settings pointing to the `main` branch root. The app will be live at:
```
https://DevanTQ.github.io/Indonesian-word-connection/index.html
```

---

## 📦 wordlist.json

This file contains supplementary words focused on rare or specialised Indonesian vocabulary:

| Prefix | Example Words |
|---|---|
| `ia` | ialah, iambik, iatrogenesis |
| `ai` | aioli, airbag, ain |
| `ah` | ahad, ahli, ahimsa, ahwal |
| `ih` | ihwal, ihram, ihsan |
| `io` | ion, ionisasi, iodin, iodisasi |
| `ion` | ionik, ionosfer, ionofora |
| `on` | onkologi, ontologi, onomatopeia |
| `kn` | knalpot |
| `x` | xenon, xilofon, xerofit, xantofil |
| `y` | yakin, yodium, yttrium, yurisdiksi |
| `z` | zat, zodiak, zoologi, zwitterion |

### Words Ending in `-x` (64 words)
Includes: `latex`, `matrix`, `helix`, `reflex`, `suffix`, `prefix`, `cortex`, `paradox`, `flux`, `borax`, `apex`, `index`, `syntax`, `complex`, `simplex`, `duplex`, `thorax`, `pharynx`, `larynx`, and more.

### JSON Format

```json
{
  "meta": {
    "deskripsi": "...",
    "sumber": "KBBI, scientific terms, technical terms, valid loanwords",
    "versi": "1.0",
    "total": 341
  },
  "words": [
    "ialah",
    "ion",
    "xenon"
  ]
}
```

---

## ➕ Adding Words to the Wordlist

Open `wordlist.json` and append your words to the `words` array:

```json
"words": [
  "existing-word",
  "your-new-word"
]
```

The app automatically merges words from `wordlist.json` with the built-in wordlist every time the page loads.

---

## 🗂️ Built-in Word Categories

The wordlist embedded in `index.html` covers:

- **General** — base words, affixed forms, everyday formal vocabulary
- **Chemistry** — elements, compounds, chemical processes (electrolysis, hydrolysis, oxidation, etc.)
- **Physics** — mechanics, thermodynamics, waves, quantum physics, etc.
- **Biology** — cells, genetics, ecosystems, metabolism, etc.
- **Mathematics** — algebra, calculus, statistics, geometry, etc.
- **Medical** — pathology, pharmacology, diagnosis, anatomy, etc.
- **Geography** — topography, ecosystems, geomorphology, etc.

---

## 🛠️ Tech Stack

- Pure HTML5 + CSS3 + Vanilla JavaScript — no frameworks, no dependencies
- Fonts: [Playfair Display](https://fonts.google.com/specimen/Playfair+Display), [DM Mono](https://fonts.google.com/specimen/DM+Mono), [Literata](https://fonts.google.com/specimen/Literata) via Google Fonts
- Data: `wordlist.json` loaded via the `fetch()` API

---

## 📄 License

Free to use for personal, educational, and Indonesian language research purposes.

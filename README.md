# Sakura Gojuon (Japanese 50 Sounds Learning)

[Start Learning (Live Demo)](https://breeze833.github.io/sakura-gojuon/) | [繁體中文 (Traditional Chinese)](README_zh-TW.md)

This project is a comprehensive learning resource for Japanese Hiragana and Katakana, designed specifically for Traditional Chinese speakers (Taiwan). It uses `reveal.js` to create an interactive slide deck for mastering the 50 sounds.

## Features

### 🌸 Visual & Aesthetic
- **Sakura Theme**: A faint, repeating cherry blossom petal watermark on all slides.
- **Japanese Transitions**: "Sliding Door" effect with a custom "Sakura Fubuki" (cherry blossom blizzard) animation on every slide change.
- **Clean Design**: High-contrast layout using `Noto Serif JP` for Japanese characters and `Noto Sans TC` for Traditional Chinese.

### 🧭 Navigation
- **Global Navigation Bar**: A persistent bar at the bottom of the screen allows quick access to:
  - Home (首頁)
  - Outline (大綱)
  - 50 Sounds Table (五十音圖)
  - Hiragana (平假名)
  - Katakana (片假名)
  - Quiz (測驗)
- **Optimized Controls**: Reveal.js controls are positioned to avoid overlap with the navigation bar.

### 📚 Content Modules
- **50 Sounds Table (Gojūon)**: Complete, compact table displaying Hiragana, Katakana, and Romaji.
- **Stroke Order Animation**:
  - Uses `dmak.js` and KanjiVG data.
  - click on the "play" button or the character to see the stroke order animation.
- **Audio/Pronunciation**:
  - Built with Web Speech API (`window.speechSynthesis`).
  - Click on any Kana or vocabulary word to hear the pronunciation.
  - Automatically prioritizes "Google Japanese" or native `ja-JP` voices.

## Technical Details
- **Framework**: [reveal.js](https://revealjs.com/)
- **Stroke Order**: [dmak.js](https://github.com/mbilbille/dmak) + [KanjiVG](https://kanjivg.tagaini.net/)
- **Icons**: Google Fonts
- **Deployment**: Static HTML (GitHub Pages compatible)

## Setup
1. Clone the repository.
2. **Run a local web server** (Required due to CORS restrictions):
   ```bash
   # Python 3
   python3 -m http.server 8000
   ```
3. Open `http://localhost:8000/src/` in your browser.

   > **Note**: You cannot open `src/index.html` directly in the browser because the application needs to load external Markdown files (`slides.md`), which is blocked by CORS policies on the `file://` protocol.

## Project Background
The development history and technical evolution of this project are documented in [Project History](doc/DEVELOPMENT_HISTORY.md).

Reflection: [My First Experience Developing with Antigravity and Reveal.js](https://medium.com/@breeze833/my-first-experience-developing-with-antigravity-and-reveal-js-acacc4e0400b)

## License
MIT

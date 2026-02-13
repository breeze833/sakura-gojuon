# Japanese 50 Sounds Learning (Traditional Chinese)

## Project Overview
This project aims to create a comprehensive learning resource for Japanese Hiragana and Katakana using reveal.js slides.

## Target Audience
- **Beginners**: Specifically targeted at Taiwanese users with no prior Japanese knowledge.
- **Language**: Traditional Chinese (繁體中文).
- **Learning Goals**: Mastering reading, writing (stroke order), and pronunciation of the 50 sounds.

## Content Structure
1. **Introduction**: Brief overview of the Japanese writing system (Hiragana/Katakana/Kanji).
2. **50 Sounds Table (Gojūon)**: Interactive overview.
3. **Hiragana Detail**:
    - Each character on its own slide.
    - Animation/visual for stroke order.
    - Example vocabulary with pronunciation guide (Rōmaji & Zhuyin if applicable).
4. **Katakana Detail**: Similar structure to Hiragana.
5. **Practice/Quiz**: Simple recognition exercises.

## Technical Specifications
- **Framework**: reveal.js (Markdown based).
- **Styling**:
    - Clean, high-contrast design.
    - Fonts: Priority on correct Japanese glyphs (e.g., `Noto Serif JP`) while maintaining readable Traditional Chinese (`Noto Sans TC`).
    - Large font sizes for clarity.
- **Deployment**: Static HTML presentation.

## User Preferences
- Focus on pedagogical clarity.
- Use of visual aids for stroke order is highly recommended.
- Pronunciation guides should leverage familiar systems (Zhuyin/Bopomofo) where helpful for Taiwanese learners.

## Current Functional Specifications (As of 2026-02-13)

### 1. Visual & Aesthetic
-   **Sakura Watermark**: A faint, repeating cherry blossom petal pattern on the background of all slides (opacity 0.15).
-   **Japanese Transition**:
    -   **Style**: "Sliding Door" effect (`transition: 'slide'`).
    -   **Speed**: Slow (`transitionSpeed: 'slow'`) for an elegant feel.
    -   **Animation**: "Sakura Blizzard" (Sakura Fubuki) particle effect triggers on every slide change.

### 2. Navigation
-   **Global Navigation Bar**: Fixed at the bottom of the screen.
    -   Links: Home (首頁), Outline (大綱), 50 Sounds (五十音圖), Hiragana (平假名), Katakana (片假名), Quiz (測驗).
    -   Style: Semi-transparent white background, distinct from slide content.
-   **Reveal.js Controls**: Positioned 60px from the bottom to avoid overlap with the navigation bar.

### 3. Content Modules
-   **50 Sounds Table**:
    -   Complete table with all rows (A, Ka, Sa, Ta, Na, Ha, Ma, Ya, Ra, Wa, N).
    -   Compact layout: Kana (Hiragana/Katakana) and Romaji displayed on a single line per cell to fit single slides.
-   **Stroke Order Animation**:
    -   Library: `dmak.js` + KanjiVG SVG data.
    -   Behavior: Animates stroke order for Hiragana/Katakana characters on their respective detailed slides.
-   **Audio/Pronunciation**:
    -   **Technology**: Web Speech API (`window.speechSynthesis`).
    -   **Interactivity**: Click on any Kana character or vocabulary word to hear its pronunciation.
    -   **Voice Selection**: Prioritizes "Google Japanese" or `ja-JP` voices for natural accent. Pitch set to 1, Rate set to 0.8 (slightly slower) for clarity.

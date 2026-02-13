# Pronunciation Functionality (Speech API)

This document explains how the text-to-speech (TTS) functionality is implemented in the Japanese 50 Sounds Learning project.

## Overview
The project uses the browser's native **Web Speech API** (`window.speechSynthesis`) to provide audio pronunciation for Hiragana, Katakana, and vocabulary words. This approach avoids the need for external audio files, reducing project size and complexity.

## Implementation Details

### 1. `speakText(text)` Function
The core logic is encapsulated in the `speakText` function within `index.html`.

-   **Browser Support Check**: It first checks if `window.speechSynthesis` is available.
-   **Cancellation**: `window.speechSynthesis.cancel()` is called to stop any currently playing audio before starting new speech.
-   **Utterance Creation**: A `SpeechSynthesisUtterance` object is created with the provided text.
-   **Settings**:
    -   `rate`: Set to `0.8` (slightly slower than default) to help beginners hear the pronunciation clearly.
    -   `pitch`: Set to `1` (normal pitch).

### 2. Voice Selection Strategy
To ensure natural Japanese pronunciation, the system implements a prioritization strategy for voice selection:

1.  **Google Japanese**: Checks for a voice with `lang === 'ja-JP'` and name containing "Google". This is often the highest quality natural voice available in Chrome.
2.  **Native Japanese**: Falls back to any voice with `lang === 'ja-JP'`.
3.  **Default**: If no specific Japanese voice is found, it explicitly sets `utterance.lang = 'ja-JP'`, relying on the browser's default synthesis engine to handle the language code.

### 3. User Interaction (Event Delegation)
Instead of attaching event listeners to every single character, **Event Delegation** is used for better performance. A single listener is attached to the `document`.

-   **Triggers**:
    -   `.kana-main`: The large main character on the slide.
    -   `.jp-char` within `.vocab-item`: The Japanese characters in the vocabulary list.
-   **Behavior**: When a user clicks these elements, the text content is extracted and passed to `speakText()`.

## Code Snippet
```javascript
function speakText(text) {
    if (!window.speechSynthesis) return;
    window.speechSynthesis.cancel();
    
    const utterance = new SpeechSynthesisUtterance(text);
    utterance.rate = 0.8;
    
    const voices = window.speechSynthesis.getVoices();
    const jpVoice = voices.find(v => v.lang === 'ja-JP' && v.name.includes('Google')) ||
                    voices.find(v => v.lang === 'ja-JP');
    
    if (jpVoice) utterance.voice = jpVoice;
    else utterance.lang = 'ja-JP';

    window.speechSynthesis.speak(utterance);
}
```

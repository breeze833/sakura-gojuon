# Sakura Blizzard Transition Animation

This document explains the implementation of the "Sakura Blizzard" (Sakura Fubuki / 桜吹雪) transition effect used in the slides.

## Overview
To enhance the Japanese aesthetic, a custom animation triggers every time the slide changes. A flurry of cherry blossom petals falls across the screen, complementing the "Sliding Door" transition effect of the presentation.

## Implementation Details

### 1. CSS Animation (`@keyframes fall`)
The core animation is defined in CSS keyframes.
-   **Start (0%)**: Petals start above the viewport (`top: -10%`) with `0` opacity.
-   **Fade In (10%)**: Petals quickly fade in (`opacity: 0.8`).
-   **End (100%)**: Petals fall to below the viewport (`top: 110%`) while rotating (`rotate(360deg)`) and drifting horizontally (`translateX(200px)`).

### 2. JavaScript Logic (`triggerSakuraBlizzard`)
The animation is controlled by JavaScript function `triggerSakuraBlizzard()` in `index.html`.

-   **Petal Creation**: Loop creates 30 `div` elements with class `.sakura-petal`.
-   **Randomization**: Each petal gets random values for:
    -   `left`: Starting horizontal position (0-100vw).
    -   `animationDuration`: Speed of fall (1.5s - 3s).
    -   `animationDelay`: Start delay (0 - 0.5s).
    -   `width`/`height`: Size variations (10px - 20px).
-   **Cleanup**: A `setTimeout` removes the petal elements from the DOM after their animation completes to prevent memory leaks.

### 3. Reveal.js Integration
The animation is hooked into the Reveal.js `slidechanged` event.

```javascript
Reveal.on('slidechanged', event => {
    handleSlideChange(event.currentSlide);
    triggerSakuraBlizzard(); // Triggers the visual effect
});
```

### 4. Background Watermark vs. Transition
It is important to distinguish between the **Background** and the **Transition**:
-   **Background**: A static pseudo-element (`.reveal::before`) with a repeating sakura pattern and low opacity (0.15).
-   **Transition**: Dynamic DOM elements created on-the-fly that animate and then disappear.

## Assets
-   `sakura_bg.png`: Used for both the static background watermark and the texture of the falling petals.

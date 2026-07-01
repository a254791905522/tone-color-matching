# Tone Color Matching - Gameplay Fact Card

## Core Screen
A vertical color matching puzzle scene. Top: level title (target name), timer, and difficulty stars. Center: target color swatch (hidden after preview period on higher levels), player's current color swatch, and three sliders (Hue, Saturation, Lightness) with value labels. Bottom: Submit button, Skip button, and level navigation. A result overlay appears after submission showing the target color, player color, hex values, DeltaE difference, score, and stars earned.

## Core Action
1. Read the level brief: target name and a memory hint describing the color.
2. Study the target color preview (shown for levels 1-5 only; levels 6+ hide the preview).
3. Drag the Hue slider (0-360 degrees) to find the right hue.
4. Drag the Saturation slider (0-100%) to set color intensity.
5. Drag the Lightness slider (0-100%) to set how light or dark the color is.
6. Tap Submit to compare your color against the target.
7. Score is based on DeltaE (color difference): lower DeltaE = higher score = more stars.

## Goal
Match the target color as closely as possible using HSL sliders within the 30-second time limit. Score is based on color accuracy (DeltaE). Earn 1-3 stars per level. Unlock the next level by completing the current one.

## Scoring
- Score is calculated from DeltaE (CIE color difference formula).
- Lower DeltaE = closer match = higher score.
- Stars awarded based on score thresholds.
- Best score per level stored locally.
- Total stars tracked across all levels.
- Level progression unlocks sequentially.

## Progression
50 levels organized into 5 themed sets, sequential unlock. Each set introduces new colors and gradually removes the training wheels, until levels 11+ become a pure color memory challenge.

## Tutorial
- Levels 1-5: Show target color preview (full swatch visible).
- Levels 1-10: Show memory hint text describing the target color.
- Levels 6+: Hide preview, rely on memory and hint only.
- Levels 11+: No hint shown, pure color memory challenge.

## Color System
- Hue: 0-360 degrees (red, yellow, green, cyan, blue, magenta cycle).
- Saturation: 0-100% (gray to full color).
- Lightness: 0-100% (black to white, 50% = pure color).
- DeltaE: CIE color difference metric used for scoring.
- Hex color: displayed in results for reference.

## Time Limit
- Each level has a 30-second time limit.
- Timer runs continuously during the level.

## Difficulty
- Difficulty 1-5, scaling every 10 levels.
- Difficulty 1 (levels 1-10): hints shown.
- Difficulty 2 (levels 11-20): no hints.
- Difficulty 3 (levels 21-30).
- Difficulty 4 (levels 31-40).
- Difficulty 5 (levels 41-50): hardest.

## Persistence
All data stored locally via NSUserDefaults:
- Unlocked level (highest completed level).
- Stars per level.
- Best score per level.
- Total stars.
- Sound effects toggle.
- Music toggle.
- Haptics toggle.

## Monetization and Network
- Offline: no network calls.
- No ads, no in-app purchases, no accounts, no analytics, no tracking.

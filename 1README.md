# ECHO

**PixelForge 2026 | Theme: THE UNKNOWN**

> You can only see by making sound. And something in the dark is listening.

## Description

At 3:12 AM, every sound in the city stopped. You enter the silent city in total darkness. The only way to see is to send out an echo pulse that briefly reveals the walls around you, like a bat. But every pulse also tells the creature in the dark exactly where you are. Between pulses, it guesses where you went by learning your movement habits. Find 6 lost recordings, uncover why the city went silent, and return to the Resonator to break the silence.

## Connection to THE UNKNOWN

- **An unknown world:** the city is pitch black. You never see the whole map, only what your echo reveals for a moment.
- **An unknown creature:** the Listener hunts by sound. You only glimpse it in your echo, or when it's already too close.
- **Hidden secrets:** 2 recordings are sealed behind hollow walls that only show their cracks in your echo. Dash into them to break them open.
- **An unsolved mystery:** 6 recordings tell the story of what happened to the city, and the last one reveals the twist.

## How the creature thinks (the AI)

- It hears your **footsteps** 5 times per second (your direction, not your position) and builds an **online Markov model** of your habits: P(next move | current move).
- **Recency weighting** (decay = 0.985) makes old habits fade, so it re-learns you if you change your style.
- When you **pulse**, it hears your exact position.
- **Between pulses**, it moves its guess using only your learned habits (dead reckoning). The red ring labelled "ITS GUESS" shows that guess live.
- Predictable players get found in the dark. Unpredictable players make its guess drift away.
- It grows and changes colour as its accuracy rises: "IT IS LEARNING YOU", "IT UNDERSTANDS YOU", "IT KNOWS YOU".
- **Unpredictability = score:** your multiplier (x1 to x3) is the normalised Shannon entropy of your movement.
- **Adaptive difficulty** ramps up while you're doing well and eases off after you get hit.
- The end screen reports what it learned: your favourite direction, your strongest habit, whether you freeze, and how regular your echo rhythm was.

## Controls

| Action | Keyboard | Mobile |
|---|---|---|
| Move | WASD / Arrows | Drag |
| Echo pulse | Space (or mouse click) | Tap |
| Dash (destroys spawn, stuns the creature, breaks hollow walls) | Shift | Double-tap |
| Journal | J | |
| Pause | P / Esc | |

## Enemies

- **The Listener:** the big creature. Hunts its guess of where you are.
- **Watchers (magenta):** fire at its predicted position when they hear you pulse. Walls block their shots.
- **Crawlers (orange):** chase its guess of where you are.

## Run

Open `index.html` in any browser. No install, no build, no dependencies.

## Tech

Plain HTML5 Canvas and JavaScript in one file. All sound is synthesised with the Web Audio API, so there are no asset files.

## Team

| Member | Contribution |
|---|---|
| Name 1 | AI and creature behaviour |
| Name 2 | Gameplay, map, secrets, recordings |
| Name 3 | Visuals, effects, sound, menus |
| Name 4 | Story, playtesting, presentation |

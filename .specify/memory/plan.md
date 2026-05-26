# Cox Dash — Plan

## Tech Stack
- Single HTML file, no build tools, no framework
- Vanilla JavaScript for all game logic
- HTML5 Canvas for game rendering
- CSS for UI overlays, screens, and animations
- localStorage for score persistence

## Architecture

### Files
- index.html — single file, everything lives here

### Structure
- Canvas layer — game world, characters, obstacles, background
- UI layer — HTML overlays for start screen, HUD, game over screen
- Game engine — vanilla JS game loop using requestAnimationFrame
- State manager — tracks game state: idle, running, gameover
- Score manager — reads and writes to localStorage

## Character Rendering
- All characters and obstacles drawn in CSS and SVG, no image files
- Each character has a 2 frame run animation via CSS keyframes
- Name tags and descriptors rendered as HTML absolutely positioned
  over the canvas

## Game Loop
- requestAnimationFrame drives everything
- Delta time based updates for consistent speed across devices
- Obstacle spawn rate and speed increase as steps climb
- Chaser proximity calculated each frame

## Collision Detection
- Simple bounding box collision between player and obstacles
- Separate detection for chaser catch distance from behind
- Alex juke window calculated on double tap timing

## Leaderboard
- Array of top 10 scores stored in localStorage as JSON
- Read on page load, updated on every game over
- Displayed on start screen and game over screen

## Visual Effects
- Screen shake via CSS transform on canvas container
- Particle burst on collision using small canvas drawn circles
- Slow motion via reducing game loop delta multiplier to 0.2
- Parallax background using two offset scrolling CSS layers

## Controls
- Space or Up Arrow — jump
- Down Arrow — duck
- Left then Right Arrow (quick) — juke Alex Taylor
- Space or click — start and restart

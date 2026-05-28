# Cox Dash

A browser-based endless runner built for the Cox Automotive Step Challenge 2026. Dodge office obstacles and rack up as many steps as possible before wiping out.

## How to Play

Open `index.html` in any browser. No install, no server, no build step.

| Control | Action |
|---|---|
| Space or Up Arrow | Jump over low obstacles |
| Down Arrow | Duck under high obstacles |

Managers chase from behind but they cannot catch you on their own. The only way to die is colliding with an obstacle.

## Obstacles

Obstacles fly in from the right at increasing speed. You must jump or duck to survive each one.

| Obstacle | How to survive |
|---|---|
| Office chair | Jump |
| Stack of papers | Jump |
| Coffee mug | Jump |
| Printer | Jump |
| Flying laptop | Duck |
| Motivational banner | Duck |
| Monitor arm | Duck |

Duck obstacles only start appearing after 600 steps.

## The Managers

Managers appear progressively as your step count climbs. Each one is faster than the last. They chase from behind but stay at a fixed distance, so they create pressure without directly ending your run.

| Manager | Alias | Appears at |
|---|---|---|
| Nick | Iron Man | 0 steps |
| Nikki | Sugar Cat Mom | 100 steps |
| Sam | Oui Oui Baguette | 200 steps |
| Andrew | Wise Sage of Beer | 300 steps |
| Alex Taylor | Aura King / Final Boss | 400 steps |

## Architecture

Everything lives in a single `index.html`. No framework, no bundler, no server required.

| Layer | What it does |
|---|---|
| HTML5 Canvas | Renders the game world: background, characters, obstacles, particles |
| HTML overlays | Start screen, HUD, and game over screen built as positioned divs |
| Game loop | Driven by requestAnimationFrame with delta time for consistent speed |
| State machine | Three states: idle, running, gameover |
| Score system | Top 10 scores saved to localStorage, persists across browser refreshes |

### Rendering

Characters are drawn with Canvas 2D API primitives (arcs, rects, beziers). Nick, Nikki, and Alex Taylor have real face photos clipped to their head circles. Sam and Andrew are fully procedurally drawn.

Background uses two parallax layers scrolling at different speeds. Obstacles and chasers scale with screen height so the game works on any display size.

### Physics

Jump is a fixed upward velocity with constant gravity applied each frame. Duck lowers the player hitbox to roughly half height. Collision detection is axis-aligned bounding boxes with a small inset margin.

### Speed scaling

Obstacle speed and spawn rate both scale with the step counter. Speed approaches a soft cap around 4000 steps. Chaser speeds are fixed per character but each successive manager is notably faster than the previous.

## Repo Scaffold

```
specathon-project/
    my-hackathon-project/
        index.html              the entire game
        README.md               this file
        assets/
            alextaylor.jpeg     face photo used on Alex Taylor character
            nickray.jpeg        face photo used on Nick character
            nikkimunir.jpeg     face photo used on Nikki character
        .specify/               Speckit artifacts (see below)
            memory/
                constitution.md project principles and hard constraints
                specify.md      feature spec written before any code
                plan.md         architecture and tech decisions
                tasks.md        ordered task breakdown used during build
            workflows/
                workflow-registry.json
            integrations/
                claude.manifest.json
                speckit.manifest.json
```

## How We Used Speckit

This project was built using the Speckit workflow inside Claude Code. Speckit is a spec-driven development toolkit that runs a full SDD cycle before touching any code.

### The workflow

1. `/speckit-constitution` — We wrote the non-negotiable project principles first. Single HTML file, no backend, playable in under 10 seconds, working beats perfect. This file acted as a filter for every decision made during the build.

2. `/speckit-specify` — We described the game in plain language: what it is, why it exists, the core user journey, obstacle types, manager roster, and what success looks like. This produced `specify.md`.

3. `/speckit-plan` — Speckit read the spec and produced an architecture plan covering the tech stack, file structure, game loop design, rendering approach, collision detection, and control scheme. This produced `plan.md`.

4. `/speckit-tasks` — Speckit read the spec and plan together and produced a sequenced task list broken into 11 phases from project shell through final testing. Each task was small, testable, and ordered so nothing blocked anything else. This produced `tasks.md`.

5. `/speckit-implement` — Claude Code executed the tasks in order, reading from the spec and plan at each step to stay consistent with the original intent.

The result is that the game design was fully locked before any code was written. When decisions came up during implementation (like adding face photos despite the constitution saying no external assets), there was a clear written baseline to compare against.

Note: the original spec included a juke mechanic for Alex Taylor that was removed during implementation.

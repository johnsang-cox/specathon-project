# Cox Dash — Specify

## What We Are Building
A single file browser based endless runner game where the player
controls Intern Noob, a Cox employee trying to rack up the highest
step count while dodging incoming office items and outrunning
managers who chase from behind. The final boss is Alex Taylor who
requires a special juke mechanic to defeat.

## Why We Are Building It
To create a fun, instantly playable, personally relevant game for
the Cox specathon that ties into the company step challenge, gets
laughs from the room, and generates genuine competition during
the demo.

## Core User Journey
1. Player lands on a start screen showing Cox Dash title and controls
2. Player presses space to start
3. Intern Noob runs automatically, step counter climbs
4. Office items fly in from the right at increasing speed
5. Player jumps over low items with space or up arrow
6. Player ducks under high items with down arrow
7. Manager chasers appear at step milestones closing in from behind
8. Alex Taylor appears at 7500 steps, player must double tap
   left then right arrow quickly to juke him into an office item
9. Successful juke sends Alex flying and awards 500 step bonus
10. Game ends on any collision, score screen shows final step count
11. Player can restart immediately with space

## Incoming Obstacles
All obstacles fly in from the right side of the screen.
Player must jump over or duck under each one.

### Jump over these
- Office chair rolling in
- Stack of performance review papers
- Printer spitting pages
- Coffee mug sliding across the floor

### Duck under these
- Flying laptop thrown in frustration
- Suspended motivational banner
- Swinging monitor arm

## Manager Chasers
Appear from the left and close the gap over time.
Touching them ends the game.

- Nick "Iron Man" — appears at 1000 steps, medium speed
- Nikki "The Pace Killer" — appears at 2000 steps, faster
- Sam "HR is Watching" — appears at 3500 steps, faster still
- Andrew "Mandatory 1on1" — appears at 5000 steps, very fast
- Alex Taylor "The Quarterly Review" — appears at 7500 steps,
  fastest, requires double tap left/right juke to defeat

## Key Features
- Endless runner core loop with automatic scrolling
- Step counter as score, climbs continuously while alive
- Jump and duck mechanics for incoming obstacles
- 4 manager chasers at increasing step milestones
- Alex Taylor final boss with left/right double tap juke mechanic
- Start screen, game over screen, step score display
- Flat illustrated CSS and SVG character sprites with run animations
- Parallax scrolling office corridor background
- Screen shake and particle burst on any collision
- Slow motion dramatic effect on successful Alex juke


## Screens and UI

### Start Screen (popup overlay)
- Cox Dash title with tagline "Don't get caught by your manager"
- Brief one liner explaining controls
- Big Start button
- Shows current leaderboard if scores already exist

### HUD During Game
- Top of screen: 🏃 Steps: 4,271 incrementing in real time
- Always visible throughout the entire run

### Game Over Screen
- Displays final step count
- Shows top 10 leaderboard of all time best runs
- Current run highlighted in the list
- Scores persist via localStorage across browser refreshes
- Restart button and keyboard shortcut displayed

## Data Persistence
- Top 10 scores saved to localStorage
- Each entry stores step count and timestamp
- Survives browser refresh for full specathon day
- No backend required

## What Success Looks Like
- Any person understands how to play in under 10 seconds
- At least one person laughs when they see the character names
- Runs in any browser with zero setup
- Players compete over the high score during the demo

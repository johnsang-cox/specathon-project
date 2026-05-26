# Cox Dash — Tasks

## Order of Operations
Build in this exact order. Do not skip ahead.
Each task must work before moving to the next.

---

## Phase 1: Project Shell (15 mins)
- [ ] Create index.html with basic HTML structure
- [ ] Add canvas element centered on screen
- [ ] Add CSS reset and base styles
- [ ] Add game loop using requestAnimationFrame
- [ ] Confirm blank canvas renders in browser

---

## Phase 2: Background and World (20 mins)
- [ ] Draw scrolling office floor and ceiling on canvas
- [ ] Add parallax office corridor background
- [ ] Add second background layer scrolling at different speed
- [ ] Confirm smooth infinite scroll loop

---

## Phase 3: Player Character (25 mins)
- [ ] Draw Intern Noob as flat CSS SVG sprite on canvas
- [ ] Add 2 frame run animation cycling on game loop
- [ ] Add jump mechanic with gravity and arc
- [ ] Add duck mechanic lowering player hitbox
- [ ] Add name tag "Intern Noob" above character
- [ ] Confirm jump and duck feel responsive

---

## Phase 4: Obstacles (25 mins)
- [ ] Build obstacle spawner that fires from right side
- [ ] Draw office chair obstacle (jump over)
- [ ] Draw stack of papers obstacle (jump over)
- [ ] Draw coffee mug obstacle (jump over)
- [ ] Draw flying laptop obstacle (duck under)
- [ ] Draw motivational banner obstacle (duck under)
- [ ] Add bounding box collision detection for each
- [ ] Increase spawn rate and speed as steps climb
- [ ] Confirm collision ends game

---

## Phase 5: Step Counter HUD (15 mins)
- [ ] Add step counter incrementing every frame while alive
- [ ] Display 🏃 Steps: X at top of screen at all times
- [ ] Style it clean and bold, always visible
- [ ] Confirm it climbs in real time during play

---

## Phase 6: Manager Chasers (30 mins)
- [ ] Draw Nick sprite with name tag "Iron Man"
- [ ] Draw Nikki sprite with name tag "The Pace Killer"
- [ ] Draw Sam sprite with name tag "HR is Watching"
- [ ] Draw Andrew sprite with name tag "Mandatory 1on1"
- [ ] Add chaser spawn logic at step milestones
  - Nick at 1000 steps
  - Nikki at 2000 steps
  - Sam at 3500 steps
  - Andrew at 5000 steps
- [ ] Add chaser close in logic, gap shrinks over time
- [ ] Add collision detection when chaser catches player
- [ ] Confirm each chaser appears and closes the gap correctly

---

## Phase 7: Alex Taylor Final Boss (30 mins)
- [ ] Draw Alex Taylor sprite with name tag
      "The Quarterly Review"
- [ ] Add Alex spawn trigger at 7500 steps
- [ ] Make Alex faster than all other chasers
- [ ] Add double tap left then right detection with timing window
- [ ] On successful juke trigger slow motion effect
- [ ] Show Alex flying into nearest obstacle with comic animation
- [ ] Award 500 step bonus on successful juke
- [ ] Reset Alex and continue loop faster after juke
- [ ] Confirm juke mechanic feels fair and responsive

---

## Phase 8: Screens and UI (25 mins)
- [ ] Build start screen popup overlay
  - Cox Dash title
  - Tagline "Don't get caught by your manager"
  - Controls explanation
  - Start button
  - Show leaderboard if scores exist
- [ ] Build game over screen
  - Final step count large and bold
  - Top 10 leaderboard with current run highlighted
  - Restart button and space bar prompt
- [ ] Wire space bar and button clicks to start and restart

---

## Phase 9: Leaderboard and Persistence (15 mins)
- [ ] On game over save score to localStorage
- [ ] Read top 10 scores from localStorage on load
- [ ] Sort scores highest first
- [ ] Display on both start screen and game over screen
- [ ] Confirm scores survive browser refresh

---

## Phase 10: Visual Polish (20 mins)
- [ ] Add screen shake on any collision
- [ ] Add particle burst on collision impact point
- [ ] Add slow motion delta multiplier on Alex juke
- [ ] Add subtle speed increase visual cue as steps climb
- [ ] Polish character run animations
- [ ] Polish obstacle designs for laughs and clarity

---

## Phase 11: Final Testing (15 mins)
- [ ] Play through full game start to game over
- [ ] Test all obstacles trigger correctly
- [ ] Test all chasers appear at correct milestones
- [ ] Test Alex juke mechanic under pressure
- [ ] Test leaderboard saves and displays correctly
- [ ] Test in Chrome and Safari
- [ ] Fix any bugs found

---

## Total Estimated Time: 4 hours 15 mins
## Buffer remaining: 45 mins for bugs and polish

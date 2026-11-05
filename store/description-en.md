# Flock Leader — Store Submission Materials

## Short description (CrazyGames / GameDistribution / itch.io)

Lead a migrating bird flock south. You whistle, they reorganize: turn the
swarm, scatter to dodge hawks, tighten formation for canyons and storms.
How many birds reach the winter grounds?

(186 characters)

## Details

- Genre: Arcade / Simulation / Casual
- Controls: Mouse / Touch (drag anywhere to fly, tap command buttons). Keyboard:
  WASD/arrows steer, 1/Q TURN (arrow keys + Enter on the compass), 2/E SCATTER,
  3/R GATHER, M mute, P pause.
- Features:
  - Emergent flock behavior (separation / alignment / cohesion) — commands
    reshape parameters, birds never teleport.
  - 3 whistle commands with cooldowns: TURN (compass heading with inertia),
    SCATTER (×4 separation burst vs hawks & peaks), GATHER (×3 cohesion for
    canyons & storms).
  - Hawks with a full AI state machine (approach, predicted dive, catch or
    whiff, retreat, re-strike), storm cells that drain stamina, rest islands
    that heal stragglers, insect swarms to feed on (+2 per bird).
  - 5 seeded procedural levels: Open Skies, The Canyon, Hawk Country,
    Storm Belt, The Long March. Route reachability and difficulty balance
    verified by headless simulation.
  - Scoring: arrived birds ×20 + insects ×2. Survival rate sets stars
    (≥90% ★★★). Best score and stars saved locally.
  - Procedural graphics & sounds (WebAudio chirps, whistles, wind, hawk
    screeches). Cloud parallax, command ripples, warm southern light.
- Tech: Vanilla JavaScript, Canvas 2D, WebAudio. Single-file HTML5, no
  external assets, no frameworks, no tracking, works offline once loaded.
  Mobile touch + desktop keyboard/mouse, landscape-first responsive canvas.

## Tags

birds, flock, boids, simulation, arcade, casual, migration, animals,
single-file, strategy

## CrazyGames submission checklist
- [x] Self-contained index.html (SDK loads only on crazygames domains)
- [x] gameplayStart / gameplayStop / loadingStart / loadingStop / happytime events wired
- [x] Responsive (canvas scales, landscape-first, touch buttons)
- [x] No external links inside gameplay, no analytics
- [ ] Cover: 16:9 1280×720 (suggest: flock V-formation over sunset mountains,
      leader bird highlighted, title top-left)

## itch.io
- Upload zip (rename to flock-leader.zip), mark "This file is playable in
  browser", entry file: index.html, viewport: fits any (landscape recommended),
  kind: html
- Pricing: $0 (donations optional)
- Suggested page copy: "You are the lead bird. The flock has a mind of its
  own — separation, alignment, cohesion. Your whistle is the only command:
  turn them, scatter them, gather them. Bring as many as you can to the
  southern wintering grounds."

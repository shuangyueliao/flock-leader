# Flock Leader

A free, original bird-flock herding game. Single-file HTML5 — no external
assets, no tracking, no ads.

You are the lead bird of a migrating flock. The birds behind you fly with a
mind of their own (boids: separation, alignment, cohesion) — you cannot
control them directly. You whistle, and the whole flock reorganizes:

## Mechanics

- **TURN** — pick a compass heading; the flock banks toward it with inertia
  (each bird steers by limited acceleration, so the swarm turns as a mass).
- **SCATTER** — separation weight bursts ×4 (decaying back over ~2.6s) plus
  an outward impulse: the flock flushes apart to dodge hawks and mountain
  walls. A hawk locked onto a bird aborts its dive when prey bursts apart.
- **GATHER** — cohesion weight ×3 and separation damped: the flock tightens
  into a knot for narrow canyons and storms.
- **Leader bird** — drag anywhere (or WASD/arrows) to fly freely; the flock
  follows your rally point.
- **Stamina & stragglers** — storms drain stamina; tired birds fly slower
  and fall behind, loitering at the screen edge. Rest islands restore the
  flock and stragglers rejoin automatically when the flock passes.
- **Hawks** — approach → lock the nearest bird → predicted dive → catch
  (max 2 birds) or whiff → retreat. Some hawks strike twice.
- **Scoring** — arrived birds ×20 + insects fed ×2 (each bird feeds +2 per
  swarm it crosses). Survival rate sets the stars: ≥90% ★★★, ≥60% ★★,
  ≥30% ★.

5 levels with seeded procedural terrain: Open Skies → The Canyon →
Hawk Country → Storm Belt → The Long March. Every level guarantees a
clearance corridor along the main migration route (verified by simulation:
20 route samples per level, naive-policy survival 60–95%).

## Controls

- Mouse / touch: drag anywhere to fly; command buttons (also works with
  tap-compass aiming for TURN).
- Keyboard: WASD / arrows steer, 1/Q TURN (then arrows + Enter on the
  compass), 2/E SCATTER, 3/R GATHER, M mute, P pause.

## Tech

- One `index.html` (~56 KB), vanilla JS, Canvas 2D, WebAudio (all graphics
  and sounds are procedural — no images, fonts or audio files).
- Boids simulation is DOM-free and unit-tested headless in Node: command
  envelopes (×4 scatter / ×3 gather with decay), eagle state machine
  (approach–dive–miss/kill–retreat–re-strike), terrain reachability,
  default-policy balance, and 60-bird frame-time budget.
- Portal SDK loader is domain-guarded: the CrazyGames SDK loads only on
  crazygames domains, the GameDistribution SDK only on gamedistribution /
  gd.games domains, nothing anywhere else. gameplayStart / gameplayStop /
  happytime are wired behind the same guard.
- Progress, stars and mute preference are stored in localStorage (fully
  optional; the game runs fine with storage blocked).

## Run

Serve the file over HTTP (or open directly) — everything is inline:

```
python3 -m http.server 8000
# http://localhost:8000/
```

## License

Original work — names, mechanics, art and audio are all original.

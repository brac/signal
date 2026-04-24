# Signal

A single-file browser game about deep-space exploration. Navigate your ship through increasingly strange systems, scan anomalies, salvage cargo, and jump deeper into the unknown.

## Play

Serve the directory with any static file server and open it in a browser:

```
python3 -m http.server 8080
```

Then visit `http://localhost:8080`. Opening `index.html` directly also works, though some browsers restrict ES modules over `file://` URLs.

## How to play

**Goal:** Jump deeper into space, scan signals, sell cargo at docks, and survive as long as possible. Item values double with each depth level — the deeper you go, the more each haul is worth.

**Movement**
- Desktop: `WASD` or arrow keys to rotate/thrust, `Space` to warp-jump
- Mobile: on-screen joystick + thrust button; tap the JUMP button to warp

**Signals**
A pulsing signal appears in each system. Fly within range to reveal it, then scan for 3 seconds to collect the item. Signals can be derelict ships, asteroid samples, or alien artifacts — flavor text gets stranger the deeper you go.

**Docking**
When a dock is present, approach the landing pad and dock to sell your cargo and buy upgrades:
- **Cargo upgrades** — add more item slots (up to 10)
- **Jump drive upgrades** — jump multiple depths at once

**Fuel**
- Each jump costs fuel. Deeper jumps cost more.
- Scanning items costs fuel.
- Run out of fuel and you're stranded. Jump home (HOME button) to escape — cost scales with current depth.

**Hull & death**
Colliding with the planet or hazards damages your hull. On death, your ship is recorded as a ghost at that depth. Ghost ships appear in future runs — scan them to recover a memory of what happened there.

**Depth**
The game tracks how deep you've traveled (0–∞). Background color, star tint, planet type, dock availability, and signal content all shift with depth. The flavor text cycles through 10 pools before repeating, each darker and stranger than the last.

## Stack

- **PixiJS v8** — loaded from CDN, no install required
- Single `index.html` — no build step, no bundler, no dependencies
- `localStorage` — used only to persist ghost ship records across sessions

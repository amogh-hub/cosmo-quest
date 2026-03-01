# 🚀 Cosmo Quest

A retro-style space platformer game inspired by classic Mario, built with pure HTML5 Canvas and JavaScript — no frameworks, no dependencies, just one file and a browser.

![Cosmo Quest](https://img.shields.io/badge/game-platformer-7c3aed?style=for-the-badge)
![HTML5](https://img.shields.io/badge/HTML5-Canvas-f97316?style=for-the-badge&logo=html5)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-fbbf24?style=for-the-badge&logo=javascript)
![License](https://img.shields.io/badge/license-MIT-22c55e?style=for-the-badge)

---

## 🎮 Play It

Just open `index.html` in any modern browser. No installation, no build step, no server required.

Or host it instantly with **GitHub Pages**:
1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, root `/`
4. Your game will be live at `https://yourusername.github.io/cosmo-quest`

---

## 🕹️ Controls

| Key | Action |
|-----|--------|
| `←` `→` | Move left / right |
| `Space` or `↑` | Jump |
| `Space` or `↑` (mid-air) | Double jump |

---

## ✨ Features

- **Double jump** — press jump again in mid-air to reach higher platforms
- **Stomp enemies** — land on top of alien enemies to defeat them (+100 pts)
- **Collectible coins** — scattered across the world (+10 pts each)
- **Star power-ups** — rare stars grant an extra life (+500 pts)
- **Gap hazards** — fall into a pit and lose a life
- **Goal flag** — reach the end of the level to advance
- **3 lives** system with respawn
- **Animated pixel-art sprites** — astronaut hero, alien enemies, coins, stars
- **Parallax space background** — twinkling stars and nebula effects
- **Particle effects** — on jumps, stomps, and coin collection
- **Camera tracking** — smooth horizontal scrolling world

---

## 🗂️ Project Structure

```
cosmo-quest/
└── index.html      # Complete game — HTML, CSS, and JS all in one file
```

The entire game lives in `index.html`, organized into clear sections:

| Section | Description |
|---------|-------------|
| CSS | Styling, fonts, layout, and UI |
| Stars canvas | Animated twinkling background |
| Game canvas | Main 800×450 game viewport |
| Sprite data | Pixel-art grid arrays for player and enemies |
| Level builder | `buildLevel(n)` — generates platforms, enemies, coins, gaps |
| Physics engine | Gravity, velocity, AABB collision detection |
| Input handler | Keyboard state tracking |
| Game loop | `update()` + `draw()` called via `requestAnimationFrame` |
| HUD | Score, lives, level, coins displayed above the canvas |

---

## 🧠 How It Works

### Physics
The game uses simple Euler integration for movement. Each frame, gravity is added to vertical velocity (`vy`), and velocity is added to position. Collision uses AABB (Axis-Aligned Bounding Box) overlap detection, resolving on the axis with the smallest overlap.

### Level Generation
`buildLevel(level)` procedurally places:
- Ground tiles (with deliberate gaps for challenge)
- Floating platforms at varied heights
- Enemies patrolling between defined start/end X positions
- Coins on platforms and on the ground
- 3 hidden star power-ups per level

### Rendering
All rendering uses the HTML5 Canvas 2D API. Sprites are defined as 2D color arrays and painted pixel-by-pixel. The camera is a simple horizontal offset (`cameraX`) subtracted from all world X positions during drawing.

---

## 🎨 Visual Style

- **Theme:** Deep space — purples, indigos, gold accents
- **Font:** [Press Start 2P](https://fonts.google.com/specimen/Press+Start+2P) (Google Fonts)
- **Palette:**
  - Background: `#0a0015` → `#1a0040`
  - Platforms: `#7c3aed` / `#4c1d95`
  - Player: Gold helmet, purple suit
  - Enemies: Green aliens with red antennae
  - Coins: `#ffd700` with glow
  - Stars: White with bloom effect

---

## 📈 Scoring

| Action | Points |
|--------|--------|
| Collect a coin | +10 |
| Stomp an enemy | +100 |
| Collect a star | +500 |
| Complete a level | +1000 |

---

## 🛠️ Extending the Game

Want to add more? Here are some easy starting points:

- **New levels:** Modify `buildLevel()` — add more gap configs, enemy placements, or tighter platform gaps for higher levels
- **New enemies:** Add a new sprite array and movement pattern in the enemies update loop
- **Sound effects:** Use the [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) to generate retro beeps on jump/collect
- **Mobile controls:** Add on-screen touch buttons that set the same `keys` object
- **Persistent high score:** Use `localStorage.setItem('highScore', score)` to save between sessions

---

## 📄 License

MIT — free to use, modify, and distribute.

---

*Built with ❤️ and vanilla JavaScript. No frameworks were harmed in the making of this game.*

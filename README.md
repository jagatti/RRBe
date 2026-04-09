# RRBe — Race & Rhythm Beat

```
╔══════════════════════════════════════════════════════════════╗
║  ██████╗ ██████╗ ██████╗ ███████╗                           ║
║  ██╔══██╗██╔══██╗██╔══██╗██╔════╝                           ║
║  ██████╔╝██████╔╝██████╔╝█████╗                             ║
║  ██╔══██╗██╔══██╗██╔══██╗██╔══╝                             ║
║  ██║  ██║██║  ██║██████╔╝███████╗                           ║
║  ╚═╝  ╚═╝╚═╝  ╚═╝╚═════╝ ╚══════╝  Race & Rhythm Beat      ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║          ·  ·  ·  ·  ·  [VANISHING POINT]  ·  ·  ·  ·      ║
║        /  ·  ·  · PLATFORM ·  ·  ·  ·  \                    ║
║       / ·  · ██HIGH██ ·  ·  ·  · LOW·  · \                  ║
║      / ·  · ·  · ·  · ·  BARRIER  · · ·   \                 ║
║     /══|══════|══════|══════|══════|══════|══\               ║
║    /   |      |      |      |      |      |   \              ║
║   /    | LANE0| LANE1| LANE2| LANE3| LANE4|    \             ║
║  /     |      |      |   🚗 |      |      |     \            ║
║ /══════|══════|══════|══════|══════|══════|══════\           ║
║                        [PLAYER]                              ║
╚══════════════════════════════════════════════════════════════╝
```

A neon-soaked cyberpunk racer where you dodge obstacles to the beat of
procedurally-generated electronic music. Inspired by R2BEAT.

---

## 🎮 How to Play

Open `index.html` in any modern web browser (Chrome, Firefox, Edge, Safari).  
No server, no install, no dependencies — just open the file and play.

```
file:///path/to/RRBe/index.html
```

---

## ⌨️ Controls

| Key | Action |
|-----|--------|
| `←` Left Arrow | Move to the left lane |
| `→` Right Arrow | Move to the right lane |
| `↑` Up Arrow | **Jump** — clear high walls or land on platforms |
| `↓` Down Arrow | **Crouch** — slide under low barriers |
| `SPACE` | Start the game |
| `R` | Restart after Game Over |

---

## 🕹️ Gameplay

### Obstacle Types

| Obstacle | Color | How to Avoid |
|----------|-------|--------------|
| **LOW barrier** | 🟠 Red/Orange | Crouch (↓) or jump over (↑) |
| **HIGH wall** | 🟣 Magenta/Red | Jump (↑) or change lane |
| **PLATFORM** | 🟢 Cyan/Green | Jump (↑) onto it for bonus points |

- **5 lanes** — move left and right to dodge incoming obstacles
- Obstacles are generated in sync with the **128 BPM** beat
- Successfully avoiding an obstacle in the same lane rewards points and builds your **combo**
- Changing lanes to avoid obstacles also scores points
- Getting hit breaks your combo and costs a **life** (3 lives total)
- Speed increases the further you travel — survive as long as you can!

---

## 🎵 Music

BGM is entirely synthesized at runtime using the **Web Audio API** — no external files required.

- **BPM**: 128
- **Kick drum**: 4-on-the-floor pattern
- **Snare**: Beats 2 & 4
- **Hi-hat**: 16th-note pattern with open hi-hats on off-beats
- **Bass**: Sawtooth synth bass (8th-note groove)
- **Lead Synth**: Square-wave melody on a pentatonic scale

The background and lane visuals pulse in sync with each beat for an immersive rhythm experience.

---

## 🖥️ Technical Details

- **Single file**: Everything runs from `index.html` — HTML, CSS, and JavaScript inline
- **HTML5 Canvas**: Pseudo-3D perspective rendering (vanishing-point projection)
- **Web Audio API**: Fully procedural drum machine + synth engine
- **Vanilla JS**: Zero external libraries or CDN dependencies
- **Neon/Cyberpunk aesthetic**: Glow effects via `shadowBlur`, neon color palette (cyan, magenta, orange)
- **Particle system**: Hit/score feedback bursts

---

## 📊 Scoring

| Action | Base Points |
|--------|-------------|
| Pass a LOW obstacle (crouch) | 20 |
| Clear a HIGH obstacle (jump) | 25 |
| Land on a PLATFORM | 30 |
| Weave past obstacle (different lane) | 15 |
| Obstacle passes by | 10 |
| Distance traveled | +1 per unit |

All base points are multiplied by a **combo multiplier**: `floor(combo ÷ 10 + 1)`.  
Every 10 consecutive successes adds ×1 to your score multiplier.

---

## 🚀 Requirements

- Any modern browser with HTML5 Canvas + Web Audio API support
- Keyboard (mouse/touch not required)
- Recommended: Chrome 90+ or Firefox 88+

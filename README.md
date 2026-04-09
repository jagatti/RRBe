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
║               ·  · [VANISHING POINT] ·  ·                   ║
║              / ·  ·  ·  ·  ·  ·  ·  · \                    ║
║             / ·  ·  ·  🔶ARCH·  ·  ·  · \                  ║
║            / ·  ·  · 🔷BLOCK · ·  ·  ·   \                 ║
║           / ·  🟠PYLON ·  · PYLON🟠 ·  ·  \                ║
║          /═══════════════════════════════════\               ║
║         /        ← [JUDGMENT LINE] →         \              ║
║        /              🏃 CHARACTER              \            ║
║       /          [←]   [↓]   [↑]   [→]          \           ║
║      /═══════════════════════════════════════════\           ║
║                                                              ║
║     判定 94.5%          649 COMBO         SCORE: 48200      ║
║     PERFECT  312                        [===ACCURACY===]    ║
║     GREAT     45                        [====LIFE=====]     ║
║     GOOD      12                                            ║
╚══════════════════════════════════════════════════════════════╝
```

An R2BEAT-inspired rhythm running game. Your character runs forward on a
neon-lit 3D track while obstacles rush toward you — dodge pylons, duck
under arches, and jump over blocks to the beat!

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
| `←` Left Arrow | **Dodge left** — avoid a pylon on the right side |
| `→` Right Arrow | **Dodge right** — avoid a pylon on the left side |
| `↓` Down Arrow | **Duck** — crouch under an overhead arch |
| `↑` Up Arrow | **Jump** — leap over a ground block |
| `SPACE` | Start the game |
| `R` / `SPACE` | Restart after Game Over or Results |

---

## 🕹️ Gameplay

Your character runs forward on a single center lane. Obstacles scroll from
the vanishing point toward you. Press the **correct arrow key** when each
obstacle reaches the **judgment zone** near the character:

### Obstacle Types

| Obstacle | Appearance | How to Avoid | Key |
|----------|-----------|-------------|-----|
| 🟠 **Pylon (right)** | Orange cone on the RIGHT side | Dodge LEFT | `←` |
| 🟠 **Pylon (left)** | Orange cone on the LEFT side | Dodge RIGHT | `→` |
| 🔵 **Arch** | Cyan overhead gate | DUCK under | `↓` |
| 🟢 **Block** | Green ground barrier | JUMP over | `↑` |

### Timing & Judgments

| Judgment | Timing Window | Score | Combo | Health |
|----------|--------------|-------|-------|--------|
| **PERFECT** | ±45 ms | 100 pts | ✅ continues | +1 |
| **GREAT** | ±90 ms | 80 pts | ✅ continues | +0.5 |
| **GOOD** | ±140 ms | 50 pts | ✅ continues | ±0 |
| **BAD** | ±195 ms | 20 pts | ❌ resets | −3 |
| **MISS** | >240 ms | 0 pts | ❌ resets | −5 |

### Scoring
- Base score × **combo multiplier** (`floor(combo ÷ 10 + 1)`)
- Every 10 consecutive successful dodges increases the multiplier

### Health & Survival
- Health starts at **100**
- PERFECT/GREAT heal slightly, BAD/MISS damage health
- If health reaches **0** → **GAME OVER**
- Survive the full 90-second song → **STAGE CLEAR** with grade!

### Grades

| Accuracy | Grade |
|----------|-------|
| ≥ 95% | **S** |
| ≥ 90% | **A** |
| ≥ 80% | **B** |
| ≥ 70% | **C** |
| ≥ 60% | **D** |
| < 60% | **F** |

---

## 🎵 Music

BGM is entirely synthesized at runtime using the **Web Audio API** — no
external audio files required.

- **BPM**: 128
- **Kick drum**: 4-on-the-floor pattern
- **Snare**: Beats 2 & 4
- **Hi-hat**: 16th-note pattern with open hi-hats on off-beats
- **Bass**: Sawtooth synth bass (8th-note groove)
- **Lead Synth**: Square-wave melody on a pentatonic scale

Obstacles are generated in sync with the beat, with difficulty ramping from
simple half-note patterns to dense 16th-note sequences.

---

## 🖥️ Technical Details

- **Single file**: Everything runs from `index.html` — HTML, CSS, and
  JavaScript inline
- **HTML5 Canvas** (960×640): Pseudo-3D perspective road with vanishing-point
  projection
- **Web Audio API**: Fully procedural drum machine + synth engine
- **Vanilla JS**: Zero external libraries or CDN dependencies
- **312 auto-generated obstacles** across 48 bars (90 seconds)
- **Neon/Cyberpunk aesthetic**: Glow effects, particle bursts, beat flash
- **Character animation**: Dodge left/right, duck, and jump reactions

### Obstacle Colors

| Obstacle | Color |
|----------|-------|
| Pylon (left/right) | 🟠 Orange |
| Arch (overhead) | 🔵 Cyan/Blue |
| Block (ground) | 🟢 Green |

---

## 🚀 Requirements

- Any modern browser with HTML5 Canvas + Web Audio API support
- Keyboard (mouse/touch not required)
- Recommended: Chrome 90+ or Firefox 88+

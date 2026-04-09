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
║              / ·  ·  ← · ·  → · ·  · \                     ║
║             / ·  ·  ·  ·  ·  ↑ ·  ·  · \                   ║
║            / ·  ←  ·  ·  ·  ·  ·  →  ·  \                  ║
║           / ·  ·  ·  ↓  ·  ·  ·  ·  ·  · \                 ║
║          /═══════════════════════════════════\               ║
║         / [←]    [↓]    [↑]    [→]  ← JUDGE \              ║
║        /     ← LANE  ↓ LANE  ↑ LANE  → LANE  \             ║
║       /              🏃 CHARACTER               \            ║
║      /═══════════════════════════════════════════\           ║
║                                                              ║
║     判定 94.5%          649 COMBO         SCORE: 48200      ║
║     PERFECT  312                        [===ACCURACY===]    ║
║     GREAT     45                        [====LIFE=====]     ║
║     GOOD      12                                            ║
╚══════════════════════════════════════════════════════════════╝
```

An R2BEAT-inspired rhythm running game. A character runs on a neon-lit 3D
track while arrow-marked notes scroll toward you — press the matching arrow
key with perfect timing to the beat!

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
| `←` Left Arrow | Hit **← notes** on the left lane |
| `↓` Down Arrow | Hit **↓ notes** on the down lane |
| `↑` Up Arrow | Hit **↑ notes** on the up lane |
| `→` Right Arrow | Hit **→ notes** on the right lane |
| `SPACE` | Start the game |
| `R` / `SPACE` | Restart after Game Over or Results |

---

## 🕹️ Gameplay

Notes scroll from the vanishing point toward the **judgment line** near the
bottom of the screen. Each note shows an arrow (← ↓ ↑ →) indicating which
key to press. Hit the matching key when the note reaches the judgment line!

### Timing & Judgments

| Judgment | Timing Window | Score | Combo | Health |
|----------|--------------|-------|-------|--------|
| **PERFECT** | ±42 ms | 100 pts | ✅ continues | +1 |
| **GREAT** | ±84 ms | 80 pts | ✅ continues | +0.5 |
| **GOOD** | ±130 ms | 50 pts | ✅ continues | ±0 |
| **BAD** | ±180 ms | 20 pts | ❌ resets | −3 |
| **MISS** | >220 ms | 0 pts | ❌ resets | −5 |

### Scoring
- Base score × **combo multiplier** (`floor(combo ÷ 10 + 1)`)
- Every 10 consecutive hits increases the multiplier

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

Notes are generated in sync with the beat, with difficulty ramping from
simple quarter-note patterns to dense 16th-note runs.

---

## 🖥️ Technical Details

- **Single file**: Everything runs from `index.html` — HTML, CSS, and
  JavaScript inline
- **HTML5 Canvas** (960×640): Pseudo-3D perspective road with vanishing-point
  projection
- **Web Audio API**: Fully procedural drum machine + synth engine
- **Vanilla JS**: Zero external libraries or CDN dependencies
- **312 auto-generated notes** across 48 bars (90 seconds)
- **Neon/Cyberpunk aesthetic**: Glow effects, particle bursts, beat flash

### Lane Colors

| Lane | Arrow | Color |
|------|-------|-------|
| Left | ← | 🩷 Pink/Magenta |
| Down | ↓ | 🩵 Cyan/Blue |
| Up | ↑ | 💚 Green |
| Right | → | 🧡 Orange/Yellow |

---

## 🚀 Requirements

- Any modern browser with HTML5 Canvas + Web Audio API support
- Keyboard (mouse/touch not required)
- Recommended: Chrome 90+ or Firefox 88+

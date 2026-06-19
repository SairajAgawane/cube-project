<div align="center">

# 🧩 The Cube

**A beautifully crafted 3D Rubik's Cube simulator — solve it, scramble it, theme it.**
Runs entirely in the browser, no build tools required.

`Three.js` · `Vanilla JS` · `No Build Tools`

![Version](https://img.shields.io/badge/version-0.99.2-7c5cfc?style=flat-square)
![Three.js](https://img.shields.io/badge/Three.js-r95-4eff88?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-ffa544?style=flat-square)
![Vanilla JS](https://img.shields.io/badge/Vanilla-JS-cc88ff?style=flat-square)

[🚀 Live Demo](https://cube-project.vercel.app/)

</div>

---

## ✨ Features

| | |
|---|---|
| 🎲 **Multi-Size Cubes** | Choose between 2×2, 3×3, 4×4, or 5×5. Each size tracks its own stats independently. |
| 🎨 **5 Built-in Themes** | Switch between Cube, Erno, Dust, Camo, and Rain palettes in a single tap. |
| 🖌️ **Custom Theme Editor** | Full HSL color picker — tap any face and dial in exactly the color you want. |
| ⏱️ **Timer & Stats** | Tracks best time, Ao5, Ao12, and Ao25 averages. All data persists across sessions. |
| 🔀 **Auto Scrambler** | Easy / Medium / Hard scramble difficulty — proper WCA-style move notation. |
| ⚙️ **Flip Animations** | Three flip styles: Swift, Smooth, and Bounce. Camera FOV goes from ortho to wide. |
| 📱 **Touch & Mouse** | Full drag support on desktop and mobile. Drag on a face to rotate a layer; drag outside for the whole cube. |
| 🎉 **Confetti on Solve** | Celebratory particle burst and best-time trophy when you crack it. |

---

## 🎮 How to Play

Double-tap the cube to begin. The timer starts on your first move. Solve all six faces to win.

| Action | Gesture / Control |
|---|---|
| Rotate a layer | `Drag` on a cube face |
| Rotate the whole cube | `Drag` outside the cube |
| Start a new game | `Double-tap` the cube |
| Open settings | `⚙️` icon — bottom right |
| View stats | `🏆` icon — bottom left |
| Back to menu | `←` back icon |

---

## 🎨 Themes

Five curated palettes, each with a distinct personality. Or build your own with the HSL picker.

| Face | Position | Default Color |
|---|---|---|
| U | Top | ⬜ White (`#f5f5f0`) |
| F | Front | 🟥 Red (`#e03030`) |
| R | Right | 🟦 Blue (`#2a6fdb`) |
| L | Left | 🟩 Green (`#2db058`) |
| D | Bottom | 🟨 Yellow (`#f0c020`) |
| B | Back | 🟧 Orange (`#f07020`) |

---

## 📊 Stats & Records

All stats are tracked per cube size and saved automatically to `localStorage` — no account needed.

- ✅ **Solves** — tracked
- 🥇 **Best** — personal record
- 📈 **Ao5** — rolling average
- 📊 **Ao12** — rolling average
- 🔢 **Ao25** — rolling average

---

## 🛠️ Tech Stack

- **Three.js r95** — 3D rendering
- **Vanilla JS (ES6+)** — no frameworks
- **CSS3 Animations** — UI transitions
- **LocalStorage** — stats & settings persistence
- **requestAnimationFrame** — animation loop
- **WebGL** — graphics backend
- **Vercel** — hosting / deployment

---

## 📁 Project Structure

No build step. Clone and open in a browser.

```
the-cube/
├── index.html          # app shell & UI markup
├── style.css           # fonts, sliders, layout
├── script.js           # full game logic
│   ├── AnimationEngine # rAF loop & tweening
│   ├── World           # Three.js scene, camera, lighting
│   ├── Cube             # 3D model & geometry
│   ├── Controls          # drag / touch / layer rotation
│   ├── Scrambler          # move generation & notation
│   ├── Timer               # game clock
│   ├── Scores               # stats & averages
│   ├── Storage                # localStorage persistence
│   ├── Themes                  # color schemes
│   └── Confetti                 # celebration particles
└── README.md
```

---

## 🚀 Run Locally

No build step required. Clone, serve, and play.

```bash
# Clone the repo
git clone https://github.com/your-username/the-cube.git
cd the-cube

# Serve locally
npx serve .
# or
python -m http.server 8080
```

### Deploy to Vercel

```bash
npm install -g vercel
vercel
```

---

## 📄 License

MIT License

---

<div align="center">

Built with ❤️ and [Three.js](https://threejs.org/) · Inspired by Ernő Rubik (1974)

[cube-project.vercel.app](https://cube-project.vercel.app/)

</div>

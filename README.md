<div align="center">

<img src="readme-assets/hero-cube.svg" alt="Animated colorful Rubik's Cube" width="100%" />

# 🧩 THE CUBE

### A colorful 3D Rubik’s Cube simulator — scramble it, rotate it, theme it, solve it.

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=17&duration=2600&pause=850&color=22D3EE&center=true&vCenter=true&width=700&lines=Experience+3D+Rubik's+Cube.;Scramble.+Rotate.+Solve.;Customize+Your+Cube.;Challenge+Your+Best+Time.;Enter+the+World+of+Cubing." alt="Animated Cube project tagline" />

<br />

![Version](https://img.shields.io/badge/version-0.99.2-8B5CF6?style=for-the-badge)
![Three.js](https://img.shields.io/badge/Three.js-r95-4EFF88?style=for-the-badge)
![Vanilla JS](https://img.shields.io/badge/Vanilla-JS-FFD93D?style=for-the-badge)
![WebGL](https://img.shields.io/badge/WebGL-3D-22D3EE?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-FF9F43?style=for-the-badge)

[🚀 **Play the Live Demo**](https://cube-project.vercel.app/) · [📦 **View the Repository**](https://github.com/SairajAgawane/cube-project)

</div>

![Neon section separator](readme-assets/neon-separator.svg)

## ✨ FEATURES

| Feature | What it does |
|---|---|
| 🎲 **Multi-size cubes** | Choose between 2×2, 3×3, 4×4, or 5×5. Each size tracks its own stats independently. |
| 🎨 **Five built-in themes** | Switch between Cube, Erno, Dust, Camo, and Rain palettes in a single tap. |
| 🖌️ **Custom theme editor** | Use the HSL color picker to tune the color of any cube face. |
| ⏱️ **Timer & statistics** | Tracks solves, best time, Ao5, Ao12, and Ao25. Data persists across sessions. |
| 🔀 **Automatic scrambler** | Choose Easy, Medium, or Hard with WCA-style move notation. |
| ⚙️ **Three flip animations** | Choose Swift, Smooth, or Bounce camera transitions from orthographic to wide FOV. |
| 📱 **Touch & mouse controls** | Drag on a face to rotate a layer; drag outside the cube to rotate the whole cube. |
| 🎉 **Solve celebration** | Trigger a confetti particle burst and best-time trophy when the cube is solved. |

![Neon section separator](readme-assets/neon-separator.svg)

## 🎮 HOW TO PLAY

Double-tap the cube to begin. The timer starts on your first move. Solve all six faces to win.

| Action | Gesture / control |
|---|---|
| Rotate a layer | `Drag` on a cube face |
| Rotate the whole cube | `Drag` outside the cube |
| Start a new game | `Double-tap` the cube |
| Open settings | `⚙️` icon — bottom right |
| View stats | `🏆` icon — bottom left |
| Back to menu | `←` back icon |

![Animated cube controls](readme-assets/hero-cube.svg)

![Neon section separator](readme-assets/neon-separator.svg)

## 🎨 THEMES & CUSTOMIZATION

Five curated palettes give the simulator different personalities, while the custom HSL editor lets you tune individual face colors.

![Cube face color palette](readme-assets/theme-palette.svg)

| Face | Position | Default color |
|---|---|---|
| U | Top | ⬜ White (`#f5f5f0`) |
| F | Front | 🟥 Red (`#e03030`) |
| R | Right | 🟦 Blue (`#2a6fdb`) |
| L | Left | 🟩 Green (`#2db058`) |
| D | Bottom | 🟨 Yellow (`#f0c020`) |
| B | Back | 🟧 Orange (`#f07020`) |

![Neon section separator](readme-assets/neon-separator.svg)

## 🏆 STATS & RECORDS

All statistics are tracked per cube size and saved automatically to `localStorage` — no account required.

| Record | Meaning |
|---|---|
| ✅ **Solves** | Number of completed solves |
| 🥇 **Best** | Personal best time |
| 📈 **Ao5** | Rolling average of five solves |
| 📊 **Ao12** | Rolling average of twelve solves |
| 🔢 **Ao25** | Rolling average of twenty-five solves |

![Neon section separator](readme-assets/neon-separator.svg)

## 🛠️ TECHNOLOGY STACK

| Technology | Role |
|---|---|
| [Three.js r95](https://threejs.org/) | 3D scene, camera, lighting, geometry, and cube rendering |
| Vanilla JavaScript (ES6+) | Game logic and interaction state |
| CSS3 animations | Interface transitions and responsive presentation |
| WebGL | Browser graphics backend |
| `requestAnimationFrame` | Render and animation loop |
| `localStorage` | Stats and settings persistence |
| Vercel | Live deployment |

![Three.js](https://img.shields.io/badge/Three.js-r95-8B5CF6?style=flat-square&logo=threedotjs&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-FFD93D?style=flat-square&logo=javascript&logoColor=111827)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![WebGL](https://img.shields.io/badge/WebGL-22D3EE?style=flat-square)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)

![Neon section separator](readme-assets/neon-separator.svg)

## 📁 PROJECT STRUCTURE

No build step is required.

```text
cube-project/
├── index.html          # App shell and UI markup
├── style.css           # Fonts, sliders, layout, and responsive styling
├── script.js           # Full game logic
│   ├── AnimationEngine # rAF loop and tweening
│   ├── World           # Three.js scene, camera, and lighting
│   ├── Cube            # 3D model and geometry
│   ├── Controls        # Drag, touch, and layer rotation
│   ├── Scrambler       # Move generation and notation
│   ├── Timer           # Game clock
│   ├── Scores          # Stats and averages
│   ├── Storage         # localStorage persistence
│   ├── Themes          # Color schemes
│   └── Confetti         # Celebration particles
├── readme-assets/
│   ├── hero-cube.svg
│   ├── theme-palette.svg
│   └── neon-separator.svg
└── README.md
```

![Neon section separator](readme-assets/neon-separator.svg)

## 🚀 RUN LOCALLY

No build tools are required. Clone the repository and serve the static files.

```bash
git clone https://github.com/SairajAgawane/cube-project.git
cd cube-project

# Option 1: static server through npx
npx serve .

# Option 2: Python's built-in server
python -m http.server 8080
```

Then open the URL printed by your local server.

### Deploy to Vercel

```bash
npm install -g vercel
vercel
```

The live deployment is available at [cube-project.vercel.app](https://cube-project.vercel.app/).

![Neon section separator](readme-assets/neon-separator.svg)

## 📄 LICENSE

This project is released under the [MIT License](https://opensource.org/licenses/MIT).

<div align="center">

Built with ❤️ and [Three.js](https://threejs.org/) · Inspired by Ernő Rubik (1974)

[🚀 cube-project.vercel.app](https://cube-project.vercel.app/)

</div>


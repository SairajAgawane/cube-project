# 🧩 The Cube

> A beautifully crafted 3D Rubik's Cube simulator built with Three.js — solve it, scramble it, theme it.

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-cube--project.vercel.app-black?style=for-the-badge)](https://cube-project.vercel.app/)
[![Version](https://img.shields.io/badge/Version-0.99.2-blue?style=for-the-badge)](#)
[![Three.js](https://img.shields.io/badge/Three.js-r95-brightgreen?style=for-the-badge)](https://threejs.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](#)

---

## 📸 Preview

![The Cube - Screenshot](./preview.png)

---

## ✨ Features

| Feature | Description |
|---|---|
| 🎲 **Multi-Size Cubes** | Play with 2×2, 3×3, 4×4, or 5×5 cubes |
| 🎨 **5 Built-in Themes** | Cube, Erno, Dust, Camo, Rain |
| 🖌️ **Custom Theme Editor** | Pick any color with HSL controls |
| ⏱️ **Timer & Stats** | Track best times, averages (5, 12, 25), and total solves |
| 🔀 **Auto Scrambler** | Adjustable scramble difficulty |
| 💾 **Auto Save** | Game state persists across browser sessions |
| 📱 **Touch & Mouse** | Full support for both desktop and mobile |
| 🏆 **Best Time Trophy** | Celebrate your personal records |
| 🎉 **Confetti Animation** | Fires on a successful solve |
| ⚙️ **Flip Animations** | Swift, Smooth, or Bounce flip styles |
| 🔭 **Camera FOV Control** | Orthographic to wide perspective |

---

## 🚀 Live Demo

👉 **[cube-project.vercel.app](https://cube-project.vercel.app/)**

Double-tap the cube to start a new game!

---

## 🎮 How to Play

1. **Open** the app and **double-tap** the cube to begin
2. The cube is **auto-scrambled** — your timer starts on your first move
3. **Drag** on the cube's faces to rotate layers
4. **Drag** outside the cube to rotate the whole cube
5. Solve all six faces to **win** 🎉
6. Tap **Back** to return to the menu and save your time

### Controls

| Action | Gesture |
|---|---|
| Rotate a layer | Drag on a cube face |
| Rotate the whole cube | Drag outside the cube |
| Start a new game | Double-tap the cube |
| Open settings | ⚙️ icon (bottom right) |
| View stats | 🏆 icon (bottom left) |
| Back to menu | ← icon |

---

## 🛠️ Tech Stack

- **[Three.js r95](https://threejs.org/)** — 3D rendering & WebGL
- **Vanilla JavaScript (ES6+)** — No frameworks, no build tools
- **Custom Animation Engine** — `requestAnimationFrame`-based loop with tweening
- **CSS3** — UI transitions and layout
- **LocalStorage** — Game state and preferences persistence
- **Vercel** — Deployment & hosting

---

## 📁 Project Structure

```
the-cube/
├── index.html       # App shell & UI markup
├── style.css        # All styles (BungeeFont, range sliders, UI layout)
├── script.js        # Full game logic
│   ├── AnimationEngine  # rAF-based animation loop
│   ├── World            # Three.js scene, camera, lighting
│   ├── Cube             # 3D cube model & geometry
│   ├── Controls         # Drag/touch input & layer rotation
│   ├── Scrambler        # Move generation & notation
│   ├── Transition       # UI animations & tweens
│   ├── Timer            # Game clock
│   ├── Scores           # Stats & averages
│   ├── Storage          # LocalStorage persistence
│   ├── Themes           # Color schemes
│   ├── ThemeEditor      # HSL color picker
│   └── Confetti         # Celebration particles
└── README.md
```

---

## 🧑‍💻 Getting Started

No build step required — it's pure HTML, CSS, and JavaScript.

### Run Locally

```bash
# Clone the repository
git clone https://github.com/your-username/the-cube.git

# Navigate into the project
cd the-cube

# Serve with any static file server, e.g.:
npx serve .
# or
python -m http.server 8080
```

Then open `http://localhost:8080` in your browser.

### Deploy to Vercel

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
vercel
```

---

## 🎨 Themes

| Theme | U (Top) | F (Front) | R (Right) | L (Left) | D (Bottom) | B (Back) |
|---|---|---|---|---|---|---|
| **Cube** | White | Red | Blue | Green | Yellow | Orange |
| **Erno** | White | Crimson | Royal Blue | Kelly Green | Gold | Flame |
| **Dust** | Cream | Burgundy | Sage | Olive | Sand | Terracotta |
| **Camo** | Off-white | Dark Brown | Army Green | Forest | Khaki | Tan |
| **Rain** | Snow | Crimson | Teal | Yellow-green | Amber | Coral |

You can also **create your own theme** using the built-in HSL color picker — tap any face in theme mode to edit that color.

---

## 📊 Scoring & Stats

The app tracks the following per cube size (2×2 through 5×5):

- ✅ Total solves
- 🥇 Best time
- 📈 Average of 5, 12, and 25 solves
- 💾 All scores saved automatically to localStorage

---

## ⚙️ Preferences

| Setting | Options |
|---|---|
| Cube Size | 2×2, 3×3, 4×4, 5×5 |
| Flip Animation | Swift (fast), Smooth (eased), Bounce |
| Scramble Length | Easy / Medium / Hard |
| Camera FOV | Orthographic → Wide Perspective |
| Color Theme | 5 presets + custom editor |

---

## 🙏 Acknowledgements

- **[Three.js](https://threejs.org/)** — 3D graphics library
- **[BungeeFont](https://fonts.google.com/specimen/Bungee)** — Display typeface
- **[Font Awesome](https://fontawesome.com/)** — Icon SVG paths
- Inspired by the timeless **Rubik's Cube**, invented by Ernő Rubik in 1974

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use, modify, and distribute.

---

<div align="center">

Made with ❤️ and Three.js

**[⬆ Back to Top](#-the-cube)**

</div>

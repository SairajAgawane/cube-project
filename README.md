<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>🧩 The Cube — README</title>
<link href="https://fonts.googleapis.com/css2?family=Bungee&family=Space+Grotesk:wght@300;400;600;700&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --border: #1e1e2e;
    --text: #e8e8f0;
    --muted: #6c6c88;
    --white: #ffffff;
    --face-u: #f5f5f0;
    --face-f: #e03030;
    --face-r: #2a6fdb;
    --face-l: #2db058;
    --face-d: #f0c020;
    --face-b: #f07020;
    --accent: #7c5cfc;
    --accent2: #fc5c7c;
    --glow: rgba(124,92,252,0.18);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    font-size: 16px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ─── HERO ─── */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 4rem 2rem;
    overflow: hidden;
  }

  .hero-bg {
    position: absolute; inset: 0;
    background: radial-gradient(ellipse 80% 60% at 50% 40%, rgba(124,92,252,0.12) 0%, transparent 70%),
                radial-gradient(ellipse 50% 40% at 80% 70%, rgba(252,92,124,0.07) 0%, transparent 60%);
    pointer-events: none;
  }

  /* floating grid lines */
  .hero-bg::after {
    content: '';
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(124,92,252,0.06) 1px, transparent 1px),
      linear-gradient(90deg, rgba(124,92,252,0.06) 1px, transparent 1px);
    background-size: 60px 60px;
    animation: gridDrift 20s linear infinite;
  }

  @keyframes gridDrift {
    0%   { background-position: 0 0; }
    100% { background-position: 60px 60px; }
  }

  /* ─── 3D CUBE ─── */
  .cube-wrapper {
    perspective: 600px;
    margin-bottom: 2.5rem;
    position: relative;
    z-index: 2;
  }

  .cube-3d {
    width: 110px; height: 110px;
    transform-style: preserve-3d;
    animation: spinCube 10s linear infinite;
    position: relative;
  }

  @keyframes spinCube {
    0%   { transform: rotateX(-20deg) rotateY(0deg); }
    100% { transform: rotateX(-20deg) rotateY(360deg); }
  }

  .face {
    position: absolute;
    width: 110px; height: 110px;
    border: 3px solid rgba(0,0,0,0.4);
    border-radius: 8px;
    display: grid;
    grid-template-columns: repeat(3,1fr);
    grid-template-rows: repeat(3,1fr);
    gap: 3px;
    padding: 6px;
    opacity: 0.95;
  }

  .face-front  { background: var(--face-f); transform: translateZ(55px); }
  .face-back   { background: var(--face-b); transform: rotateY(180deg) translateZ(55px); }
  .face-right  { background: var(--face-r); transform: rotateY(90deg) translateZ(55px); }
  .face-left   { background: var(--face-l); transform: rotateY(-90deg) translateZ(55px); }
  .face-top    { background: var(--face-u); transform: rotateX(90deg) translateZ(55px); }
  .face-bottom { background: var(--face-d); transform: rotateX(-90deg) translateZ(55px); }

  .sticker {
    border-radius: 3px;
    background: rgba(255,255,255,0.18);
    border: 1px solid rgba(0,0,0,0.15);
  }

  .hero-eyebrow {
    font-family: 'Space Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 1rem;
    position: relative; z-index: 2;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.3s;
  }

  .hero-title {
    font-family: 'Bungee', cursive;
    font-size: clamp(3.5rem, 12vw, 7rem);
    line-height: 1;
    background: linear-gradient(135deg, #fff 30%, var(--accent) 70%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 1.2rem;
    position: relative; z-index: 2;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.5s;
  }

  .hero-sub {
    font-size: 1.15rem;
    color: var(--muted);
    max-width: 520px;
    margin: 0 auto 2.5rem;
    position: relative; z-index: 2;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.7s;
  }

  .badges {
    display: flex; flex-wrap: wrap; gap: 0.6rem;
    justify-content: center;
    margin-bottom: 2.5rem;
    position: relative; z-index: 2;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.9s;
  }

  .badge {
    font-family: 'Space Mono', monospace;
    font-size: 0.7rem;
    padding: 0.4rem 0.85rem;
    border-radius: 999px;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  .badge-version  { background: #1a1a2e; color: #7c9eff; border: 1px solid #2a2a4e; }
  .badge-threejs  { background: #0a2a0a; color: #4eff88; border: 1px solid #1a4a1a; }
  .badge-mit      { background: #2a1a0a; color: #ffa544; border: 1px solid #4a2a0a; }
  .badge-vanilla  { background: #1a0a2a; color: #cc88ff; border: 1px solid #3a1a4a; }

  .hero-cta {
    display: inline-flex;
    align-items: center;
    gap: 0.6rem;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    color: #fff;
    font-family: 'Bungee', cursive;
    font-size: 1rem;
    padding: 0.9rem 2.2rem;
    border-radius: 8px;
    text-decoration: none;
    letter-spacing: 0.06em;
    position: relative; z-index: 2;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 1.1s;
    box-shadow: 0 0 30px rgba(124,92,252,0.4);
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .hero-cta:hover {
    transform: translateY(-2px);
    box-shadow: 0 0 50px rgba(124,92,252,0.6);
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ─── SCROLL ARROW ─── */
  .scroll-hint {
    position: absolute; bottom: 2.5rem; left: 50%; transform: translateX(-50%);
    display: flex; flex-direction: column; align-items: center; gap: 0.4rem;
    color: var(--muted); font-size: 0.7rem; letter-spacing: 0.15em;
    text-transform: uppercase; font-family: 'Space Mono', monospace;
    opacity: 0; animation: fadeUp 0.6s ease forwards 1.4s;
  }
  .scroll-hint svg { animation: bounce 1.8s ease-in-out infinite; }
  @keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50%       { transform: translateY(6px); }
  }

  /* ─── SECTIONS ─── */
  section {
    max-width: 960px;
    margin: 0 auto;
    padding: 6rem 2rem;
  }

  .section-label {
    font-family: 'Space Mono', monospace;
    font-size: 0.68rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 0.8rem;
    display: flex; align-items: center; gap: 0.7rem;
  }
  .section-label::after {
    content: '';
    flex: 1; height: 1px;
    background: linear-gradient(to right, var(--border), transparent);
  }

  .section-title {
    font-family: 'Bungee', cursive;
    font-size: clamp(1.8rem, 5vw, 2.8rem);
    line-height: 1.1;
    margin-bottom: 1.2rem;
    background: linear-gradient(90deg, var(--white) 60%, var(--muted));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .section-desc {
    color: var(--muted);
    max-width: 600px;
    margin-bottom: 3rem;
    font-size: 1.05rem;
  }

  /* ─── FEATURES GRID ─── */
  .features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 1.2rem;
  }

  .feature-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.5rem;
    transition: border-color 0.25s, transform 0.25s, box-shadow 0.25s;
    position: relative;
    overflow: hidden;
  }
  .feature-card::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(circle at 0% 0%, rgba(124,92,252,0.08), transparent 70%);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .feature-card:hover {
    border-color: rgba(124,92,252,0.4);
    transform: translateY(-3px);
    box-shadow: 0 8px 30px rgba(124,92,252,0.12);
  }
  .feature-card:hover::before { opacity: 1; }

  .feature-icon { font-size: 1.8rem; margin-bottom: 0.8rem; display: block; }
  .feature-name {
    font-family: 'Space Mono', monospace;
    font-weight: 700;
    font-size: 0.9rem;
    color: var(--white);
    margin-bottom: 0.4rem;
    letter-spacing: 0.02em;
  }
  .feature-desc { font-size: 0.88rem; color: var(--muted); line-height: 1.6; }

  /* ─── FACES PALETTE ─── */
  .faces-row {
    display: flex; flex-wrap: wrap; gap: 1.2rem;
    margin-bottom: 3rem;
  }

  .face-chip {
    display: flex; align-items: center; gap: 0.75rem;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 0.75rem 1.1rem;
    transition: transform 0.2s;
  }
  .face-chip:hover { transform: scale(1.04); }

  .face-swatch {
    width: 32px; height: 32px;
    border-radius: 5px;
    border: 2px solid rgba(255,255,255,0.12);
    flex-shrink: 0;
  }

  .face-info { line-height: 1.3; }
  .face-role { font-size: 0.7rem; color: var(--muted); font-family: 'Space Mono', monospace; text-transform: uppercase; letter-spacing: 0.1em; }
  .face-color-name { font-size: 0.85rem; color: var(--white); font-weight: 600; }

  /* ─── CONTROLS TABLE ─── */
  .controls-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.92rem;
  }
  .controls-table th {
    font-family: 'Space Mono', monospace;
    font-size: 0.68rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
    text-align: left;
    padding: 0.7rem 1rem;
    border-bottom: 1px solid var(--border);
  }
  .controls-table td {
    padding: 0.85rem 1rem;
    border-bottom: 1px solid rgba(30,30,46,0.5);
    vertical-align: middle;
  }
  .controls-table tr:last-child td { border-bottom: none; }
  .controls-table tr:hover td { background: rgba(124,92,252,0.05); }

  kbd {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 5px;
    padding: 0.2rem 0.5rem;
    font-family: 'Space Mono', monospace;
    font-size: 0.78rem;
    color: var(--accent);
  }

  /* ─── TECH STACK ─── */
  .tech-stack {
    display: flex; flex-wrap: wrap; gap: 1rem;
  }
  .tech-pill {
    display: flex; align-items: center; gap: 0.6rem;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 999px;
    padding: 0.55rem 1.1rem;
    font-size: 0.85rem;
    font-family: 'Space Mono', monospace;
    color: var(--white);
    transition: border-color 0.2s, color 0.2s;
  }
  .tech-pill:hover { border-color: var(--accent); color: var(--accent); }
  .tech-dot { width: 8px; height: 8px; border-radius: 50%; }

  /* ─── FILE TREE ─── */
  .file-tree {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 2rem;
    font-family: 'Space Mono', monospace;
    font-size: 0.82rem;
    line-height: 2;
    color: var(--muted);
  }
  .file-tree .dir  { color: var(--accent); }
  .file-tree .file { color: var(--white); }
  .file-tree .comment { color: var(--muted); font-size: 0.75rem; }

  /* ─── INSTALL BLOCK ─── */
  .code-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.8rem 2rem;
    font-family: 'Space Mono', monospace;
    font-size: 0.82rem;
    line-height: 2;
    position: relative;
    overflow: hidden;
  }
  .code-block::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 3px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
  }
  .code-block .comment { color: var(--muted); }
  .code-block .cmd     { color: var(--face-d); }
  .code-block .arg     { color: var(--face-l); }
  .code-block .str     { color: #ff9e7a; }

  /* ─── STATS CARD ─── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 1rem;
    margin-bottom: 2rem;
  }
  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.4rem 1.2rem;
    text-align: center;
  }
  .stat-icon { font-size: 1.5rem; margin-bottom: 0.4rem; }
  .stat-label { font-family: 'Space Mono', monospace; font-size: 0.65rem; letter-spacing: 0.15em; text-transform: uppercase; color: var(--muted); margin-bottom: 0.3rem; }
  .stat-value { font-family: 'Bungee', cursive; font-size: 1.5rem; color: var(--white); }

  /* ─── FOOTER ─── */
  footer {
    border-top: 1px solid var(--border);
    text-align: center;
    padding: 3rem 2rem;
    font-size: 0.85rem;
    color: var(--muted);
  }
  footer a { color: var(--accent); text-decoration: none; }
  footer a:hover { text-decoration: underline; }
  .footer-logo {
    font-family: 'Bungee', cursive;
    font-size: 1.5rem;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 0.5rem;
    display: block;
  }

  /* ─── DIVIDER ─── */
  .divider {
    border: none;
    border-top: 1px solid var(--border);
    margin: 0;
  }

  /* ─── SCROLL REVEAL ─── */
  .reveal {
    opacity: 0;
    transform: translateY(28px);
    transition: opacity 0.65s ease, transform 0.65s ease;
  }
  .reveal.visible {
    opacity: 1;
    transform: none;
  }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 600px) {
    .features-grid { grid-template-columns: 1fr; }
    .stats-row { grid-template-columns: repeat(2, 1fr); }
    .faces-row { flex-direction: column; }
  }
</style>
</head>
<body>

<!-- ═══ HERO ═══ -->
<header class="hero">
  <div class="hero-bg"></div>

  <div class="cube-wrapper">
    <div class="cube-3d">
      <div class="face face-front">
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
      </div>
      <div class="face face-back">
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
      </div>
      <div class="face face-right">
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
      </div>
      <div class="face face-left">
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
      </div>
      <div class="face face-top">
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
      </div>
      <div class="face face-bottom">
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
        <div class="sticker"></div><div class="sticker"></div><div class="sticker"></div>
      </div>
    </div>
  </div>

  <p class="hero-eyebrow">Three.js · Vanilla JS · No Build Tools</p>
  <h1 class="hero-title">The Cube</h1>
  <p class="hero-sub">A beautifully crafted 3D Rubik's Cube simulator — solve it, scramble it, theme it. Runs entirely in the browser.</p>

  <div class="badges">
    <span class="badge badge-version">v 0.99.2</span>
    <span class="badge badge-threejs">Three.js r95</span>
    <span class="badge badge-mit">MIT License</span>
    <span class="badge badge-vanilla">Vanilla JS</span>
  </div>

  <a href="https://cube-project.vercel.app/" class="hero-cta" target="_blank">
    🚀 &nbsp;Live Demo
  </a>

  <div class="scroll-hint">
    <span>Scroll</span>
    <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M8 3v10M3 9l5 5 5-5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
  </div>
</header>

<hr class="divider"/>

<!-- ═══ FEATURES ═══ -->
<section>
  <p class="section-label reveal">What's Inside</p>
  <h2 class="section-title reveal">Features</h2>
  <p class="section-desc reveal">Everything you need for a competitive solve session — from a 2×2 warm-up to a full 5×5 challenge.</p>

  <div class="features-grid">
    <div class="feature-card reveal">
      <span class="feature-icon">🎲</span>
      <div class="feature-name">Multi-Size Cubes</div>
      <div class="feature-desc">Choose between 2×2, 3×3, 4×4, or 5×5. Each size tracks its own stats independently.</div>
    </div>
    <div class="feature-card reveal">
      <span class="feature-icon">🎨</span>
      <div class="feature-name">5 Built-in Themes</div>
      <div class="feature-desc">Switch between Cube, Erno, Dust, Camo, and Rain palettes in a single tap.</div>
    </div>
    <div class="feature-card reveal">
      <span class="feature-icon">🖌️</span>
      <div class="feature-name">Custom Theme Editor</div>
      <div class="feature-desc">Full HSL color picker — tap any face and dial in exactly the color you want.</div>
    </div>
    <div class="feature-card reveal">
      <span class="feature-icon">⏱️</span>
      <div class="feature-name">Timer & Stats</div>
      <div class="feature-desc">Tracks best time, Ao5, Ao12, and Ao25 averages. All data persists across sessions.</div>
    </div>
    <div class="feature-card reveal">
      <span class="feature-icon">🔀</span>
      <div class="feature-name">Auto Scrambler</div>
      <div class="feature-desc">Easy / Medium / Hard scramble difficulty — proper WCA-style move notation.</div>
    </div>
    <div class="feature-card reveal">
      <span class="feature-icon">⚙️</span>
      <div class="feature-name">Flip Animations</div>
      <div class="feature-desc">Three flip styles: Swift, Smooth, and Bounce. Camera FOV goes from ortho to wide.</div>
    </div>
    <div class="feature-card reveal">
      <span class="feature-icon">📱</span>
      <div class="feature-name">Touch & Mouse</div>
      <div class="feature-desc">Full drag support on desktop and mobile. Drag on a face to rotate a layer; drag outside for the whole cube.</div>
    </div>
    <div class="feature-card reveal">
      <span class="feature-icon">🎉</span>
      <div class="feature-name">Confetti on Solve</div>
      <div class="feature-desc">Celebratory particle burst and best-time trophy when you crack it.</div>
    </div>
  </div>
</section>

<hr class="divider"/>

<!-- ═══ HOW TO PLAY ═══ -->
<section>
  <p class="section-label reveal">Getting Started</p>
  <h2 class="section-title reveal">How to Play</h2>
  <p class="section-desc reveal">Double-tap the cube to begin. The timer starts on your first move. Solve all six faces to win.</p>

  <table class="controls-table reveal">
    <thead>
      <tr>
        <th>Action</th>
        <th>Gesture / Control</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Rotate a layer</td>
        <td><kbd>Drag</kbd> on a cube face</td>
      </tr>
      <tr>
        <td>Rotate the whole cube</td>
        <td><kbd>Drag</kbd> outside the cube</td>
      </tr>
      <tr>
        <td>Start a new game</td>
        <td><kbd>Double-tap</kbd> the cube</td>
      </tr>
      <tr>
        <td>Open settings</td>
        <td><kbd>⚙️</kbd> icon — bottom right</td>
      </tr>
      <tr>
        <td>View stats</td>
        <td><kbd>🏆</kbd> icon — bottom left</td>
      </tr>
      <tr>
        <td>Back to menu</td>
        <td><kbd>←</kbd> back icon</td>
      </tr>
    </tbody>
  </table>
</section>

<hr class="divider"/>

<!-- ═══ THEMES ═══ -->
<section>
  <p class="section-label reveal">Color Schemes</p>
  <h2 class="section-title reveal">Themes</h2>
  <p class="section-desc reveal">Five curated palettes, each with a distinct personality. Or build your own with the HSL picker.</p>

  <div class="faces-row reveal">
    <div class="face-chip">
      <div class="face-swatch" style="background:#f5f5f0;"></div>
      <div class="face-info"><div class="face-role">U · Top</div><div class="face-color-name">White</div></div>
    </div>
    <div class="face-chip">
      <div class="face-swatch" style="background:#e03030;"></div>
      <div class="face-info"><div class="face-role">F · Front</div><div class="face-color-name">Red</div></div>
    </div>
    <div class="face-chip">
      <div class="face-swatch" style="background:#2a6fdb;"></div>
      <div class="face-info"><div class="face-role">R · Right</div><div class="face-color-name">Blue</div></div>
    </div>
    <div class="face-chip">
      <div class="face-swatch" style="background:#2db058;"></div>
      <div class="face-info"><div class="face-role">L · Left</div><div class="face-color-name">Green</div></div>
    </div>
    <div class="face-chip">
      <div class="face-swatch" style="background:#f0c020;"></div>
      <div class="face-info"><div class="face-role">D · Bottom</div><div class="face-color-name">Yellow</div></div>
    </div>
    <div class="face-chip">
      <div class="face-swatch" style="background:#f07020;"></div>
      <div class="face-info"><div class="face-role">B · Back</div><div class="face-color-name">Orange</div></div>
    </div>
  </div>
</section>

<hr class="divider"/>

<!-- ═══ STATS ═══ -->
<section>
  <p class="section-label reveal">Scoring</p>
  <h2 class="section-title reveal">Stats & Records</h2>
  <p class="section-desc reveal">All stats are tracked per cube size and saved automatically to localStorage — no account needed.</p>

  <div class="stats-row reveal">
    <div class="stat-card">
      <div class="stat-icon">✅</div>
      <div class="stat-label">Tracked</div>
      <div class="stat-value">Solves</div>
    </div>
    <div class="stat-card">
      <div class="stat-icon">🥇</div>
      <div class="stat-label">Personal</div>
      <div class="stat-value">Best</div>
    </div>
    <div class="stat-card">
      <div class="stat-icon">📈</div>
      <div class="stat-label">Rolling</div>
      <div class="stat-value">Ao5</div>
    </div>
    <div class="stat-card">
      <div class="stat-icon">📊</div>
      <div class="stat-label">Rolling</div>
      <div class="stat-value">Ao12</div>
    </div>
    <div class="stat-card">
      <div class="stat-icon">🔢</div>
      <div class="stat-label">Rolling</div>
      <div class="stat-value">Ao25</div>
    </div>
  </div>
</section>

<hr class="divider"/>

<!-- ═══ TECH STACK ═══ -->
<section>
  <p class="section-label reveal">Under the Hood</p>
  <h2 class="section-title reveal">Tech Stack</h2>
  <p class="section-desc reveal">No frameworks, no bundlers, no dependencies beyond Three.js. Pure, fast, portable.</p>

  <div class="tech-stack reveal">
    <div class="tech-pill"><span class="tech-dot" style="background:#4eff88;"></span>Three.js r95</div>
    <div class="tech-pill"><span class="tech-dot" style="background:#f0c020;"></span>Vanilla JS ES6+</div>
    <div class="tech-pill"><span class="tech-dot" style="background:#7c9eff;"></span>CSS3 Animations</div>
    <div class="tech-pill"><span class="tech-dot" style="background:#ff9e7a;"></span>LocalStorage</div>
    <div class="tech-pill"><span class="tech-dot" style="background:#cc88ff;"></span>requestAnimationFrame</div>
    <div class="tech-pill"><span class="tech-dot" style="background:#4ecfff;"></span>WebGL</div>
    <div class="tech-pill"><span class="tech-dot" style="background:#fff;"></span>Vercel</div>
  </div>
</section>

<hr class="divider"/>

<!-- ═══ PROJECT STRUCTURE ═══ -->
<section>
  <p class="section-label reveal">Codebase</p>
  <h2 class="section-title reveal">Project Structure</h2>
  <p class="section-desc reveal">Everything lives in three files. No build step. Clone and open in a browser.</p>

  <div class="file-tree reveal">
    <span class="dir">the-cube/</span><br>
    &nbsp;&nbsp;├── <span class="file">index.html</span>&nbsp;&nbsp;&nbsp;<span class="comment">// app shell &amp; UI markup</span><br>
    &nbsp;&nbsp;├── <span class="file">style.css</span>&nbsp;&nbsp;&nbsp;&nbsp;<span class="comment">// Bungee font, sliders, layout</span><br>
    &nbsp;&nbsp;├── <span class="file">script.js</span>&nbsp;&nbsp;&nbsp;&nbsp;<span class="comment">// full game logic</span><br>
    &nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="comment">AnimationEngine &nbsp;// rAF loop &amp; tweening</span><br>
    &nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="comment">World &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// Three.js scene, camera, lighting</span><br>
    &nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="comment">Cube &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// 3D model &amp; geometry</span><br>
    &nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="comment">Controls &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// drag / touch / layer rotation</span><br>
    &nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="comment">Scrambler &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// move generation &amp; notation</span><br>
    &nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="comment">Timer &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// game clock</span><br>
    &nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="comment">Scores &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// stats &amp; averages</span><br>
    &nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="comment">Storage &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// localStorage persistence</span><br>
    &nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;├── <span class="comment">Themes &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// color schemes</span><br>
    &nbsp;&nbsp;│&nbsp;&nbsp;&nbsp;└── <span class="comment">Confetti &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;// celebration particles</span><br>
    &nbsp;&nbsp;└── <span class="file">README.md</span>
  </div>
</section>

<hr class="divider"/>

<!-- ═══ INSTALL ═══ -->
<section>
  <p class="section-label reveal">Setup</p>
  <h2 class="section-title reveal">Run Locally</h2>
  <p class="section-desc reveal">No build step required. Clone, serve, and play.</p>

  <div class="code-block reveal">
    <span class="comment"># Clone the repo</span><br>
    <span class="cmd">git</span> <span class="arg">clone</span> <span class="str">https://github.com/your-username/the-cube.git</span><br>
    <span class="cmd">cd</span> <span class="arg">the-cube</span><br><br>
    <span class="comment"># Serve locally</span><br>
    <span class="cmd">npx</span> <span class="arg">serve</span> .<br>
    <span class="comment"># or</span><br>
    <span class="cmd">python</span> <span class="arg">-m</span> <span class="str">http.server</span> 8080
  </div>

  <br/>

  <div class="code-block reveal">
    <span class="comment"># Deploy to Vercel</span><br>
    <span class="cmd">npm</span> <span class="arg">install</span> <span class="str">-g vercel</span><br>
    <span class="cmd">vercel</span>
  </div>
</section>

<hr class="divider"/>

<!-- ═══ FOOTER ═══ -->
<footer>
  <span class="footer-logo">🧩 The Cube</span>
  <p>Built with ❤️ and <a href="https://threejs.org/" target="_blank">Three.js</a> &nbsp;·&nbsp;
    Typeface: <a href="https://fonts.google.com/specimen/Bungee" target="_blank">Bungee</a> &nbsp;·&nbsp;
    Inspired by Ernő Rubik (1974) &nbsp;·&nbsp;
    <a href="#">MIT License</a>
  </p>
  <p style="margin-top:0.5rem;">
    <a href="https://cube-project.vercel.app/" target="_blank">cube-project.vercel.app</a>
  </p>
</footer>

<script>
  // Scroll-reveal
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.12 });

  document.querySelectorAll('.reveal').forEach((el, i) => {
    el.style.transitionDelay = (i % 4) * 0.07 + 's';
    observer.observe(el);
  });
</script>
</body>
</html>

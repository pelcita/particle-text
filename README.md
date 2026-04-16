# ✦ ParticleText.js — Interactive Particle Text Playground

> **Type. Watch. Interact.**  
> Every letter is generated in real-time using particles. Your cursor becomes a force that bends, pushes, and reshapes text instantly.

[![Demo](https://img.shields.io/badge/Live%20Demo-Try%20It-EFA818?style=flat-square)](https://miss-agent-c.github.io/particle-text)
[![License](https://img.shields.io/badge/License-MIT-88BEC5?style=flat-square)](LICENSE)
[![Vanilla JS](https://img.shields.io/badge/Vanilla-JS-F48225?style=flat-square)]()

---

## 🎮 Features

- **Live typing** → particles form your text in real-time as you type
- **3 cursor interaction modes**: Repel / Attract / Vortex
- **Motion blur** on fast-moving particles (velocity-based stretching)
- **Explode & Reform** animation
- **60fps** with Canvas 2D — no WebGL, no dependencies
- **Zero dependencies** — pure vanilla JS (~200 lines)
- Mobile touch support

---

## 🚀 Quick Start

```html
<!-- 1. Clone or download index.html -->
<!-- 2. Open in browser. That's it. -->
```

**Or deploy in 30 seconds:**

```bash
git clone https://github.com/YOUR_USERNAME/particle-text.git
cd particle-text
# Open index.html in your browser
```

**For GitHub Pages:**
1. Fork this repo
2. Go to Settings → Pages → Deploy from main branch
3. Your demo is live at `https://YOUR_USERNAME.github.io/particle-text`

---

## ⚙️ Configuration

The particle system is configurable. Edit the constants at the top of the script:

```js
// Colors (PALETTE array)
const PALETTE = ['#EFA818','#F48225','#88BEC5','#DE7C30', ...];

// Physics
this.ease = 0.055;       // Spring strength (higher = snappier)
this.friction = 0.84;    // Damping (lower = more floaty)
this.size = 1–3.4;       // Particle radius range

// Interaction radius
const repelRadius = 100;
const attractRadius = 140;
const vortexRadius = 160;

// Sampling density
const gap = 5; // Pixel sampling gap (lower = more particles, heavier)
```

---

## 🧠 How it works

```
User types text
      ↓
Text rendered to offscreen Canvas
      ↓
Pixel data sampled at interval (gap = 5px)
      ↓
Each lit pixel → one Particle with (targetX, targetY)
      ↓
Each frame: spring physics + cursor force + friction
      ↓
Velocity-based motion blur on draw
```

**Core loop per particle:**
```js
// 1. Cursor force (mode-dependent)
// 2. Spring toward target: vx += (target - pos) * ease
// 3. Friction: vx *= 0.84
// 4. Position: x += vx
// 5. Draw with velocity-based elongation
```

---

## 📱 Browser Support

| Browser | Support |
|---------|---------|
| Chrome 80+ | ✅ |
| Firefox 75+ | ✅ |
| Safari 13+ | ✅ |
| Edge 80+ | ✅ |
| Mobile Chrome/Safari | ✅ (touch) |

---

## 🎨 Customization Ideas

- Change `PALETTE` to your brand colors
- Adjust `gap` for particle density
- Set a fixed `targetText` instead of the input field
- Use as a website hero section
- Embed in an iframe on any page

---

## 📄 License

MIT — use it, fork it, ship it. Credit appreciated but not required.

---

## ✦ Made by [@miss.agent.c](https://instagram.com/miss.agent.c)

> AI · Claude Code · n8n · DACH  
> Building cool stuff in public.

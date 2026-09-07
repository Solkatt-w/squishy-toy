# Squishy Toy · 电子捏捏乐

> A bite-size stress-relief web toy. Tap, hold, and squeeze 8 squishy items with realistic tactile feedback.

[Live Demo](https://solkatt-w.github.io/squishy-toy/) · [Report Bug](#) · [Request Feature](#)

---

## ✨ Features

- **8 squishy items** with distinct visuals, tactile words, and sound profiles
  - 🍮 Jelly · 🧸 Plush · 🟢 Slime · 🧽 Sponge · ⚪ Bubble Wrap · 🟫 Clay · 🔴 Stress Ball · ☁️ Marshmallow
- **10-step hardness slider** that dynamically modulates deformation, pitch, and volume
- **5-channel tactile feedback** on every tap: visual squish · tactile word · ripple · floating score · device vibration
- **Web Audio synthesis** — zero audio assets, all sounds generated procedurally
- **3 interaction modes**: single tap · long-press to spam · auto-squeeze hands-free
- **Single-file zero-dependency** — under 25 KB, deploy to any static host

## 🎮 Try It

Open `electronic-pinpin.html` directly in a browser, or visit the [GitHub Pages demo](https://solkatt-w.github.io/squishy-toy/) once enabled.

No build step. No npm. No frameworks. Just open and play.

## 🛠 Tech Stack

| Layer | Choice |
|---|---|
| Markup | Semantic HTML5 |
| Styling | CSS3 (Grid, custom properties, keyframes) |
| Graphics | Inline SVG (parameterized drawing) |
| Audio | Web Audio API (OscillatorNode + GainNode) |
| Interaction | Vanilla ES6+ |
| Mobile | `touch-action`, `navigator.vibrate`, viewport meta |

## 📦 Project Structure

```
squishy-toy/
├── electronic-pinpin.html   # The full game in one file
├── README.md                # You are here
├── LICENSE                  # MIT
└── .gitignore
```

## 🚀 Local Preview

```bash
# Just open it
open electronic-pinpin.html        # macOS
start electronic-pinpin.html       # Windows

# Or serve with any static server
python -m http.server 8080
```

## 🧩 How It Works

1. **Visuals** — Each item is drawn with inline SVG (paths, circles, ellipses). Hardness controls a `--sx` / `--sy` CSS variable that scales the shape along x/y axes for a believable squish.
2. **Audio** — `OscillatorNode` synthesizes sounds at runtime. Bubble Wrap uses 3 stacked square waves with offset envelopes to mimic a popping cluster. Other items use sine or triangle waves with frequency decay.
3. **Tactile** — A `TACTILE` map holds per-item word banks (`"啵～"`, `"Q弹~"`, `"啾~"`, etc.) sampled randomly on each tap.
4. **Mobile vibration** — `navigator.vibrate(10 + hardness × 30)` provides haptic pulse on supported devices.

## 🎯 Roadmap

- [ ] More items (balloon, water blob, foam brick)
- [ ] LocalStorage to persist stats across sessions
- [ ] PWA manifest for offline install
- [ ] Optional Matter.js physics for advanced items
- [ ] Sound on/off toggle
- [ ] Light/dark theme

## 🤝 Contributing

PRs welcome! Keep it dependency-free and single-file if you can.

## 📄 License

MIT © Solkatt-w
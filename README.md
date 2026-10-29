# 🎮 DATA HEIST — Cyber City
### A Pixel Art Cybersecurity Awareness Game

---

## 📁 File Structure

```
data-heist-game/
│
├── index.html      ← Main game HTML (structure & screens)
├── style.css       ← All styling (pixel art, neon, CRT effects, animations)
├── game.js         ← Game engine (state, questions, audio, particles, canvas art)
├── server.py       ← Python backend (leaderboard API, score tracking, file server)
└── README.md       ← This file
```

---

## ▶ How to Play (Browser Only — No Server Needed)

Just **double-click `index.html`** in your browser. No installation required.

- Use **mouse** or keyboard **1/2/3/4** or **A/B/C/D** to answer
- Press **Enter** to continue after answering
- Toggle sound with the 🔊 button (bottom-right)

---

## 🐍 How to Run with Python Backend (Optional)

The Python server adds:
- 📊 Persistent leaderboard (saved to `scores.json`)
- 🔐 Server-side answer validation
- 📈 Statistics API

**Requirements:** Python 3.10+

```bash
cd data-heist-game
python3 server.py
```

Then open **http://localhost:8080** in your browser.

### API Endpoints

| Method | Endpoint                  | Description              |
|--------|---------------------------|--------------------------|
| GET    | `/api/leaderboard?limit=10` | Top scores              |
| GET    | `/api/stats`              | Global statistics         |
| POST   | `/api/session/start`      | Start a game session      |
| POST   | `/api/session/answer`     | Submit an answer          |
| POST   | `/api/session/finish`     | Finalise and save score   |

**Example — start session:**
```bash
curl -X POST http://localhost:8080/api/session/start \
     -H "Content-Type: application/json" \
     -d '{"player": "CYBER_HERO"}'
```

---

## 🎨 Game Features

### Visual
- **Full pixel art aesthetic** — CSS-drawn characters, buildings, scenes
- **CRT scanline effect** — authentic retro monitor feel
- **Neon glow animations** — buttons, text, timers all pulse
- **Glitch text effect** — animated title screen with colour splits
- **Particle system** — pixel-square explosions on correct answers
- **Star field** — animated twinkling background stars
- **City skyline** — SVG-drawn pixel city on start screen
- **Floating icons** — security icons drift across the background
- **Three chapter scenes** — University, Mall, House pixel environments

### Audio (Web Audio API — no files needed)
- 🔊 8-bit sound effects for: correct, wrong, timeout, chapter clear, victory, game over
- Tick sounds when timer runs low
- All synthesised in-browser, no external audio files

### Gameplay
- **12 questions** across 3 chapters
- **3 lives** — lose them all = game over
- **Adaptive timers** — 20s / 15s / 10s per difficulty
- **Combo streaks** — bonus points for consecutive correct answers
- **Speed bonuses** — more time remaining = more points
- **S/A/B/C/D rank** system on victory screen
- **Hi-score** saved to localStorage
- **Keyboard shortcuts** — 1/2/3/4 or A/B/C/D + Enter

---

## 📚 The Story

**Cyber City** — a metropolis where banks, universities, malls and homes are all connected to the grid. You are an ordinary citizen. Today, the hackers have set their sights on you.

| Chapter | Location      | Difficulty | Time | Theme             |
|---------|---------------|------------|------|-------------------|
| 1       | 🎓 University | Easy       | 20s  | Phishing emails   |
| 2       | 🛒 Mall       | Medium     | 15s  | Social engineering |
| 3       | 🏠 House      | Hard       | 10s  | Home network security |

---

## ⚔ The Six Laws of Cyber City

1. Never click links in suspicious emails
2. Real banks never ask for PINs or passwords by phone
3. Never plug in unknown USB drives
4. Always use strong, unique passwords for every account
5. Verify unexpected visitors before letting them in
6. Keep your router and all devices updated regularly

---

## 🛠 Technical Details

| File        | Language   | Purpose                          |
|-------------|-----------|----------------------------------|
| index.html  | HTML5      | Game screens, DOM structure      |
| style.css   | CSS3       | Pixel art, animations, theming   |
| game.js     | JavaScript | Game engine, audio, canvas art   |
| server.py   | Python 3   | HTTP server, leaderboard, API    |

### JavaScript Modules (game.js)
- `QUESTIONS` — all 12 questions with answers and feedback
- `CHAPTERS` — chapter metadata (name, colour, story, scene)
- `ScoreBoard` (class) — leaderboard logic
- `Particle System` — canvas-based pixel particle explosions
- `Audio Engine` — Web Audio API synthesiser (no files needed)
- `Pixel Art Renderer` — grid-based canvas pixel drawing
- `Star Field / Floating Icons` — animated background elements
- `City Skyline` — SVG procedural pixel city
- `Game State Machine` — screen transitions and state management

---

*"In real life, one mistake can cost you everything. Keep learning and stay safe online."*

# 🌐 DisasterBridge

> AI-powered emergency response coordination for individuals with disabilities during natural disasters.

**Live Demo:** [View on GitHub Pages](https://YOUR-USERNAME.github.io/disasterbridge/)

---

## The Problem

During natural disasters, people with disabilities face **two layers of risk**:

1. **Immediate physical danger** from the disaster itself
2. **Loss of access** to the support systems, equipment, and routines they depend on daily

Standard emergency systems — loud sirens, mass texts, shelter-in-place orders — were not designed with disability in mind. DisasterBridge uses AI to close that gap.

---

## How It Works

```
🗺️ Risk Map  ──────────────────────→  🚨 People Requiring Attention
   (flags residents)                        (central dashboard)
                                                  ↑
📞 Welfare Calls  ─────────────────→  (cards updated live from calls)
   (AI dispatcher + interactive mode)
```

The **People Requiring Attention** dashboard is the single source of truth. The risk map seeds it, welfare calls update it in real time, and first responders read from it.

---

## The Three Tools

### 🗺️ Risk Map (`simulation.html`)
- Animated Hurricane Beryl vulnerability map — Houston, Harris County
- Click **▶ Run Simulation** to watch 5 phases unfold: scanning → flagging → dispatching → welfare calls → shelters confirmed
- Each critical resident's pin appears with full card data
- **Automatically saves flagged residents to the People Requiring Attention dashboard** via localStorage — no API key needed
- A clickable banner appears during the simulation linking directly to the dashboard

### 📞 Welfare Call Simulator (`call.html`)
- AI dispatcher (Groq + Llama 3.1) places welfare check calls adapted to each disability profile
- **Auto mode** — AI plays both sides, showing a complete call transcript
- **Interactive mode** — you respond as the resident; AI reacts in real time
- Profiles: Margaret T. (oxygen dependent), James R. (ventilator), Aisha M. (autism), Unknown Caller (intake from scratch)
- After each call, **card data is extracted from the transcript and saved** to People Requiring Attention automatically
- A green toast confirms the save

### 🚨 People Requiring Attention (`card.html`)
- Central dashboard automatically populated from the risk map and welfare calls
- Each person shown with priority colour coding: 🔴 CRITICAL / 🟡 HIGH / 🟢 STANDARD
- Three tabs per person: **Responder Card** (print-ready) · **Edit/Add** · **Call Log**
- Clicking **Edit & Regenerate** runs an AI merge — new information is merged with existing card data, nothing is lost
- Add people manually via form with quick-fill presets
- Cards persist across browser sessions via localStorage

---

## API Key

The Call Simulator and card regeneration require a **free Groq API key**:

1. Go to [console.groq.com/keys](https://console.groq.com/keys)
2. Sign up with any email → click **Create API key**
3. Paste it into the yellow bar at the top of the page

The key is held in your browser session only — it is never stored in code, committed to this repo, or sent anywhere other than Groq's API directly.

The **Risk Map** works with no API key at all.

---

## Running Locally

No build step required. Just open the HTML files in a browser:

```bash
git clone https://github.com/YOUR-USERNAME/disasterbridge
cd disasterbridge
open index.html   # or double-click in Finder / Explorer
```

Or deploy to GitHub Pages:

1. Push to a public or private GitHub repo
2. Settings → Pages → Source: main branch → Save
3. Your live URL: `https://YOUR-USERNAME.github.io/disasterbridge/`

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Pure HTML / CSS / JavaScript — no framework, no build step |
| AI | Groq API · Llama 3.1 8B Instant |
| Storage | Browser localStorage (persistent across sessions) |
| Hosting | GitHub Pages |

---

## File Structure

```
disasterbridge/
├── index.html        ← Landing page + flow overview
├── simulation.html   ← Risk map with animated simulation
├── call.html         ← AI welfare call simulator (auto + interactive)
├── card.html         ← People Requiring Attention dashboard
└── README.md
```

---

## Roadmap

- **Phase 1** ✅ Preparedness — vulnerability mapping, risk scoring
- **Phase 2** ✅ Active Response — AI welfare calls, live responder cards, attention dashboard
- **Phase 3** 🔜 Recovery — resource coordination, follow-up scheduling, outcome tracking

---

## License

MIT — built for humanitarian impact. Use it, fork it, improve it.

---

## Authors

Tarun.N.M
Mohammed Jassim

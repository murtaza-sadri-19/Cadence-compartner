# Cadence

Real-time voice analysis console for interview practice. Runs in-browser, no backend, no data leaves your machine.

Tracks: **WPM**, **volume (dB)**, **pitch (Hz)**, **filler words**, and a live transcript. Generates a post-session report with charts and auto-generated feedback.

## Quick start

```bash
node server.js
# open http://localhost:3000
```

Or open `index.html` directly in Chrome/Edge (mic permissions work better that way).

## Health endpoint

```
GET /health
→ {"status":"ok","uptime":12.345}
```

Use for cron keepalive (UptimeRobot, GitHub Actions, etc.).

## Deploy

**Vercel:**
1. Push to GitHub
2. Import repo on vercel.com → Framework: Other → Output: `.`
3. Deploy

**Railway:**
```bash
npm i -g railway && railway login && railway init && railway up && railway domain
```

**Fly.io:**
```bash
fly launch && fly deploy
```

## Pitch detection

Uses [Pitchy](https://github.com/ianprime0509/pitchy) (McLeod Pitch Method) via CDN. Loads automatically in the browser — no npm install needed for the frontend.

## Chrome/Edge required

Speech recognition (WPM, transcript, fillers) requires Chrome or Edge. Volume and pitch work everywhere.

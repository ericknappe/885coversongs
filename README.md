# WXPN 885 Greatest Cover Songs — Countdown

An interactive, single‑page dashboard for exploring **WXPN’s “885 Greatest Cover Songs”**.

Built as a lightweight, client‑side app that runs entirely in the browser and works well on desktop, tablet, and mobile.

---

## What You Can Do

- Browse the countdown by rank
- See album art, song details, and original artists
- Preview tracks (Spotify / Deezer previews where available)
- Jump quickly through the list using the slider or the **Next 10 Songs** panel
- Explore charts showing trends across artists, years, decades, and songs

This project focuses on **music discovery**, not consumption.

---

## Music & Previews

- Preview‑only playback (no full tracks)
- No logins or subscriptions required
- No autoplay
- Optional links out to some streaming services

---

## How It Works

- One self‑contained HTML file
- Loads a JSON dataset in the browser
- No frameworks, no build step
- Hosted easily on GitHub Pages

---

## Run Locally

Because the app loads JSON via `fetch()`, use a simple local server:

```bash
python3 -m http.server 8000
```

Then open:

```
http://localhost:8000/
```

---

## Credits

- Countdown data: WXPN  
- Preview embeds: Spotify, Deezer

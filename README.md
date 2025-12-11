# 885 Greatest Cover Songs – Countdown Dashboard
Interactive Bar-Race Dashboard Powered by D3.js

This repository contains a fully client-side HTML/JavaScript dashboard that visualizes the **885 Greatest Cover Songs Countdown**. It renders six D3 bar-race charts plus a “Current Song” display, all synced to a slider that represents the countdown rank (885 → 1).

The dashboard is designed to run entirely in the browser — no server required — and can be hosted directly on **GitHub Pages**.

---

## 🚀 Features

### ✓ Six animated bar-race charts
- Most Covered Original Artists  
- Most Frequent Cover Artists  
- Most Represented Genres  
- Most Covered Original Songs  
- Most Covered Original Decades  
- Current Song (image + metadata display)

(*A seventh chart for Cover Years exists in the codebase but is currently disabled.*)

---

### ✓ Interactive controls
- Slider moves the timeline through all 885 songs  
- Each chart updates live as the countdown progresses  
- Fast risers marked with ↑ and bold labels  
- Hide/show toggle on every chart panel  
- Drag-and-drop reordering of chart panels (desktop only)

---

### ✓ Responsive layout
- Desktop: 3×3 grid  
- Medium screens: 2-wide grid  
- Mobile/iPad: 1-column stack  
- Chart margins adjust automatically so bars remain visually centered

---

### ✓ Data-driven
The dashboard reads a JSON file containing 885 countdown data.  
You can supply your own via:

`...?data_endpoint=url_to_file.json`

Example:

`https://yourusername.github.io/885coversongs/?data_endpoint=data/wxpn_885.json`

---

## 📁 Repository Structure

```
/
├── index.html            # The interactive dashboard
├── data/
│   └── wxpn_885.json     # Countdown dataset (you provide this)
├── README.md
└── (optional) assets/
```

---

## 📦 Data File Requirements (`wxpn_885.json`)

The dashboard expects an **array of objects**, one per song:

```json
{
  "id": "18661",
  "artist": "Led Zeppelin",
  "song": "Dazed And Confused",
  "album": "Led Zeppelin",
  "releaseDate": "1969",
  "albumArt": "https:\/\/i.scdn.co\/image\/ab67616d00001e026f2f499c1df1f210c9b34b32",
  "originalArtist": "Jake Holmes",
  "originalYear": "1967",
  "genre": "a:4:{i:0;s:12:\"classic rock\";i:1;s:4:\"rock\";i:2;s:9:\"hard rock\";i:3;s:13:\"rock and roll\";}",
  "rank": 497
}
```

### Required fields

| Field | Type | Purpose |
|-------|------|---------|
| `rank` | integer | Determines frame order (885 → 1) |
| `artist` | string | Cover artist |
| `originalArtist` | string | Used for Original Artist race |
| `song` | string | Used in "Original Songs" combo |
| `genre` | PHP serialized array | Decoded client-side |
| `albumArt` | URL or empty | Displays in Current Song |
| `releaseDate` | string containing YYYY | Used to extract cover year |

A missing or malformed `releaseDate` affects only the Cover Years chart (currently disabled).

---

## 🧭 Using the Dashboard

### 1. Local Development
Clone the repo:

```sh
git clone https://github.com/ericknappe/885coversongs.git
cd 885coversongs
```

Open `index.html` directly in a browser:

- Chrome ✓  
- Firefox ✓ (smoothest scrolling)  
- Safari ✓ (best performance when Current Song block is visible)

No build tools required.

---

### 2. Deploy on GitHub Pages
1. Go to **Settings → Pages**
2. Choose **Deploy from branch**
3. Select `main` (or `docs/`) as publishing source
4. Save

Your dashboard becomes available at:

`https://yourusername.github.io/885coversongs/`

To use a custom dataset:

`https://yourusername.github.io/885coversongs/?data_endpoint=data/wxpn_885.json`

---

## 🛠 Known Issues & Notes

### Cover Years chart disabled
The dataset appears to include a `releaseDate` value, but real-world values vary.  
A robust parser is included, but the chart is hidden until confirmed.

### Safari scroll jitter
Safari is sensitive to DOM repaints. Performance improves if the Current Song card is hidden.

### Album art variations
If some entries have missing images or different dimensions, the fixed-height container prevents chart jumps but may still affect Safari’s rendering cost.

---

## 🤝 Contributions
Pull requests are welcome, especially for:
- Improving Cover Years parsing  
- Adding animation smoothing  
- Visual refinements  
- Alternate layouts / themes  

---

## 📜 License
MIT License — free to modify, fork, and build upon.


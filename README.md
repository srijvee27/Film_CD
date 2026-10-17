# A24 Film Catalog — Interactive 3D Showcase

An interactive, high-fidelity web showcase inspired by the A24 film catalog, featuring a real-time WebGL 3D compact disc (CD) carousel powered by Three.js and GSAP.

**Repository:** [https://github.com/srijvee27/Film_CD](https://github.com/srijvee27/Film_CD)

---

## Overview

This project is a recreation of the A24 interactive film gallery experience. It showcases iconic and upcoming A24 film productions through a custom-built 3D physical disc carousel. Each film is represented by a physical CD model complete with realistic material properties—such as front clearcoat gloss, back metallic iridescence, transparent inner hubs, and printed face textures. Users can smoothly drag, swipe, wheel-scroll, and inspect individual titles with cinematic transitions.

### Featured Titles in Catalog
- **Backrooms** (2026)
- **The Invite** (2026)
- **Tony** (2026)
- **Marty Supreme** (2025)
- **The Smashing Machine** (2025)
- **The Brutalist** (2024)
- **The Zone of Interest** (2023)
- **Everything Everywhere All at Once** (2022)
- **Uncut Gems** (2019)
- **Hereditary** (2018)
- **Lady Bird** (2017)
- **Ex Machina** (2015)

---

## Features

- **3D WebGL CD Carousel:** Real-time Three.js scene rendering procedural and textured 3D compact discs with physical shaders (clearcoat, iridescence, rough metallic backs, and transparent plastic hubs).
- **Physics & Motion Animation:** Smooth gesture handling, momentum dragging, wheel ticks, friction, snap physics, and tilt effects powered by GSAP.
- **Dynamic Content Bindings:** Film metadata, directors, cast lists, release years, review quotes, and star ratings parsed directly into interactive views.
- **Quick-Access Film Index:** Dropdown navigation overlay with quick jump links for every release in the archive.
- **Custom Typography:** Integrated web fonts including `PPEiko-Regular`, `PPMuseum-Regular`, and `PPNeueMontreal-Medium`.
- **Zero-Dependency Local Server:** Built-in lightweight Node.js HTTP static file server supporting SPA route fallbacks and MIME types.

---

## Technology Stack

- **Frontend / Rendering:** Three.js (WebGL), GSAP (GreenSock Animation Platform), Barba.js transition hooks
- **Build / Bundle:** Astro & Vite asset bundling (`_astro/`)
- **Server:** Node.js standard library (`http`, `fs`, `path`) — no external runtime npm dependencies required
- **Assets:** Custom WebP disc artwork, SVG vectors, AVIF textures, and WOFF2 fonts

---

## Prerequisites

- **Node.js:** v16.0.0 or higher (Node 18+ or 20+ recommended)
- A modern web browser with **WebGL 2.0** enabled (Chrome, Edge, Firefox, Safari)

---

## Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/srijvee27/Film_CD.git
   cd Film_CD
   ```

2. **Verify dependencies:**
   The included static server uses native Node.js core modules (`http`, `fs`, `path`). No third-party npm packages are required to run the local server.

---

## Running Locally

Start the local server using npm:

```bash
npm start
```

or directly using Node.js:

```bash
node server.js
```

Once running, open your browser and navigate to:
```
http://localhost:3000/
```

To stop the server, press `Ctrl + C` in your terminal.

---

## Project Structure

```
Film_CD/
├── .gitignore                   # Git ignore patterns (node_modules, logs, .env)
├── README.md                    # Project documentation
├── index.html                   # Main HTML document with catalog data & DOM structures
├── package.json                 # Project metadata and run scripts
├── server.js                    # Zero-dependency Node.js HTTP server (port 3000)
├── _astro/                      # Production scripts, Three.js modules, and stylesheets
│   ├── bootstrap.*.js           # Core animation and GSAP initialization
│   ├── main.*.js                # 3D carousel logic and disc physics
│   ├── three.module.*.js        # Three.js WebGL rendering engine
│   └── ExportPage.*.css         # Typography and layout styling
├── fonts/                       # Custom typography (WOFF2)
│   ├── PPEiko-Regular.woff2
│   ├── PPMuseum-Regular.woff2
│   └── PPNeueMontreal-Medium.woff2
└── images/                      # Static branding, textures, and CD disc artworks
    ├── discs/                   # WebP textures for individual film discs
    ├── a24thumb.png
    ├── favicon.png
    ├── grid-tile.svg
    ├── noise_1noise.avif
    └── webclip.png
```

---

## Environment Variables & Database

- **Environment Variables:** None required. The project runs completely self-contained as a client-side WebGL application.
- **Database:** None required. Film metadata and assets are structured within the application DOM and local asset directory.

---

## Troubleshooting

- **Black or Blank Canvas:**
  Ensure your browser supports WebGL 2.0 and that hardware acceleration is enabled in your browser settings (`Settings` > `System` > `Use graphics acceleration when available`).
- **Port 3000 In Use:**
  If port `3000` is already in use by another service, edit the `PORT` constant near the top of [server.js](server.js):
  ```javascript
  const PORT = 3001; // Change to an available port
  ```

---

## License

This project is licensed under the **ISC** license as specified in `package.json`.

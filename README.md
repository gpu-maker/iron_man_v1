# KESTREL — Armored Flight Sim

A first-person 3D armored-suit combat game that runs in any modern browser on phones, tablets and computers. You fly through a neon night city, fight waves of war-frame robots with four weapon systems, and spend credits between sectors to upgrade your suit.

**Play:** `https://<your-username>.github.io/<repo-name>/`

![KESTREL preview](icons/og-image.png)

## Features

- A full helmet HUD: compass, speed and altitude gauges, radar, a target panel, threat warnings, hit-direction arcs, a lead indicator and a suit diagram that tracks damage to each body part
- A visor you can open. It switches the HUD off and leaves your armor exposed.
- Four weapons: a repeater gun, a beam laser, guided rockets, and swarm pods that lock up to four targets and ripple-fire mini-rockets
- Rockets that kick off the launcher, light their motor, burn out and coast, steer toward where a target is heading, explode on a proximity fuse and leave smoke trails
- Limited ammo, refilled by supply caches that destroyed robots drop
- Five waves per sector, then a debrief with stats, an upgrade shop (8 upgrades with multiple levels) and repair or resupply services
- Bloom glow, color grading, searchlights, clouds, ground mist and moving traffic
- Synthesized sound effects. There are no audio files.
- Installable as an app, and playable offline after the first visit

## Controls

| Action | Keyboard and mouse | Touch |
|---|---|---|
| Fly (forward follows your aim, so look up to climb) | W A S D | Left stick |
| Straight up / down | Space or E / C or X | ▲ / ▼ |
| Boost | Shift | — |
| Aim | Mouse (click to capture) or arrow keys | Drag the right side of the screen |
| Fire | Left click or F | FIRE |
| Weapons | 1 gun · 2 laser · 3 rockets · 4 swarm, Q or the mouse wheel to cycle | Weapon buttons |
| Visor | V | VISOR |
| Pause | P or Esc | II |

**Lock-on:** with rockets selected, hold your aim on a robot until you see LOCK. With swarm pods selected, sweep your aim across up to four robots, then fire.

## Deploy to GitHub Pages

1. Create a new repository on GitHub, for example `kestrel`.
2. Upload everything in this folder to the root of the repository, including the hidden `.nojekyll` file.
   - **On the website:** *Add file → Upload files*, then drag in the folder's contents.
   - **From a terminal:**
     ```bash
     git init
     git add .
     git commit -m "KESTREL"
     git branch -M main
     git remote add origin https://github.com/<your-username>/kestrel.git
     git push -u origin main
     ```
3. In the repository, open **Settings → Pages**. Under **Build and deployment**, set **Source** to *Deploy from a branch*, then choose **Branch: `main`** and folder **`/ (root)`**, and save.
4. After a minute or two the game is live at `https://<your-username>.github.io/kestrel/`.

**Optional:**
- Link previews on some sites need an absolute image URL. Replace `icons/og-image.png` in the `og:image` tag in `index.html` with the full address.
- When you change any file, bump `VERSION` in `sw.js` (for example to `kestrel-v2`) so returning players get the new version instead of their cached copy.

## Run it locally

The offline cache only works over `http(s)`, so serve the folder rather than double-clicking `index.html`:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Project layout

```
index.html            the whole game (HTML, CSS and JavaScript in one file)
sw.js                 offline cache
manifest.webmanifest  install / home-screen settings
favicon.svg, icons/   icons and the social preview image
vendor/               three.js r128 and its post-processing passes (MIT)
.nojekyll             tells GitHub Pages to serve files as-is
```

## Credits

- 3D rendering by [three.js](https://threejs.org) r128 (MIT License, see `vendor/THREE-LICENSE.txt`)
- Fonts: Orbitron and Share Tech Mono from Google Fonts (SIL Open Font License), loaded at runtime with system fallbacks
- Everything else (the suit, robots, city, HUD, sound and gameplay) is original to this project.

Add a `LICENSE` file if you want to set terms for others reusing your code.

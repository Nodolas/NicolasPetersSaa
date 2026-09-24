# Personal Portfolio — Nicolas Peters Saa

**Live:** https://nodolas.github.io/NicolasPetersSaa/

A single-file, scroll-driven portfolio with a white, quantum-inspired look. Black and white with one light-blue accent (`#9ad8ff`), Anton headlines, and Mona Sans body text. Smooth scrolling comes from Lenis and GSAP ScrollTrigger, loaded from a CDN. There is no build step.

---

## What's inside

| File | Purpose |
|---|---|
| `index.html` | The whole site: HTML, CSS and JS in one file |
| `media/picturesofme/headshot-cut.webp` | Transparent cut-out portrait used in the hero |
| `media/picturesofme/headshot-web.jpg` | Web-sized portrait for the About section and link previews |
| `media/picturesofme/Headshot.jpg` | Original full-resolution photo, the source for both files above |
| `media/certificates/` | Certificate images and PDFs |
| `media/video/` | Optional background video for the IBM Quantum section, see `media/video/README.md` |
| `media/favicon.svg` | Static qubit icon, the fallback for browsers that don't animate the favicon |
| `media/apple-touch-icon.png` | 180px home-screen icon for phones |
| `main.html` | Old template from the first version, not linked from the site |
| `package.json` | Dev-server scripts only |

---

## How the page works

In order from top to bottom:

1. **Intro screen.** A black screen with a light-blue counter from 00 to 100 and the name. It slides up, then the hero animates in letter by letter.
2. **Hero.** "NICOLAS" sits behind the cut-out portrait and "PETERS SAA" sits in front. An animated Bloch-sphere qubit is drawn on a canvas behind everything and follows the mouse slightly. The hero is sticky: on scroll the name lines drift apart, the photo shrinks, and the rest of the page slides up over it.
3. **Ticker strip.** A light-blue marquee with qubit-ring separators.
4. **About.** The text reveals word by word as you scroll, next to the portrait. Four stats count up.
5. **IBM Quantum.** A full-screen section over an animated qubit-lattice canvas, or over a video if `media/video/quantum-chip.mp4` exists.
6. **Experience.** Pinned horizontal scroll on desktop, stacked cards on mobile.
7. **Skills, Freelance, Certifications, Currently building.** Each section header rule ends in a tiny circuit glyph: an H gate, a qubit and a measurement.
8. **Contact** and footer.

Small quantum details: ket-style section labels such as `|01⟩`, a spinning orbit around the nav logo dot, "In progress" dots that flicker between hollow and filled, and a favicon with particles orbiting a qubit. The favicon is animated by JS in Chrome, Edge and Firefox. Other browsers show the static SVG.

With `prefers-reduced-motion` set, the intro, smooth scrolling, pinning and looping animations all switch off.

---

## Common edits

All content lives in `index.html`. Search for these to find each part:

| What | Search for |
|---|---|
| Hero name lines | `id="name-back"` and `id="name-front"` |
| Hero intro text | `class="hero-meta"` |
| "Now" box, top right of the hero | `class="now-box"` |
| Ticker words | `id="marquee-track"` |
| About text | `id="manifesto"` |
| Stats | `class="stats"` |
| IBM Quantum section | `<!-- ============ QUANTUM FEATURE` |
| Experience cards | `class="exp-card` |
| Skills | `<!-- ============ SKILLS` |
| Freelance cards | `class="fl-card` |
| Certificate cards | `class="cert fade"` |
| "Currently building" rows | `class="now-row` |
| Email and social links | `mailto:` / `linkedin.com` / `github.com/Nodolas` |
| Accent colour | `--accent:` in `:root`, plus `154,216,255` and `#9ad8ff` in the canvas code |

**Add a certificate.** Put the image or PDF in a folder under `media/certificates/`, then copy an existing card:

```html
<div class="cert fade" onclick="openLightbox('media/certificates/folder/image.png', 'media/certificates/folder/file.pdf', 'Title')">
    <div class="cert-media"><img src="media/certificates/folder/image.png" alt="Title" loading="lazy"></div>
    <div class="cert-info"><div><h4>Title</h4><div class="iss">ISSUER</div></div><span class="cert-arrow">&nearr;</span></div>
</div>
```

Pass `null` instead of the PDF path if there is no PDF. For a PDF-only certificate, copy one of the cards that uses `window.open(...)` and a `cert-art` tile.

**Mark a project as done.** In "Currently building", change `class="status"` to `class="status done"` and the text to `Complete`.

---

## Replacing the portrait

The hero needs a portrait with a transparent background, so the name can sit behind it. The current `headshot-cut.webp` was cut out automatically from `Headshot.jpg`. A dedicated tool gives cleaner hair and shoulder edges:

1. Remove the background with remove.bg, Canva's background remover, or "Select Subject" in Photoshop.
2. Export a PNG or WebP with transparency, about 1800px tall, with the person standing and cropped at the thighs.
3. Save it as `media/picturesofme/headshot-cut.webp`, or keep your own file name and update the hero `<img id="hero-photo">` and the `rel="preload"` line in `<head>`.

File names are case-sensitive on the live site. `Photo.PNG` and `photo.png` are different files there, even though Windows treats them as the same.

---

## Run locally

```bash
npm install     # first time only
npm start       # opens http://127.0.0.1:8080 with live reload
```

`start.bat` does the same with a double-click. Opening `index.html` directly also works, but the fonts and animation libraries need an internet connection because they load from a CDN.

---

## Publishing

The site is served by **GitHub Pages from the `main` branch, root folder**. Every push or merge to `main` updates https://nodolas.github.io/NicolasPetersSaa/ within about a minute. Hard-refresh with Ctrl+F5 to see it.

Recommended workflow:

1. Create a branch for a change, for example `git checkout -b new-cert`.
2. Commit and push it, then preview locally with `npm start`.
3. Open a pull request into `main` on GitHub and merge it. That publishes the change.

Other design versions are kept as branches:

| Branch | What it is |
|---|---|
| `main` | The live site, landing v2 |
| `landing-v2` | Branch the live design was merged from |
| `quantum-redesign` | Earlier white, IBM-style version with the expanding "quantum window" hero |

To preview another version locally, run `git checkout quantum-redesign` and refresh, then `git checkout main` to come back.

---

## Licence

Do whatever you want with it. Credit appreciated but not required.

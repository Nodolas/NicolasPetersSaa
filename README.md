# Personal Portfolio — Nicolas Peters Saa

A single-file personal portfolio with an animated constellation background, scroll reveal effects, a certificate lightbox, and a mobile hamburger nav. No frameworks, no build tools, no dependencies beyond a local dev server.

---

## What's inside

| File | Purpose |
|---|---|
| `index.html` | Everything — all HTML, CSS, and JS in one file |
| `media/favicon.svg` | SVG favicon (N-letterform + cyan node dots) |
| `media/picturesofme/` | Profile photo |
| `media/certificates/` | Certificate images and PDFs |
| `package.json` | Dev server scripts only |

---

## Copy this for your own portfolio

### 1. Get the files

Download or clone the repo, then delete `node_modules/` — you don't need it until you run the dev server.

### 2. Replace personal content in `index.html`

Open `index.html` and swap out the following (search by keyword):

| What to change | Search for |
|---|---|
| Your name (title bar + hero) | `Nicolas Peters Saa` |
| Your tagline / roles | `Innovation Management` |
| Your email | `mailto:` |
| LinkedIn URL | `linkedin.com/in/` |
| GitHub URL | `github.com/` |
| About section text | `<!-- About -->` |
| Experience entries | `<!-- Experience -->` |
| Education entries | `<!-- Education -->` |
| Skills tags | `<!-- Skills -->` |
| Freelance service cards | `<!-- Freelance -->` |

### 3. Replace the profile photo

Drop your photo into `media/picturesofme/` and update the `src` in the hero `<img>` tag:

```html
<img src="media/picturesofme/YourPhoto.jpg" alt="Your Name" ...>
```

### 4. Replace certificates

Put your certificate images (PNG/JPG) and PDFs into subfolders under `media/certificates/`. Then update the certificate cards in the `#certifications` section. Each card follows this pattern:

```html
<div class="cert-card reveal">
    <img src="media/certificates/yourfolder/cert.png" alt="Cert Name" class="cert-img">
    <div class="cert-info">
        <div class="cert-title">Certificate Name</div>
        <div class="cert-issuer">Issuing Organisation</div>
        <div class="cert-links">
            <a href="media/certificates/yourfolder/cert.pdf" class="cert-link" target="_blank">View PDF</a>
        </div>
    </div>
</div>
```

### 5. Update the SEO meta tags

Near the top of `<head>`, update these lines with your own details:

```html
<meta name="description" content="Your description here">
<meta name="keywords" content="Your, Keywords, Here">
<meta name="author" content="Your Name">
<meta property="og:title" content="Your Name | Your Title">
<meta property="og:description" content="...">
<meta property="og:image" content="media/picturesofme/YourPhoto.jpg">
```

> **Note:** `og:image` must be an **absolute URL** (e.g. `https://yourdomain.com/media/...`) for LinkedIn and WhatsApp previews to work. Update it after deployment.

### 6. Replace the favicon

Edit `media/favicon.svg` — it's a plain SVG you can open in any text editor or vector tool. Swap the strokes/dots for your own initials or icon. Keep the `viewBox="0 0 32 32"` so it stays crisp.

---

## Run locally

**First time only:**
```bash
npm install
```

**Then start the dev server:**
```bash
npm start
```

The site opens at `http://127.0.0.1:8080` with live-reload on save.

Alternatively, just open `index.html` directly in your browser — it works without any server (no fetch calls, no module imports).

---

## Deploy to GitHub Pages

1. Create a GitHub repo named `yourusername.github.io`
2. Push `index.html`, `media/`, and `package.json` (skip `node_modules/`)
3. Go to **Settings → Pages** and set source to the `main` branch, root folder
4. Your site will be live at `https://yourusername.github.io` within a few minutes
5. Update `og:image` and `twitter:image` to the full `https://` URL after deployment

---

## Customise the background

The animated constellation is pure Canvas 2D (no libraries). Find it near the bottom of `index.html` under the comment `PARTICLE NETWORK`. The key values to tweak:

```js
const N = 170;          // number of nodes — increase for a denser cloud
const LINK_DIST = 220;  // px — nodes within this distance get connected
```

---

## Licence

Do whatever you want with it. Credit appreciated but not required.

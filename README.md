# Personal Website

This repository contains a single-page portfolio meant to showcase who you are and your career history. It is built with plain HTML, CSS, and JavaScript, and includes a dynamic WebGL background animation using [three.js](https://threejs.org).

## Getting Started (Development)

1. **Open in VS Code** – simply open the workspace folder in VS Code.
2. **Live Preview**
   - Install the **Live Server** extension for VS Code and click "Go Live" in the status bar. This will serve `index.html` (or rename `main.html` to `index.html`) and reload automatically when you save changes.
   - Alternatively, from a terminal you can run a simple HTTP server e.g.:
     ```powershell
     # using Python (if installed)
     cd "c:\Programming\Personal Website"
     py -m http.server 8000
     # or with Node (install live-server globally or via npx)
     npx live-server --port=8000
     ```
3. **Debugging** – open the browser's developer tools (F12) to inspect elements, view console messages, and profile animations. Resize the window to test responsiveness.
4. **Customize** – update text placeholders, your photo, email address, and links to reflect your personal information. See comments inside `main.html` for guidance.

## Animations

The page includes:

- A custom cursor and subtle interactive blob effect.
- Gooey morphing gradients behind the content (CSS).
- A full-screen three.js particle system that rotates and responds to mouse movement. You can extend this animation with shaders, morphing shapes, or a particle system like those seen in the example tweets (see `three.js` documentation or CodePen for inspiration).

  The animations referenced in the tweets are generated with Processing/p5.js and Three.js with GLSL shaders; you can embed such sketches entirely inside the `<canvas>` instead of the basic particle cloud. For example:
  ```js
  // load p5.js and copy the sketch code from the tweet/CodePen
  ```
  or write a custom `ShaderMaterial` and animate vertices via noise for morphing backgrounds.
  Use the comments in `main.html` as a starting point and experiment while watching the live preview.

If you want more advanced visuals, consider creating a `shaderMaterial` with GLSL or integrating a library such as [Anime.js](https://animejs.com/) for timelines. The current setup is a starting point that you can evolve.

## Deployment to GitHub Pages

1. Rename `main.html` to `index.html` (GitHub Pages looks for `index.html` in the root). The README already references this recommendation.
2. Commit and push your changes to a GitHub repository named `yourusername.github.io` or enable Pages on any repository and set the source to the `main` branch.
3. After a few minutes your site will be live at `https://yourusername.github.io/`.

## Notes

- The project currently uses CDN links for three.js. You can also download the library and serve it locally if desired.
- For mobile debugging, connect your device to the same network and navigate to `http://<machine-ip>:8000`.
- Keep the `cursor-blob` styles if you want to maintain the custom cursor; remove `cursor: none;` if you prefer the system pointer.

Feel free to enhance the animation code or convert this into a more complex build system (React/Vite/etc.) later. The current structure is intentionally minimal so you can debug in the browser while editing.

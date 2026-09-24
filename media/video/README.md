# Video slot

The live design has one optional video. Drop the file into this folder and the page picks it up automatically, with no code change. Until the file exists, the section shows an animated qubit-lattice canvas.

| File | Used in | Length | Size / format |
|---|---|---|---|
| `quantum-chip.mp4` (+ optional `quantum-chip.webm`) | Background of the "IBM Quantum" section | 10-15 s seamless loop | 1920x1080, H.264, no audio, under ~8 MB |

## Brief: quantum-chip
A macro shot of a superconducting quantum chip or the gold "chandelier" cryostat. Use cool, light tones: silver, white and soft light-blue highlights (`#9ad8ff`) on a light background. The camera moves in a slow dolly or orbit. Keep the left third of the frame calm, because the text sits there. No text, no logos. It must loop seamlessly, with the first and last frames identical.

## Export tips
Export at 24-30 fps and strip the audio:

```
ffmpeg -i in.mp4 -an -c:v libx264 -crf 24 -preset slow -movflags +faststart quantum-chip.mp4
```

Note: the older `quantum-redesign` branch also used a `hero-qubit.mp4` slot. The live design draws the hero qubit on a canvas, so it doesn't need that file.

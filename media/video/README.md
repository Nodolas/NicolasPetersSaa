# Video slots

Drop the files below into this folder. The page detects them automatically and
switches from the animated canvas placeholder to the video. No code change needed.

| File | Used in | Length | Size / format |
|---|---|---|---|
| `hero-qubit.mp4` (+ optional `hero-qubit.webm`) | Hero "window" you scroll into | 8-12 s seamless loop | 1920x1080, H.264, no audio, under ~6 MB |
| `quantum-chip.mp4` (+ optional `quantum-chip.webm`) | "IBM Quantum" feature section background | 10-15 s seamless loop | 1920x1080, H.264, no audio, under ~8 MB |

## Brief 1: hero-qubit
A single qubit / Bloch sphere on a white or very light (#f4f4f4) background.
Thin dark wireframe sphere, a glowing blue-to-violet state vector slowly precessing,
faint particles orbiting. Camera almost static, very slow drift. No text, no logos.
Must loop seamlessly (first and last frame identical). Bright, airy, lots of white.

## Brief 2: quantum-chip
Macro shot of a superconducting quantum chip or the gold "chandelier" cryostat,
cool tones (silver, gold, blue highlights) on a light background, slow dolly or
orbit. Left third of the frame should be calm (text sits there). No text, no logos.
Must loop seamlessly.

Tips: export at 24-30 fps, use two-pass H.264 (CRF 22-26), strip audio.
`ffmpeg -i in.mp4 -an -c:v libx264 -crf 24 -preset slow -movflags +faststart hero-qubit.mp4`

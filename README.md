# Flux

Control **voice effects** and **visual effects** with your hands. Your webcam tracks your
gestures in real time (Google MediaPipe Hand Landmarker) and your microphone gets warped
live through the Web Audio API — harmonies, pitch, echo, robot and more.

Everything runs **100% in the browser** — no server, no data leaves your device.

🔗 **Live:** https://ojuliaspinola.github.io/Flux/

## How it works

A gesture picks the effect; your hand position fine-tunes it ("both combined").

| Fingers | Effect | ↕ Height | ↔ Tone |
|--------:|--------|----------|--------|
| ✊ 0 | **Clean** (bypass) | — | — |
| ☝️ 1 | **Harmonizer** — adds 3rd + 5th harmony voices | harmony volume | octave sparkle |
| ✌️ 2 | **Pitch shift** (±1 octave) | pitch | fine-tune |
| 🤟 3 | **Echo / Space** | echo amount | delay time |
| 🖖 4 | **Robot** (ring modulation) | carrier pitch | dry ↔ robot mix |
| 🖐️ 5 | **Telephone** (band-limited distortion) | drive | tone |

- **Second hand height** controls the master volume.
- Visuals: mirrored camera feed, neon hand skeleton, fingertip particles coloured per
  effect, and motion trails (long on Echo) that pulse with your microphone level.

## Tips

- **Use headphones.** Speakers will feed back into the mic (mic processing is disabled on
  purpose so the effects sound clean).
- Works best in good lighting with your hand fully in frame.
- Requires a browser with WebGL + Web Audio (Chrome, Edge, Safari, Firefox).
- Camera + microphone require **HTTPS** — the live GitHub Pages URL works; for local dev
  use a local server (below), not `file://`.

## Run locally

```bash
# from the project folder
python3 -m http.server 8000
# then open http://localhost:8000
```

## Tech

- [MediaPipe Tasks Vision](https://developers.google.com/mediapipe) — on-device hand tracking
- Web Audio API — real-time DSP graph (pitch shifter after Chris Wilson's *jungle.js* technique)
- Plain HTML/CSS/JS, no build step

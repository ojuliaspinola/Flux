# Flux — gesture omnichord

A gesture-played **omnichord**. Your webcam tracks your hands (Google MediaPipe Hand
Landmarker); a Web Audio synth makes the sound. **No microphone needed** — Flux generates
its own audio.

Everything runs **100% in the browser** — no server, no data leaves your device.

🔗 **Live:** https://ojuliaspinola.github.io/Flux/

## How to play

- **Left side = chord pads.** Hover your hand over a pad to select the chord. The diatonic
  chords of C major are laid out top-to-bottom: **C, Dm, Em, F, G, Am, B°**. The selected
  chord sustains softly, like an omnichord's chord buttons.
- **Right side = the harp / strumplate.** Sweep your hand across the vertical strings to
  strum the selected chord. **Sweep fast to arpeggiate**, move slowly for individual
  plucks — strum speed sets each note's brightness and volume.
- Works with **one or two hands** — it's zone-based, so either hand can pick chords or
  strum depending on which side of the screen it's on.
- **Make a fist** (or take your hands off the screen) to stop playing — the sustained chord
  fades out smoothly and ringing notes decay naturally. Open your hand to resume.

The look is *devotional circuitry*: a PCB-trace background, harp strings rendered as copper
traces with solder-pad nodes that light magenta when struck, silkscreened chord pads, CRT
scanlines, and the flesh / machine / holy triangle on the start screen. The strings ripple
and spark as you play, through lush convolution reverb.

## Tips

- Turn your **sound on** (no headphones needed — there's no mic).
- Good lighting and keeping your hand fully in frame improves tracking.
- Works in Chrome, Edge, Safari, or Firefox with WebGL + Web Audio.
- Camera requires **HTTPS** — the live URL works; for local dev use a local server (below),
  not `file://`.

## Run locally

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

## Tech

- [MediaPipe Tasks Vision](https://developers.google.com/mediapipe) — on-device hand tracking
- Web Audio API — polyphonic synth, convolution reverb, per-note envelopes
- Plain HTML/CSS/JS, no build step

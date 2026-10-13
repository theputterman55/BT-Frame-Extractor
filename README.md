# BT Frame Extractor

Pulls frames out of full-length videos (30-40 seconds or longer) entirely on your phone. Nothing is uploaded, and there is no length limit. Built for collecting training images for the BagTrak cornhole bag detector.

Live page: https://theputterman55.github.io/BT-Frame-Extractor/

## How to use

1. Open the page in Chrome and tap **Choose video**.
2. Pick a mode:
   - **Motion-triggered** (default): drag a box around the players, tap **Scan for motion**, check the graph, then tap **Extract**. Only the moments around movement are saved (1 second before and 2 seconds after by default). Change sensitivity or the before/after seconds and the shaded bands update instantly.
   - **Every frame at a set rate**: saves frames evenly across the whole video.
3. Pick frames per second, image size and JPEG quality, then **Save ZIP**.

The ZIP holds numbered JPEGs plus `frames.csv` (file, time in seconds, width, height, motion event number, motion score, and L or R for which side of the frame the motion was on) and `source.json` (video name, length, settings, motion windows).

## How motion detection works

Each scan frame is compared to the one before it, only inside the box. The share of pixels that changed is the motion score. The threshold adapts to the video's own background noise. No machine learning is involved. It's meant to wake up on a thrower's arm swing; a pose model could replace it later.

## Install on a phone

Open the page in Chrome, then menu, **Add to Home screen** (or **Install app**). After the first visit it also opens offline.

## Files

- `index.html` - the whole app (extraction, ZIP writer, UI)
- `sw.js` - offline cache
- `manifest.webmanifest`, `icon-192.png`, `icon-512.png` - home screen install

# BT Frame Extractor

Pulls frames out of full-length videos (30-40 seconds or longer) entirely on your phone. Nothing is uploaded, and there is no length limit. Built for collecting training images for the BagTrak cornhole bag detector.

Live page: https://theputterman55.github.io/BT-Frame-Extractor/

## How to use

1. Open the page in Chrome and tap **Choose video**.
2. Pick frames per second (3 to 5 is plenty for training data), image size and JPEG quality.
3. Tap **Extract frames**, then **Save ZIP**.

The ZIP holds numbered JPEGs plus `frames.csv` (file, time in seconds, width, height) and `source.json` (video name, length, settings).

## Install on a phone

Open the page in Chrome, then menu, **Add to Home screen** (or **Install app**). After the first visit it also opens offline.

## Files

- `index.html` - the whole app (extraction, ZIP writer, UI)
- `sw.js` - offline cache
- `manifest.webmanifest`, `icon-192.png`, `icon-512.png` - home screen install

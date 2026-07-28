# Kenny´s Tuner 🎸

A free, offline-capable instrument tuner that runs entirely in your browser — no app store, no install, no account, no ads.

**👉 Try it now: [kennystuner.netlify.app](https://kennystuner.netlify.app/)**

![license](https://img.shields.io/badge/license-MIT-brass) ![offline](https://img.shields.io/badge/works-offline-8faa7c) ![no install](https://img.shields.io/badge/install-optional-c9a15a)

---

## What it does

- **Needle tuner** — real-time pitch detection with a classic analog-style gauge and cents readout
- **Spectrum view** — a live scrolling waterfall of everything the microphone hears, so you can find your note even in a noisy room (swipe sideways to switch views)
- **7 instruments** — Guitar, Bass, Violin, Ukulele, Banjo, Mandolin, Cello
- **21 built-in tunings** — Standard, Drop D, DADGAD, Open G/D, Half Step Down, and more, depending on instrument
- **Custom tunings** — set any string to any note yourself
- **440 Hz / 432 Hz** reference pitch toggle
- **Fully offline** — install it once, then use it with no internet connection at all
- **No account, no tracking, no ads**

## Using it

1. Open **[kennystuner.netlify.app](https://kennystuner.netlify.app/)** in your phone or desktop browser
2. Tap **Start tuner** and allow microphone access
3. Play a note — the needle and note name show how in-tune you are
4. Swipe sideways for the **Spectrum** view, or pick an instrument/tuning from the tabs and dropdown
5. Tap the **Readme** button inside the app for a full walkthrough of every feature

### Install it as an app (recommended — enables offline use)

The tuner is a [Progressive Web App](https://web.dev/explore/progressive-web-apps) (PWA). Installing it lets it run without an internet connection and gives it its own home screen icon.

- **Android (Chrome):** tap ⋮ → "Add to Home screen" / "Install app"
- **iPhone (Safari):** tap the Share icon → "Add to Home Screen"
- **Desktop (Chrome/Edge):** click the install icon in the address bar

> **Note:** microphone access requires a secure (`https://`) origin. Opening the raw `index.html` file directly from your file system (`file://`) will not work — always use the hosted link above, or serve the files yourself over HTTPS (see below).

## Self-hosting

This is a static site — no build step, no server, no dependencies. Everything needed is in this repository.

1. Clone or download this repo
2. Upload all files (`index.html`, `manifest.webmanifest`, `sw.js`, and the three icon PNGs) to **the same folder** on any HTTPS web host
3. Open the page once while online so the service worker caches it
4. Install it to your home screen — it now works fully offline

That's it. There's nothing to build or compile.

## How the tuning detection works

Pitch is detected with an autocorrelation algorithm (ACF2+ style) run on live microphone audio via the Web Audio API — no external libraries, no server round-trip, everything happens on-device. The Spectrum view uses a peak-picking FFT analysis with adjustable **Resolution**, **Sensitivity**, and **Noise Filter** controls so you can tune it for your instrument and environment.

## Tech

Plain HTML, CSS and JavaScript — one self-contained `index.html`, a service worker (`sw.js`) for offline caching, and a web app manifest for installability. No frameworks, no build tools, no npm install.

## Support

If this is useful to you, you're welcome to [buy me a coffee](https://www.paypal.com/ncp/payment/5PU52AGKWEQVA) ☕ — totally optional, the tuner is free either way.

## License

[MIT](LICENSE) — free to use, modify, and share.

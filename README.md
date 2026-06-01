# Golden Harmonics

A browser-based sound generator for sound-therapy practice. It synthesizes pure sine tones arranged by the **golden ratio** (φ ≈ 1.618) around a chosen base frequency, producing the shimmering, non-repeating "harmonic field" used in golden-ratio sound work.

Runs entirely client-side with the Web Audio API — no server, no build step, no dependencies. A single static `index.html`. Works in Safari and Chrome on macOS and iOS.

## Use

- **Pick a base** — tap a frequency from the ring around the orb (lowest at the top, increasing clockwise), or type any frequency (20–12000 Hz) into *Custom*.
- **Choose a mode** — *Golden φ* and *Fibonacci* build a field of overtones above the base; *Schumann* and *Binaural* are brainwave-beat modes that ignore the base. Tap the **ⓘ** beside the mode name for a plain-language explanation of what it does.
- **Shape the harmonics** — the strip of toggles spans the mode's partials. Each chip is one partial; tap to include or drop it. *All* / *None* reset the selection. Partials that fall outside the audible range dim automatically.
- **Binaural beat** — in Binaural mode, set the perceived beat with the slider or the band buttons (Delta … Beta). Use headphones — the effect only works when each ear hears its own tone.
- **Play / pause** — tap the glowing orb (or the button). The orb breathes with the live sound.
- **Volume** — master slider, with click-free fade in/out.

On iPhone, open the page in Safari → **Share → Add to Home Screen** for a fullscreen, app-like launch. If it's silent, check the side mute switch — iOS routes Web Audio through it.

## About the sound

Ordinary harmonics are integer multiples of a fundamental (f, 2f, 3f, …) and fuse into a single perceived pitch. These partials instead sit at **f · φⁿ**, where φ is the golden ratio — the "most irrational" number, so the partials never settle into a simple repeating relationship. The result is an inharmonic, continuously shifting texture rather than one fused tone. Each partial carries an independent slow amplitude swell so the field feels alive, the level curve is weighted toward the mids with a gentle high-end shimmer, and gains are normalized so the mix never clips no matter how many partials are active.

## Deploy (Cloudflare Pages)

1. Cloudflare dashboard → **Workers & Pages → Create → Pages → Connect to Git**.
2. Authorize GitHub and select this repository.
3. Build settings — **Framework preset:** None · **Build command:** *(leave empty)* · **Build output directory:** `/`.
4. **Save and Deploy.** Every push to `main` redeploys automatically; a `*.pages.dev` URL is created.
5. *(Optional)* **Custom domains** → add a subdomain (e.g. `harmonics.example.com`) if the zone is on Cloudflare.

## Disclaimer

A sound tool for relaxation and sound-therapy practice. Not a medical device; makes no medical claims.

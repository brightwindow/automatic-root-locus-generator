# Root Locus Plotter

Interactive single-file root locus plotter that runs entirely in the browser. Enter the numerator and denominator coefficients of an open-loop transfer function and visualize how the closed-loop poles move as the gain **K** sweeps from 0 to ∞.

**[Live demo](#)** · No build step, no dependencies, no backend.

## Features

- **Real-time K slider** — drag (or type a value directly) and watch the closed-loop poles glide along the locus
- **Pure JavaScript root finder** — Durand-Kerner method for arbitrary-degree polynomials
- **Proper or improper systems** — no restriction on numerator/denominator degree
- **Mobile-first** — large touch targets, sticky control panel, responsive canvas
- **Analysis readout** — open-loop poles/zeros, number of asymptotes, asymptote centroid
- **Presets** — common textbook examples one tap away
- **Single HTML file** — drop it into GitHub Pages, Netlify, or open locally

## Usage

Just open `index.html` in any modern browser. Enter polynomial coefficients in descending order, separated by spaces or commas:

| Transfer function | Numerator | Denominator |
|---|---|---|
| `1 / [s(s+1)(s+2)]` | `1` | `1 3 2 0` |
| `(s+1) / s²` | `1 1` | `1 0 0` |
| `(s+4) / [s(s²+2s+5)]` | `1 4` | `1 2 5 0` |

The characteristic equation `D(s) + K·N(s) = 0` is solved at hundreds of K samples; adjacent root sets are matched greedily so each branch stays continuous.

## Deploy to GitHub Pages

```bash
git init
git add index.html
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo>.git
git push -u origin main
```

Then in repo settings → Pages → set source to `main` branch, root folder. Your plotter will be live at `https://<your-username>.github.io/<repo>/`.

## Tech

- Vanilla HTML/CSS/JS — no frameworks
- Canvas 2D rendering with devicePixelRatio scaling
- Durand-Kerner iteration (Weierstrass method) for polynomial roots
- Inter + JetBrains Mono via Google Fonts

## License

MIT

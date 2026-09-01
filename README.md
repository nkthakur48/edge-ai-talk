# Edge AI: Unleashed — On-Device Intelligence

Slides and live demos for a Faculty Development Programme talk on running AI models fully offline — first in the browser (WebGPU + WebLLM/MLC), then on the full machine (LM Studio). No API keys, no cloud, no network calls during inference.

## Landing page

- **[index.html](index.html)** — start here. Links to the slides and every live demo below.

## Slides

- **[slides.html](slides.html)** — the reveal.js deck. Open directly in a browser, or serve locally (`npx serve` / `python3 -m http.server`) for the best experience.

## Live demos

All demo pages are self-contained static HTML files — no build step. Browser demos need a WebGPU-capable browser (Chrome/Edge); the model downloads on first load, so pre-load each one before presenting.

| Demo | Path | Runtime | Notes |
|---|---|---|---|
| Translation | [translation.html](translation.html) | WebLLM (MLC) + WebGPU, in-browser | Switch between Qwen3-4B and Gemma-2-2B live to compare quality (e.g. on Tamil) |
| Document Q&A | [docs.html](docs.html) | WebLLM (MLC) + WebGPU, in-browser | Paste plain text, get a grounded summary + sourced Q&A (no PDF upload) |
| Local Translation | [translation-local.html](translation-local.html) | LM Studio (local server) | Hits `http://localhost:1234` with Sarvam-Translate — start LM Studio's server with CORS enabled first |


## Sample data

- **[data-placements-general.txt](data-placements-general.txt)** / **[data-placements-details-2025.txt](data-placements-details-2025.txt)** — a real placement-office corpus (sourced from a college's public placement pages), useful as sample input for the Document Q&A demo's grounded-Q&A story.

## Other files

- `images/` — screenshots and illustrations used by `slides.html`.

## Running locally

Most of these are plain static files, but serve them over HTTP (not `file://`) so the browser's model cache and CORS behave correctly:

```
npx serve .
```

Then open `http://localhost:3000/` (or whichever port `serve` reports) to land on `index.html`.

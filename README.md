# AVC vs HEVC Bandwidth Demo

Single-page demo for sales: **two players** load the same stream, one prefers **AVC (H.264)** and the other prefers **HEVC (H.265)**, while the page shows **total bandwidth consumed in MB** per player and combined.

## Run

Open `index.html` in a browser (Safari/Chrome).

If the browser blocks `file://`, run a quick local server from this folder (use port `8000` to avoid macOS permission issues some users hit on `8080`):

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000/index.html`.

## GitHub Pages

This repo includes a GitHub Actions workflow that deploys the repository root (the `index.html`) to **GitHub Pages** on every push to `main`.

After the first push, enable Pages in GitHub:

- Repo → **Settings** → **Pages** → **Build and deployment** → **Source: GitHub Actions**

## Configure the default stream

Edit `DEFAULT_MANIFEST_URL` in `index.html`, or launch with:

- `index.html?manifest=YOUR_MANIFEST_URL`

## Notes

- Works best with a manifest that includes **both AVC and HEVC 1080p** variants.
- Bandwidth is counted by summing bytes of responses seen by the player (manifest + segments), not an estimate.


# Facial mimicry avatar demo

A browser-based demonstration of a 3D avatar that responds to facial movements. Developed as part of Nicolás González Raposo’s research on emotional coordination and interpersonal interaction.

The demo uses a simple smile-detection heuristic, rather than the more complex emotion-inference pipeline described in the experimental application.

## What the demo shows

- A 3D avatar that imitates detected smiles.
- Head and eye movements reflected in real time.
- Facial-landmark inference assets shipped with the static page.
- A Spanish-language explanation of the demonstration and its relationship to the experimental system.

The page describes an approximate 300 ms smile-response delay. This is a design description, not a measured latency guarantee: actual behavior depends on the browser, device, and initialization time.

## Run locally

The repository contains a static, prebuilt demo. No npm installation or build step is included.

1. Clone or download the repository.
2. In the repository root, start a local HTTP server:

   ```bash
   python3 -m http.server 8000
   ```

3. Open <http://localhost:8000> in a modern browser.
4. Allow camera access if prompted and try smiling and moving your head.

Use localhost for local testing, or HTTPS when hosting the page. Camera access, WebAssembly support, and adequate graphics performance are needed. The camera video element is hidden; the avatar is the visible interface.

## Repository map

| Path | Purpose |
| --- | --- |
| `index.html` | Demo page, layout, explanatory text, and avatar selection. |
| `assets/justSmiles.js` | Prebuilt JavaScript bundle loaded by the page. |
| `avatars/` | 3D avatar models in GLB format. |
| `models/face_landmarker.task` | Facial-landmark model asset. |
| `wasm/` | WebAssembly inference runtime files. |

The selected avatar is set in `index.html` through `window.avatarPath`. Keep the relative asset paths and filename capitalization intact when hosting or changing the model.

## Scope and limitations

This repository is a demonstration artifact. It does not include the original JavaScript project, package manifest, or build configuration required to reproduce the bundle from source.

The page states that it does not store interaction videos. Check the deployed implementation and any hosting changes before using it with participants. This demonstration has not been validated here as a measurement instrument or as a reproduction of the full experimental system.

## Troubleshooting

- **No camera response:** check browser permissions, use localhost or HTTPS, and make sure another application is not blocking the camera.
- **Blank avatar or missing model:** serve the entire repository and check the browser console for missing assets.
- **Slow startup or response:** allow model assets to load and check browser/device performance.

## Contact

Nicolás González Raposo — [nicgonzalezr@udd.cl](mailto:nicgonzalezr@udd.cl)

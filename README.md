# suby

Free subtitle generator for creators, built for accessibility and SEO. Drop in a video and get SRT, VTT or TXT captions.

Transcription runs in the browser with Whisper ([transformers.js](https://github.com/huggingface/transformers.js)). It uses WebGPU when available and falls back to WASM. There is no backend and no per-minute API cost, and video never leaves the user's device.

## Run

Any static file server works; module workers don't load over `file://`.

```bash
python3 -m http.server 8000
```

## Files

- `index.html`: landing page and app UI
- `worker.js`: Whisper pipeline (off the main thread)
- `format.js`: SRT, VTT and TXT writers
- `format.test.mjs`: run with `node format.test.mjs`

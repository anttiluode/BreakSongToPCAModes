# Fast Raw Mode Extractor – GN‑v7 Koopman Modes

Upload any song → get **raw PCA (Koopman) modes** as individual WAV files. No visualisations, just fast extraction. Perfect for preparing audio that bypasses Suno’s false‑positive content flags.

## What it does

- Takes your audio (any length) and decomposes it into `raw_mode_00.wav`, `raw_mode_01.wav`, … using delay‑embedding and randomized SVD.
- Each mode is a **single‑layer reconstruction** of the original song – it sounds similar but breaks the precise fingerprinting patterns used by platforms like Suno.

## How to use

1. Upload your song (WAV, MP3, etc.).
2. Adjust parameters (defaults work well):
   - `dim` = embedding dimension (32 = good speed/quality)
   - `tau` = delay step (3)
   - `k` = number of raw modes to extract (8)
3. Click **Extract Raw Modes**.
4. Download the ZIP, extract the WAV files.
5. Upload `raw_mode_00.wav` to Suno (or any other platform) – it should pass the filter while still sounding like your song.

## Why this helps with Suno

Suno’s content filter relies on spectral‑temporal fingerprints. A single raw mode removes most of the high‑order correlations, making the audio **numerically distinct** from the original, yet **perceptually similar**. It’s like a “musical Xerox” that evades pattern matching.

## Running locally

```bash
pip install -r requirements.txt
python app.py
```

Requirements
See requirements.txt – gradio, numpy, scipy, soundfile, scikit-learn.

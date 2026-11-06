# WAVE LAB — V1

A static, browser-based research oscilloscope and audio analysis environment.

## Included in V1
- Audio waveform display driven by Web Audio API samples
- Internal function generator: sine, square, sawtooth, triangle
- Microphone input (browser permission required)
- Local audio-file decoding and playback
- Timebase, vertical scale/position, and rising-edge trigger controls
- Live magnitude spectrum using the browser analyser FFT
- Peak, peak-to-peak, RMS, dBFS, crest factor, and zero-crossing estimates
- CSV measurement export
- Local research notebook, measurement snapshots, JSON export
- Responsive vintage/modern laboratory instrument design

## Run locally
Use a local web server (required for microphone permission):
```bash
python3 -m http.server 8000
```
Open http://localhost:8000.

## Deploy to GitHub Pages
1. Create a GitHub repository (suggested name: `wave`).
2. Upload the contents of this folder to the repository root and push to `main`.
3. In repository Settings → Pages, select **GitHub Actions** as the build/deployment source.
4. The included workflow deploys the static site on pushes to `main`.

### Optional custom domain
To use `wave.sarimoko.com`:
1. Create a file named `CNAME` in the repository root containing `wave.sarimoko.com`.
2. Add a DNS CNAME record: host `wave`, target `<your-github-username>.github.io`.
3. Set the custom domain in Settings → Pages and enable HTTPS when available.

Replace the placeholder GitHub username with your actual Pages hostname.

## Scientific limitations
This is a digital audio instrument, not a calibrated electrical oscilloscope or SPL meter.
- Amplitude is normalized digital full scale (FS), not volts.
- dBFS is not dBu, dBV, or calibrated acoustic SPL.
- Microphone sensitivity, system gain, operating-system audio processing, and hardware calibration are unknown.
- The spectrum display uses browser `AnalyserNode` frequency data; it is intended for inspection, not metrology-grade FFT work.
- Zero-crossing frequency is a rough estimate, best suited to clean single tones.
- The application does not upload audio; processing happens in the browser.

## Roadmap
Dual-channel acquisition, XY/Lissajous mode, phase analysis, spectrogram with adjustable windows/overlap, dedicated AudioWorklet DSP, calibrated FFT/window functions, THD/THD+N, SNR, WAV export, experiment session files, and report generation.

## License
Add a license before public distribution.

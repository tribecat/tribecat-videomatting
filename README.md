# tribecat.matting — public demo

Max/MSP (Cycling'74) external for **real-time video matting**
(background removal without a green screen), based on an ONNX Robust
Video Matting model.

<!-- TODO: screenshot(s) or demo GIF here -->

## About

`tribecat.matting` does real-time video matting directly inside
Max/MSP, no green screen required — useful for VJing, interactive
installations, streaming, or any patch that needs to isolate a person
from the background live.

This demo lets you evaluate the external under real conditions.
<!-- TODO: link to a product/commercial page, offer, or sales contact, if applicable -->

## Download

Latest version: see [Releases](../../releases/latest)

| Platform | File |
|---|---|
| Windows (Max 9) | `tribecat-videomatting-win-<version>.zip` |
| macOS (Max 8 and 9, Apple Silicon + Intel) | `tribecat-videomatting-mac-<version>.zip` |

## Installation

1. Download the zip matching your platform above.
2. Unzip it: you'll get a `tribecat-videomatting/` folder.
3. Place that folder in your Max Packages directory:
   - Windows: `Documents\Max 9\Packages\`
   - macOS: `~/Documents/Max 9/Packages/` (or `Max 8/Packages/`)
4. (macOS only) If Max refuses to load the external or the ONNX Runtime
   library ("cannot be loaded due to system security policy" / "does
   not contain malware"): right-click the file in Finder → Open,
   confirm the popup, then try again.
5. Restart Max. The `tribecat.matting` object is now available in your
   patches.

## Usage

See the built-in help in Max (right-click the object → Open Help), or
open `help/tribecat.matting.maxhelp` directly from the package.

Attributes:
- `@downsample_ratio <float>` — reduces the internal resolution used by
  the model before processing (between 0 and 1). A lower value speeds
  up processing but can reduce mask quality; tune it to your scene and
  machine.
- `@gpu <0|1>` — attempts to enable GPU acceleration. **Currently
  macOS-only (CoreML)**: on Windows, GPU acceleration isn't implemented
  yet, and the external silently falls back to CPU even with `@gpu 1`.
- `@dtype <16|32>` — model precision (16 or 32 bit).

## Demo limitations

This version is limited for evaluation purposes:
- a watermark is overlaid on every processed frame
- <!-- TODO: other limitations once implemented (time limit, pauses) -->

## Benchmarks

<!-- TODO: performance numbers (FPS) once available -->

## Support / contact

<!-- TODO: email, website, or Tribecat contact link -->

## License

See [LICENSE](./LICENSE) — evaluation version; commercial use and
redistribution are not permitted without explicit agreement.
<!-- TODO: needs review/drafting by whoever is responsible for this; this is a draft -->

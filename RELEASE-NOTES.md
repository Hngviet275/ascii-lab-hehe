# Release notes

## Unreleased

### Added

- **Pixel** effect: nearest-neighbour colour sampling per cell, six-level per-channel quantisation and a 1 px gutter for retro pixel art. It honours palette, tint, invert, coverage and every export — SVG stays vector via `<rect>` elements and TXT approximates cells with `█`. The tone slider is labelled **Pixel size**.
- **Color mode** for Pixel in the Color tab: Original, Mono, Grey 4, Grey 8, Game Boy DMG, CGA Mode 1 and Cyberpunk Neon. Between two neighbouring palette colours, cells use an ordered Bayer dither so palette gradients transition smoothly; the mode also applies to SVG exports.

### Changed

- The built-in demo is now a knight-and-squire artwork, embedded as a 1400×1400 WebP so the demo keeps full detail without inflating the single file.
- The blurred background dims the image at 25% instead of 45%, so Blurred backs keep more of the source's brightness.
- Pixel cells use ordered dithering between the two closest palette colours, smoothing colour ramps in Mono, Grey 4/8, Game Boy, CGA and Cyberpunk modes. Original keeps clean six-level per-channel quantisation.

## v02 — 9 November 2026

ASCII lab . hehe v02 rebuilds the control panel and fixes background handling in Dither.

### Added

- Two-tab control panel: **Render** (look, effect, background, tone, advanced) and **Color** (look filters, palette, dither colours, tint and colour grade).
- Look presets as a chip group with the active look name shown above it.
- **Normal** blend mode for tint, alongside Multiply, Screen, Overlay, Soft light and Color.
- A dither colours selector in the Color tab: Original (dynamic), Mono, Grey 4, Grey 8, Game Boy, CGA and Cyberpunk.

### Changed

- Renamed the app to **ASCII lab . hehe v02**.
- Palette tint and colour-grade tint now share one tint colour control.
- Dither algorithms trimmed to Bayer 8×8, Floyd–Steinberg, Atkinson and White Noise; the separate Chroma control was removed.
- Palette, dither colours, tint and colour grade are consolidated in the Color tab to remove duplicated controls.

### Fixed

- Background modes now work in Dither. Solid colour, transparent and blurred image backdrops show through cells that are off instead of being covered by opaque black or palette cells.
- Dither with an explicit palette treats the palette entry closest to the background colour as paper, so highlights reveal the background — Newsprint prints black ink on its beige paper, and Game Boy keeps its dark green screen.
- Error diffusion (Floyd–Steinberg, Atkinson) still propagates quantisation error for unpainted cells, so the dither pattern itself is unchanged.

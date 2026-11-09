# Release notes

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

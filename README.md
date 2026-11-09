# ASCII lab . hehe v02

Turn any image into ASCII art — in one HTML file, entirely in your browser.

**Live demo:** https://hngviet275.github.io/ascii-lab-hehe/

![ASCII lab . hehe v02](docs/screenshot.png)

## Why this exists

Most ASCII converters ship a build step, a CDN dependency or an upload. This one is a single `index.html` with inline CSS and JavaScript. Download it, double-click it, share it. Nothing is sent anywhere.

## Features

- **Six effects** — Characters, Braille (2×4 Unicode dot matrix), Block, Pixel, Dither and Halftone.
- **Pixel effect** — nearest-neighbour sampling with a six-level colour quantisation and a 1 px gutter for a crisp retro pixel-art look. A **Color mode** in the Color tab maps the cells to Original, Mono, Grey 4/8, Game Boy, CGA or Cyberpunk palettes, using ordered dithering between the two closest colours so palette ramps stay smooth.
- **Eight looks** — Terminal, Poster, Newsprint, Neon, Blueprint, Braille, Halftone and Game Boy, each a one-click starting point.
- **Dither engine** — Bayer 8×8, Floyd–Steinberg, Atkinson and White Noise, with Mono, Grey 4, Grey 8, Game Boy, CGA and Cyberpunk palettes and a strength control; dither colours live in the Color tab.
- **Glyph controls** — five ramps plus a free-text custom charset, invert ramp, and deterministic randomize with a reproducible seed.
- **Tone controls** — size, effect opacity, contrast, brightness, coverage, gamma, invert.
- **Dot grid** — optional technical dot matrix over any effect.
- **Palettes** — source colours, monochrome, or a duotone tint.
- **Colour grade** — eight filters (B&W, Sepia, Warm, Cool, Vintage, Fade, Cyber) plus tint colour, tint opacity, blend mode, saturation, vibrance, hue, gradient map, grayscale and invert. The grade is applied to the source, so previews and every export stay in sync. The tint colour is shared with the duotone palette, so there is one tint control for both.
- **Canvas colours** — custom background and transparent output for PNG and SVG.
- **Background modes** — solid colour, transparent, or a blurred copy of the source image behind the glyphs with a light 25% dim and an adjustable Gaussian blur.
- **Bundled font** — characters use IBM Plex Mono, embedded in the HTML so glyphs and SVG exports match offline.
- **Exports** — PNG (1× / 2× at source resolution), JPG, SVG, plus plain-text ASCII (.txt) and copy-to-clipboard.
- **Comfortable viewing** — drag & drop, wheel zoom, pinch zoom, pan, double-click to reset.
- **Two-tab controls** — Render for look, effect, background and tone; Color for palette, dither colours, tint and the colour grade.
- **Responsive** — a docked sidebar on desktop, a collapsible bottom sheet on mobile.
- **No external requests** — styles, scripts, fonts and the demo image are bundled in the single file.

## Use it

Open the live demo, or run the file locally:

```bash
git clone https://github.com/Hngviet275/ascii-lab-hehe.git
cd ascii-lab-hehe
python3 -m http.server 8766
# then open http://localhost:8766/
```

You can also open `index.html` directly from disk. If a browser refuses to read pixels back from local images, serve the folder over HTTP instead.

## Export sizes

PNG 1× renders at the source image's pixel size and 2× doubles it. Exports are clamped to 8192 px per side and 16 megapixels, and the aspect ratio is always preserved. SVG keeps glyphs and blocks as real vector elements and only embeds a blurred JPEG layer when the backdrop mode is Blurred image; SVG is sized to the on-screen preview. With a transparent background, PNG and SVG keep the alpha channel; JPG falls back to the chosen background colour.

## Keyboard

| Key | Action |
| --- | --- |
| `O` | Open an image |
| `+` / `-` | Zoom in / out |
| `0` or `F` | Fit / reset view |
| `Esc` | Close menus |

## Limits

- Static images only (no video).
- Canvas resolution is capped at 2× device pixel ratio for smooth interaction.
- Randomize applies to the Characters effect only.
- TXT export is exact for Characters and Braille; Dither, Halftone, Block and Pixel are approximated with `█`.
- Colour grading works on a copy of the source capped at 1600 px on the long side, so very large images export at up to 1600 px while a grade is active. Clear the grade to export at full source resolution.
- Braille uses a system braille font (Apple Braille, Segoe UI Symbol or DejaVu Sans Mono) — the embedded IBM Plex Mono has no braille glyphs.

## Release notes

See [RELEASE-NOTES.md](RELEASE-NOTES.md) for what changed in each version.

## License

MIT — see [LICENSE](LICENSE). The bundled IBM Plex Mono font is licensed under the SIL Open Font License 1.1 — see [docs/IBM-Plex-Mono-OFL.txt](docs/IBM-Plex-Mono-OFL.txt).

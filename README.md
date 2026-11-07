# ASCII lab . hehe v01

Turn any image into ASCII art — in one HTML file, entirely in your browser.

**Live demo:** https://hngviet275.github.io/ascii-mini/

![ASCII lab . hehe v01](docs/screenshot.png)

## Why this exists

Most ASCII converters ship a build step, a CDN dependency or an upload. This one is a single `index.html` with inline CSS and JavaScript. Download it, double-click it, share it. Nothing is sent anywhere.

## Features

- **Three effects** — Characters, Block and Dither.
- **Five looks** — Terminal, Poster, Newsprint, Neon and Blueprint, each a one-click starting point.
- **Five ramps** — Standard, Classic ASCII, Dense, Blocks, Binary.
- **Deterministic randomize** — jitter glyph choice with a seed you can reproduce.
- **Tone controls** — size, contrast, brightness, coverage, gamma, invert.
- **Palettes** — source colours, monochrome, or a duotone tint.
- **Canvas colours** — custom background and transparent output for PNG and SVG.
- **Image backdrop** — a blurred, dimmed copy of the source image sits behind the glyphs.
- **Exports** — PNG (1× / 2×), JPG, SVG, plus plain-text ASCII (.txt) and copy-to-clipboard.
- **Comfortable viewing** — drag & drop, wheel zoom, pinch zoom, pan, double-click to reset.
- **Responsive** — a floating side panel on desktop, a bottom sheet on mobile.
- **No external requests** — styles, scripts, fonts and the demo image are bundled in the single file.

## Use it

Open the live demo, or run the file locally:

```bash
git clone https://github.com/Hngviet275/ascii-mini.git
cd ascii-mini
python3 -m http.server 8766
# then open http://localhost:8766/
```

You can also open `index.html` directly from disk. If a browser refuses to read pixels back from local images, serve the folder over HTTP instead.

## Export sizes

PNG 1× matches the on-screen canvas, 2× doubles it. Exports are clamped to 8192 px per side and 16 megapixels. SVG keeps glyphs and blocks as real vector elements and only embeds a blurred JPEG layer when the image backdrop is on. With a transparent background, PNG and SVG keep the alpha channel; JPG falls back to the chosen background colour.

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

## License

MIT — see [LICENSE](LICENSE).

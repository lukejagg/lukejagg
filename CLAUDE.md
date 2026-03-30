# lukejagg

GitHub profile README repo (`lukejagg/lukejagg`). The README.md renders on Luke's GitHub profile page.

## Structure

- `README.md` — profile content (name, tagline, social links, project cards)
- `assets/` — SVGs and images referenced by the README

## Preview

Use `grip` to preview the README with GitHub's actual markdown rendering:

```bash
uv tool run grip README.md 6419 &
open http://localhost:6419
```

Auto-refreshes on file changes — edit in any editor and refresh the browser.

## Style

- Link/title color: `#438CEE` (same blue used for icon fills)
- Icon background: `#0A1628` (dark navy)
- Icon glow: white `flood-opacity="0.5"`, dilated 2-3px via `feMorphology`, blurred with `stdDeviation="2"`
- Project cards use `align="left"` images with zero-width spaces for text alignment
- **Icon ratio (128/160 = 80%)**: Icon SVGs use a 160x160 viewBox with a dark rounded-rect background (`#0A1628`, rx=28) at 128x128 centered at (16,16). The logo/image content sits inside that rect with additional padding. This matches the Speck app icon's natural inset. For PNG logos, create an SVG wrapper that embeds the PNG via `<image>` inside the same dark rect container, using `feFlood`+`feComposite` to tint the white PNG to `#438CEE`.

# 🎨 Canvas Studio — Color Palette Generator

Part of **BlackRoad Studio** — production creative tools.

Generate harmonious, WCAG-accessible color palettes and export to CSS, Tailwind, and JSON.

## Features

- **6 harmony types** — complementary, triadic, analogous, monochromatic, split-complementary, tetradic
- **WCAG 2.1 contrast checking** — AA / AAA grades for every foreground/background pair
- **CSS custom properties** — with RGB channels for opacity support
- **Tailwind CSS config** — drop-in `tailwind.config.js` export
- **Tint/shade scale** — 9-stop lightness scale at fixed hue
- **Semantic tokens** — auto-generated success / warning / error / info colors
- **SQLite persistence** — save, list, load, delete palettes
- **Zero dependencies** — stdlib only (`colorsys`, `sqlite3`, `json`)

## Quick start

```bash
# Generate and display
python src/palette_generator.py generate '#3b82f6' complementary --name 'Ocean'

# Save to DB
python src/palette_generator.py generate '#e11d48' triadic --name 'Ruby' --save

# Export CSS
python src/palette_generator.py css <id>

# Export Tailwind
python src/palette_generator.py tailwind <id>

# WCAG audit
python src/palette_generator.py a11y <id>

# Quick contrast check
python src/palette_generator.py contrast '#1e293b' '#f8fafc'
```

## Harmony types

| Type | Hue rotations | Use case |
|---|---|---|
| `complementary` | 0°, 180° | High contrast, bold |
| `triadic` | 0°, 120°, 240° | Vibrant, balanced |
| `analogous` | 0°, 30°, 60° | Harmonious, natural |
| `monochromatic` | same hue | Elegant, minimal |
| `split-complementary` | 0°, 150°, 210° | Softer contrast |
| `tetradic` | 0°, 90°, 180°, 270° | Rich, complex |

## WCAG grades

| Ratio | Grade | Use case |
|---|---|---|
| ≥ 7.0 | AAA | Body text |
| ≥ 4.5 | AA | Normal text |
| ≥ 3.0 | AA-Large | Large text / UI |
| < 3.0 | Fail | Avoid |

## Running tests

```bash
pip install pytest pytest-cov
pytest tests/ -v --cov=src
```

---

**Proprietary Software — BlackRoad OS, Inc.**

This software is proprietary to BlackRoad OS, Inc. Source code is publicly visible for transparency and collaboration. Commercial use, forking, and redistribution are prohibited without written authorization.

**BlackRoad OS — Pave Tomorrow.**

*Copyright 2024-2026 BlackRoad OS, Inc. All Rights Reserved.*

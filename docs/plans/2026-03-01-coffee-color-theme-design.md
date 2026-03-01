# KafuCafe Coffee Color Theme Design

**Date:** 2026-03-01  
**Status:** Approved

## Overview

Transform the Horizon-based KafuCafe theme into a professional coffee store theme with a minimalistic, clean, modern light color palette featuring white as the primary background and coffee brown accents.

---

## Color Palette

### Primary Colors

| Color | Hex | Usage |
|-------|-----|-------|
| Background (main) | `#FFFFFF` | Primary page background |
| Secondary Background | `#FAF7F2` | Warm cream - alternating sections |
| Tertiary Background | `#F5EDE4` | Light latte - cards, feature sections |

### Accent Colors

| Color | Hex | Usage |
|-------|-----|-------|
| Primary Accent | `#6F4E37` | Coffee brown - buttons, links, highlights |
| Primary Accent Hover | `#5D3E2C` | Darker brown - button hovers, active states |
| Secondary Accent | `#C4A484` | Light caramel - subtle highlights, badges |

### Text Colors

| Color | Hex | Usage |
|-------|-----|-------|
| Headings | `#2D2A26` | Soft black for headings |
| Body Text | `#4A4540` | Warm dark gray for paragraphs |
| Muted Text | `#8A847C` | Secondary text, captions |

### Border Colors

| Color | Hex | Usage |
|-------|-----|-------|
| Light Border | `#E8E2DA` | Default borders, dividers |
| Medium Border | `#D4CCC2` | Emphasized borders |

### Button Colors

| State | Background | Text | Border |
|-------|------------|------|--------|
| Primary Default | `#6F4E37` | `#FFFFFF` | `#6F4E37` |
| Primary Hover | `#5D3E2C` | `#FFFFFF` | `#5D3E2C` |
| Secondary Default | `transparent` | `#6F4E37` | `#6F4E37` |
| Secondary Hover | `#FAF7F2` | `#5D3E2C` | `#5D3E2C` |

---

## Scheme Assignments

Shopify color schemes mapped to use cases:

| Scheme | Background | Recommended Use |
|--------|-----------|-----------------|
| scheme-1 | `#FFFFFF` | Main content areas |
| scheme-2 | `#FAF7F2` | Alternating sections |
| scheme-3 | `#F5EDE4` | Feature cards, product cards |
| scheme-4 | `#FFFFFF` | Headers, hero sections with brown accents |
| scheme-5 | `#2D2A26` | Footer (dark contrast for sophistication) |
| scheme-6 | `#6F4E37` | Sale badges, highlight badges |

---

## Design Principles

1. **White Primary** — Main background always white (`#FFFFFF`) for clean, professional look
2. **Warm Cream Secondary** — Use `#FAF7F2` sparingly for section variation
3. **Coffee Brown Accent** — `#6F4E37` as the primary action color (buttons, links)
4. **Soft Contrast** — Text uses warm grays, never harsh black (`#000000`)
5. **Minimal Borders** — Light warm borders (`#E8E2DA`) for subtle separation

---

## Implementation Notes

- Update `config/settings_data.json` color schemes
- Consider adding custom CSS variables in `snippets/theme-styles-variables.liquid` for any custom colors
- Test contrast ratios for accessibility compliance
- Ensure product images pop against the cream/latte backgrounds

---
layout: default
title: Design tokens
parent: Site styles
nav_order: 1
---

# Design tokens

The platform automatically generates a set of CSS custom properties from the four [palette colours]({% link docs/site_styles/index.md %}#colours) defined in Site styles. These variables are injected as `:root` properties at runtime alongside the base palette. They provide accessible, consistent colour tokens for theme development and are computed with WCAG AA compliance in mind (4.5:1 contrast for normal text, 3:1 for large text and UI elements such as borders).

## Colour scales

Four 11-step colour scales (50–950) are generated using the OKLCH colour space for perceptually uniform steps. Each scale is derived from a single source colour.

| Scale | Source | Example variable |
|-------|--------|------------------|
| Brand | Primary colour | `--brand-50` through `--brand-950` |
| Accent | Secondary colour | `--accent-50` through `--accent-950` |
| Neutral | Site background colour | `--neutral-50` through `--neutral-950` |
| Error | Fixed (#dc2626) | `--error-50` through `--error-950` |

Steps run from lightest (50) to darkest (950).

## Semantic tokens — Text

| Variable | Description |
|----------|-------------|
| `--text-default` | Default body text colour (creator's site text colour) |
| `--text-muted` | Subdued text; meets 4.5:1 contrast, never more prominent than default |
| `--text-inverse` | Text for use on inverse (dark/light-flipped) backgrounds; 4.5:1 |
| `--text-on-brand` | Text on primary-coloured surfaces; white or brand-950, whichever has higher contrast |
| `--text-on-accent` | Text on secondary-coloured surfaces; white or accent-950 |
| `--text-on-neutral` | Text on body background; white or neutral-950 |

## Semantic tokens — Backgrounds

| Variable | Description |
|----------|-------------|
| `--background-default` | Page background (creator's site background colour) |
| `--background-muted` | Subtle tinted background for secondary surfaces |
| `--background-inverse` | Inverse background (same as default text colour) |

## Semantic tokens — Borders

| Variable | Description |
|----------|-------------|
| `--border-default` | Standard border; meets 3:1 contrast |
| `--border-muted` | Subtle/decorative border |
| `--border-brand-accessible` | Accessible border from brand scale; 3:1 |
| `--border-neutral-accessible` | Accessible border from neutral scale; 3:1 |
| `--border-accent-accessible` | Accessible border from accent scale; 3:1 |

## Semantic tokens — Surfaces and errors

| Variable | Description |
|----------|-------------|
| `--surface-primary` | Card/modal backgrounds |
| `--surface-elevated` | Elevated surface (e.g. dropdowns, popovers) |
| `--error-text` | Error message text; 4.5:1 contrast |
| `--error-background` | Error background/highlight |

## Usage example

Reference these tokens in your theme CSS instead of hard-coded colours so that colours stay consistent and accessible when Creators change their palette.

```css
.card {
  background: var(--surface-primary);
  color: var(--text-default);
  border: 1px solid var(--border-default);
}

.badge {
  background: var(--primary);
  color: var(--text-on-brand);
}
```

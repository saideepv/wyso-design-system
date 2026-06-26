# Tokens

Two-layer token architecture. Components and patterns should only ever
consume **semantic** tokens — primitives exist so the palette/scale can
change in one place without a find-and-replace across the system.

| File | Layer | Notes |
| --- | --- | --- |
| `color.primitives.css` | primitive | Raw "Lemon Mint" palette. LOCKED. No purple, no grey, no pure white/black. |
| `color.semantic.css` | semantic | Usage-named aliases (`--color-primary`, `--text-ink`, `--state-correct-*`...) over the primitives. |
| `typography.css` | primitive + usage scale | Baloo 2 (display) + Atkinson Hyperlegible (body). LOCKED pairing. |
| `spacing.css` | primitive | 4px base spacing/sizing scale. |
| `effects.css` | primitive + usage | Radii, organic "blob" shapes, signature gradients, shadows, motion easing. |
| `index.css` | — | Imports every layer above in the correct order. |

## Status

This is the **first pass**, extracted from the v0.2 foundations prototype.
Treat values marked LOCKED as settled; everything else (especially any
future semantic typography/spacing aliases, dark-mode variants, etc.) is
expected to evolve — track changes in `docs/decisions/`.

## Usage

```html
<link rel="stylesheet" href="tokens/index.css">
```

```css
.button-primary {
  background: var(--grad-grow);
  color: var(--color-on-primary);
  border-radius: var(--radius-pill);
  box-shadow: var(--shadow-btn-primary);
}
```

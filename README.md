# Wyso Design System

Design system for **Wyso** — voice-first AI learning companions for Indian
middle-school students. The first companion is **Aura**.

> Status: early foundations. Colour palette and typography pairing are
> locked; components and patterns are being built out from an initial
> prototype. See `docs/decisions/` for what's settled vs. still moving.

## Structure

```
wyso-design-system/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── docs/
│   ├── principles/     — the "why": brand voice, design principles
│   ├── foundations/     — the "what": narrative around colour, type, spacing, motion
│   ├── components/      — component inventory & usage guidance
│   ├── patterns/        — recurring flows built from components (onboarding, mission loop, ...)
│   └── decisions/       — lightweight ADR log of things we've locked in
│
├── tokens/              — the source of truth: CSS custom properties (primitives + semantic)
├── assets/              — exported images, icons, audio cues
└── figma/               — links/exports to and from Figma
```

## Quick start

Pull in the whole token layer:

```html
<link rel="stylesheet" href="tokens/index.css">
```

Then build against semantic tokens only — never hardcode a hex value or a
px size in product code. See `tokens/README.md` for the primitive →
semantic layering.

## Brand basics (locked)

- **Colour:** "Lemon Mint" palette — deep green primary, golden secondary,
  mint accent (kept to ≤10% of any screen), warm cream neutrals. No
  purple, no grey, no pure white/black. See `tokens/color.primitives.css`
  and `tokens/color.semantic.css`.
- **Type:** Baloo 2 (display) + Atkinson Hyperlegible (body) — Baloo 2
  ships native Devanagari, Atkinson Hyperlegible is built for letterform
  clarity. See `tokens/typography.css`.
- **Shape & motion:** organic "blob" shapes, generous gradients, soft
  colour-washed shadows, gentle tilt used sparingly for celebration
  moments only. See `tokens/effects.css`.

## Contributing

Open a PR. If a change touches a token in `tokens/`, add a short note to
`docs/decisions/` explaining what changed and why.

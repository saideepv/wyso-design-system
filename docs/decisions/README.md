# Decisions

Lightweight log of things we've locked in, in date order. Add a new
section per decision — keep each one short: what changed, why, what it
rules out.

---

## 0001 — Lock the "Lemon Mint" colour palette

Deep green primary, golden secondary, mint accent capped at ≤10% of any
screen, warm cream neutrals. No purple/violet, no pure grey, no pure
white/black.

**Rules out:** any future component using grey for disabled/muted states
(use the olive neutrals instead), red/amber for error states (retry is
gold, not red — see `--state-retry-*` tokens).

> **Amended by 0003:** the "no pure grey" clause is superseded — a grey
> primitive ramp now exists for a specific, scoped purpose. Olive/cream
> remain the default for primary UI text, surfaces, and borders.

## 0002 — Lock the Baloo 2 + Atkinson Hyperlegible type pairing

Baloo 2 for display (headings, buttons, the "Aura" wordmark) — ships
native Devanagari. Atkinson Hyperlegible for body/UI — built for
letterform clarity (Il1, b/d, O0), important for a middle-school reading
level.

**Rules out:** introducing a third typeface without updating this log.

## 0003 — Add a true achromatic grey primitive ramp

13 steps (`--grey-025` → `--grey-950`), R=G=B at every step, inset
slightly from pure white/black (so the "no pure white/black" half of 0001
still holds). Added for general neutral UI (disabled states, dividers),
future dark-mode surfaces, and data viz/chart baselines — not a
replacement for the warm olive/cream neutrals, which stay the default for
primary UI text, surfaces, and borders.

**Rules out:** using `--grey-*` for primary body text, canvas/card
surfaces, or borders in the current light theme — keep reaching for
`--text-body` / `--surface-card` / `--border-soft` there. No semantic
aliases over the grey ramp yet (no dark theme or chart components exist
to consume them) — add those when that work actually starts.

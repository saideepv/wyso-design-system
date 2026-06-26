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

## 0002 — Lock the Baloo 2 + Atkinson Hyperlegible type pairing

Baloo 2 for display (headings, buttons, the "Aura" wordmark) — ships
native Devanagari. Atkinson Hyperlegible for body/UI — built for
letterform clarity (Il1, b/d, O0), important for a middle-school reading
level.

**Rules out:** introducing a third typeface without updating this log.

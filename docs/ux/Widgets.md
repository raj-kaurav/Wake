# Widgets

**Phase:** 2 — UX Documentation
**Status:** Draft for review
**Purpose:** UX specification of Wake's primary surface (D1): the visual
concept space, the recommended primary concept, states, interactions,
accessibility, and platform tiering. Final visual execution is Phase 5
(`../design-system/WidgetVisualLanguage.md`); the H13 spike constrains
fidelity on iOS.

---

## 1. The Widget's Job

Render **today as a finite, moving shape** — glanceable in under one
second, emotionally calm, and always carrying one Start affordance (P2,
D2, D3). It must communicate *without being read*: shape first, digits as
caption (D4).

## 2. Concept Exploration (three candidates carried into Phase 2 testing)

### W-A "Day Dots" — recommended primary

A grid of dots representing the wake window (one dot = 15 min; a 16-hour
window = 64 dots). Passed dots fade/fill; the current dot breathes gently
(reduced-motion-safe alternative: higher contrast, no animation); future
dots remain open.

- **Why recommended:** (1) *Natively coarse* — a 15-min step matches iOS
  refresh budgets by design, so both platforms show the same honest
  granularity (R5 solved by design rather than fought); (2) discrete dots
  read as "moments available" (opportunity framing structurally built in —
  countable remaining dots, H2-friendly); (3) colorblind-safe (fill state,
  not hue, carries meaning); (4) scales across widget sizes by grid
  reflow; (5) calm — no sweeping motion, no alarm geometry.
- **Risks:** abstraction requires one-time learning (onboarding preview
  teaches it in one glance); dot grids can read as "habit tracker grid"
  (visual design must avoid calendar-like row labeling — dots are *today
  only*, never a history grid, D6).

### W-B "Day Arc" — secondary candidate

A single arc/ring that depletes (or fills) across the wake window.
Beautiful and instantly legible; but continuous geometry *implies*
continuous motion, which iOS refresh budgets can't honor (a visibly
stepping arc reads as broken — R5), and ring-shaped progress is the most
copied visual in wellness apps (category-confusion risk R3). Kept for
lock-screen/watch surfaces (Horizon 2) where rings are native grammar.

### W-C "Remaining field" — minimal text-forward variant

Large granular text ("6h 40m left of today") over a subtle shrinking
field. Strong for accessibility and for users who prefer words; weak on
feel-without-reading (D4). Ships as an alternate widget style if Phase 5
budget allows; otherwise its text is already the primary widget's caption.

**Decision requested with this phase:** W-A primary, W-B deferred to
lock/watch surfaces, W-C as stretch alternate.

## 3. Anatomy (W-A, medium size — reference layout)

1. **Dot field** — the day, at-a-glance (majority of area).
2. **Caption** — granular time text, framing per config ("6h 40m of today
   left").
3. **Content line** — one Content Engine line for the current slot
   (S1/S2/S3; T2/T3/T4 types), ≤40 chars.
4. **Start affordance** — a clearly tappable button region ("Start · 2
   min"). Never smaller than platform-minimum tap target.

Small size drops the content line; large size may add the current
intention (if set). Nothing else is ever added — no stats, no streak
row, no yesterday (D6; IA §5 illegal inputs).

## 4. State Behavior

| State | Rendering |
|---|---|
| Within wake window | Normal: dots advance; caption + slot-appropriate content line |
| Timer running | Widget mirrors the session: remaining-time face + no Start affordance (one session at a time); returns to normal at close |
| Outside wake window | Rest face: dots complete, dimmed; caption "Day complete." (voice-neutral, endorsing rest — A6); no Start affordance push, but tapping still opens Now (night starts remain possible, uninvited) |
| Gap return (S6 flag) | Identical layout; content line is a T7/T4 fresh-start line — the *only* difference (F6 rules) |
| Stale data / OS killed updates | Honest edge face: dims + "tap to refresh" microcopy (S8) — never silently wrong time (D9) |

## 5. Interactions

| Region | Action | Contract |
|---|---|---|
| Start affordance | Timer, starting immediately | <1 s; no interstitial (Navigation §7) |
| Anywhere else | Opens Now | Never settings, never a pitch |

No configuration on the widget itself in MVP (long-press platform menus
excepted, OS-provided). Widget settings (style, framing) live in Settings
when/if variants ship.

## 6. Accessibility (P10 — the widget must not be sight-only)

- Full text alternative: "Today: 9 of 16 hours remaining. 6:40 left.
  [content line]. Start two minutes." — read as one coherent utterance,
  not dot-by-dot.
- Fill-state contrast meets AA in both palettes; meaning never carried by
  hue alone (dot fill = state).
- Honors system font scaling (caption scales; dot field yields space
  before text truncates); honors reduced motion (no breathing dot —
  static contrast marker instead).
- Tap targets ≥ platform minimums at all widget sizes.

## 7. Platform Tiering (accepted reality, designed-for)

| Aspect | Android | iOS |
|---|---|---|
| Update cadence | 15-min dot step via scheduled updates; finer caption updates feasible | 15-min steps within WidgetKit budget; caption uses date-relative text (self-updating) where possible (H13 spike validates) |
| Start affordance | Direct intent to running timer | App-launch deep link (fast path budgeted; Live Activity mirror post-spike) |
| Sizes (MVP) | small, medium (large optional) | small, medium |
| Lock screen / AOD | Horizon 2 | Horizon 2 (W-B grammar) |

The dot concept makes the two platforms *equally honest*: neither promises
minute-level motion, so neither breaks (D9 applied to rendering).

## 8. Anti-Habituation Notes (R1, owned jointly with Phase 5)

The dot field itself must stay stable (it is the learned glance-language);
variation comes from the content line rotation (ContentSystem §4) and
subtle seasonal/landmark accents (S7 mornings may tint the first dot — a
design-system decision later). Any variation must never make the glance
slower (D2 outranks novelty).

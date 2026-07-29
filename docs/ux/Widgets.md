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

## 2. Widget Concept Space — Default V1 vs Long-Term Direction

**Status of decision:** Day Dots is the **Default V1 widget** for launch /
early beta — **not a finalized long-term visual identity.** Additional
concepts below are retained for beta exploration; adoption of any
alternative requires Wave 4 / post-launch A/B evidence, not Phase 2 taste.

### 2.1 Default V1 — W-A "Day Dots"

A grid of dots representing the wake window (one dot = 15 min; a 16-hour
window = 64 dots). Passed dots fade/fill; the current dot breathes gently
(reduced-motion-safe alternative: higher contrast, no animation); future
dots remain open.

- **Why Default V1:** (1) *Natively coarse* — a 15-min step matches iOS
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

### 2.2 Long-term candidates (beta exploration — do not ship as V1 default)

### W-B "Day Arc"

A single arc/ring that depletes (or fills) across the wake window.
Beautiful and instantly legible; but continuous geometry *implies*
continuous motion, which iOS refresh budgets can't honor (a visibly
stepping arc reads as broken — R5), and ring-shaped progress is the most
copied visual in wellness apps (category-confusion risk R3). **Best home:
lock-screen / watch surfaces (Horizon 2)** where rings are native grammar.

### W-C "Remaining field"

Large granular text ("6h 40m left of today") over a subtle shrinking
field. Strong for accessibility and for users who prefer words; weak on
feel-without-reading (D4). Candidate as an **accessibility / alternate
style**, not a replacement identity.

### W-D "Opportunity Tiles"

A small set of large tiles representing remaining day-blocks (e.g., four
tiles for morning / midday / afternoon / evening). Empty tiles = still
available; filled = passed. High emotional "opportunity" read; fewer
elements than dots.

- Emotional impact: strong opportunity framing; can feel chunky/coarse.
- Glanceability: excellent at medium/large; weak at small.
- Android / iOS: coarse steps friendly to both; tile count must stay
  stable across wake-window lengths (variable wake windows complicate
  layout).
- Accessibility: tiles need clear labels; color-alone banned.
- Battery: low (few updates).
- Platform consistency: high if tile count is fixed (e.g., always 4).

### W-E "Timeline Blocks"

Horizontal blocks along a day timeline (Structured-adjacent geometry,
planless). Current position marked; past muted; future open. Risk: visual
kinship with planners (R3 / P7 gravity).

- Emotional impact: orientation-strong; can imply a *schedule* even with
  no events (anti-pattern watch).
- Glanceability: good on wide/medium widgets; poor on small.
- Android / iOS: 15–30 min steps OK; continuous scrubbing not feasible.
- Accessibility: needs text equivalent of position + remaining.
- Battery: low–medium.
- Platform consistency: medium (aspect-ratio sensitive).

### W-F "Living Horizon"

A soft landscape / horizon line that shifts light/position across the
wake window (dawn → noon → dusk metaphor). High brand beauty; high
abstraction.

- Emotional impact: calm, atmospheric; risk of decoration-without-meaning
  (D2).
- Glanceability: mood yes, precise remaining-time no — caption must carry
  digits.
- Android / iOS: must be stepped (keyframe faces), not animated live;
  iOS especially limited.
- Accessibility: cannot be the sole carrier of meaning; text mandatory.
- Battery: medium if illustrated assets are heavy.
- Platform consistency: hard (asset density / wallpaper bleed).

### W-G "Remaining Day Ribbon"

A single horizontal ribbon that shortens (or empties) as the day passes —
Time Timer heritage in linear form.

- Emotional impact: depletion-forward by default (H2 risk); opportunity
  variant = ribbon of *remaining* growing emphasis on the open portion.
- Glanceability: excellent.
- Android / iOS: coarse steps look intentional on a ribbon; continuous
  motion not required.
- Accessibility: strong with labeled percentage/remaining text.
- Battery: low.
- Platform consistency: high.
- Risk: progress-bar cliché; must not read as task progress (R3).

### W-H "Segmented Day"

Wake window divided into equal segments (e.g., 8 segments of ~2h).
Current segment highlighted; past complete; future open. Between dots
(fine) and tiles (coarse).

- Emotional impact: structured calm; segments can feel like "blocks to
  fill" (A5 watch — copy must not imply productivity quotas).
- Glanceability: good.
- Android / iOS: very budget-friendly.
- Accessibility: segment labels + remaining summary.
- Battery: low.
- Platform consistency: high.

### 2.3 Comparison matrix (summary)

| Concept | Emotion | Glance | Android | iOS | A11y | Battery | Consistency | V1 posture |
|---|---|---|---|---|---|---|---|---|
| Day Dots (W-A) | Calm opportunity | High | High | High (coarse-native) | High (fill≠hue) | Low | High | **Default V1** |
| Day Arc (W-B) | Elegant; urgency risk | High | High | Medium (stepping) | Medium | Low | Medium | Horizon 2 lock/watch |
| Remaining field (W-C) | Clear, less "felt" | Medium | High | High | Highest | Low | High | Alt / a11y style |
| Opportunity Tiles (W-D) | Strong opportunity | High (med+) | High | High | Medium | Low | Medium | Beta explore |
| Timeline Blocks (W-E) | Orientation; planner risk | Medium | High | Medium | Medium | Low–Med | Medium | Beta explore |
| Living Horizon (W-F) | Atmospheric | Low precision | Medium | Medium | Low alone | Medium | Low | Research only |
| Remaining Ribbon (W-G) | Depletion/opportunity | High | High | High | High | Low | High | Beta explore |
| Segmented Day (W-H) | Structured calm | High | High | High | High | Low | High | Beta explore |

**Recommendation:** ship **Day Dots as Default V1**; run beta concept
tests (static mocks + short diary) on W-D, W-G, and W-H before any
long-term identity lock. Do not adopt a long-term direction in Phase 2.

---

## 3. Anatomy (W-A Default V1, medium size — reference layout)

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

## 9. Widget Evolution Program (pointer)

Day Dots is **Default V1**, not permanent identity (D-006). Formal
program, candidate pipeline, and pluggable-renderer architecture:
`../architecture/WidgetEvolutionProgram.md`.

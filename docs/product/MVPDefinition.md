# MVP Definition

**Phase:** 1 — Product Documentation
**Status:** Draft for review
**Purpose:** The binding scope contract for the first shipped version.
Anything not listed here as In is Out (see `OutOfScope.md`). Changes to
this document after approval follow the amendment process in
`ProductPrinciples.md`.

---

## 1. The MVP Hypothesis

> If people can **feel today passing** (widget, optional spoken time) and
> **start anything in two minutes** (one honest button), delivered **in a
> voice they chose** and with **zero cost of coming back after a lapse**,
> then a meaningful share will start real work more often and report less
> time-related distress — without task lists, plans, streaks, or accounts.

The MVP exists to test exactly this (hypotheses H1–H8). It is a complete,
honest product — not a demo — but it is intentionally one loop deep.

## 2. In Scope

### F1 — Time Awareness Widget

- Home-screen widget rendering **today as a shape** (final visual grammar
  from Phase 2/5 within platform budgets — H13 spike) plus granular
  remaining-time text ("6h 40m of today left").
- Wake window (waking hours) set once in onboarding with sensible default
  (07:00–23:00); editable later.
- One in-app "now" screen mirroring the widget (the app's home — there is
  no dashboard).
- Framing default: opportunity ("left"); depletion variant exists behind
  remote config for H2.
- Accessibility: full text alternative, contrast-safe in both voices'
  palettes, font-scaling safe.
- **Platform tiering accepted:** iOS updates in coarse steps within
  WidgetKit budgets; Android may render finer. Visual design must make the
  coarser tier feel intentional, not broken.

### F2 — Start Now

- One primary button, present on: in-app home, widget, every awareness
  notification.
- Tap → two-minute timer starts **immediately** (no intervening decisions;
  intention entry is optional and skippable at the moment).
- Timer survives lock/background (notification-based completion; platform
  specifics in Phase 3).
- End-of-timer: honest stop + genuine completion moment (peak–end design);
  silent user-initiated repeat available; **no auto-extension, no upsell to
  continue** (P8).
- Optional **single intention string** ("what will you touch?") — one
  field, prefilled with the last value, never required, never listed,
  replaced not archived (P7). Ships in MVP pending H12 prototype check.
- No session history surface. (Aggregate, non-displayed counters may exist
  for the user's own G-metrics via analytics contract only.)

### F3 — Voice system

- Onboarding choice between two voices with **mandatory preview** (three
  sample lines each; H6/H7 safety design).
- Provisional names **The Coach / The Friend** — pending product-owner
  ratification with this document (`../research/ToneNamingExploration.md`).
- Voice affects: all copy, notification text, completion moments, palette
  accents (Phase 5). Voice switch: one tap from settings, always free,
  never paywalled (P9).
- Default pre-selection: the nurturing voice (safety-first default;
  explicit choice still required — no silent default path).

### F4 — Content Engine (infrastructure)

- Local, structured, versioned content catalog: `voice × slot × variant`,
  five content types (reframes, granular time facts,
  implementation-intention prompts, starting permissions, sparse quotes).
- Slots for MVP: morning, pre-start, completion, post-lapse, evening,
  fresh-start landmark.
- Launch corpus: **400–800 reviewed lines** (English only), every line
  through the ethics checklist (`../research/EthicalConsiderations.md` §5).
  This is a scheduled workstream with editorial owner, not a byproduct.
- Selection rules: no repeat within N days per slot; landmark override on
  Mondays/month-starts/post-gap returns.

### F5 — Speak Time (tiered)

- **Android (full):** user-chosen intervals (15/30/60 min) within wake
  window; on-device TTS ("It's 12:30." — nothing more, both voices share
  the same neutral utterance); quiet hours; honors DND absolutely; one-tap
  "quiet today"; headphone-only option; instant mute. Ships if H15 spike
  passes on target OEMs.
- **iOS (approximation):** scheduled notifications with pre-rendered
  spoken-time audio; same controls where the platform allows. Ships in MVP
  **only if H14 spike passes the "acceptable, not cheap" test**; otherwise
  documented honestly as coming-later, iOS keeps silent pulses.
- Off by default on both platforms; invited during onboarding's "how loud
  should time be?" step (P9).

### F6 — Awareness pulses (notifications)

- User-scheduled cadence (default: off until invited; suggested 3/day at
  wake, midday, evening — final defaults from Phase 2) within wake window.
- Every pulse: one Content Engine line + Start action + one-tap quiet-today.
- Permission requested in-context at scheduling, never at first launch
  (`../research/NotificationPsychology.md` §5). Zero re-engagement or
  marketing notifications, permanently (P5).

### F7 — Lapse re-entry

- Return after any absence: standard home (today + button) + one
  fresh-start line. No gap acknowledgment, no "welcome back" ceremony, no
  recovered-streak mechanics. Absence leaves zero trace in UI (P3).
- Respectful-silence rule: scheduled pulses auto-downgrade after sustained
  non-interaction (spec in Phase 2).

### Onboarding (the container for all of the above)

Budget: **≤5 decisions, ≤60 seconds to first possible start (P6):**
voice (with preview) → wake window (one screen, default offered) →
optional: invite Speak Time / pulses (skippable) → home. Account creation
does not exist. Permission dialogs occur only in-context later.

## 3. Out of Scope for MVP (summary — full list in `OutOfScope.md`)

Task lists · schedules · streaks/gamification · statistics · accounts/sync ·
social · AI · calendar integration · The Stoic pack · lock-screen widgets ·
watch · live wallpaper · localization beyond English · tablet-optimized
layouts · Android/iOS feature parity where platforms genuinely differ.

## 4. MVP Quality Bars (product-level definition of done)

- **Performance:** cold start to pressable Start button < 1 s on mid-tier
  devices; widget renders correctly across the OS-required size classes.
- **Reliability:** scheduled pulses/Speak Time fire within platform
  tolerances on target devices (device matrix in Phase 3); timer completion
  never lost to backgrounding.
- **Accessibility:** full core loop completable with screen reader; WCAG AA
  contrast; font scaling to platform maximums; reduced-motion respected
  (P10).
- **Battery:** no OS battery-abuser flagging on target devices at default
  settings; Speak Time battery cost documented in its settings copy (P8).
- **Privacy:** zero network calls required for the core loop; analytics
  per the P11 contract, disclosed in plain language.
- **Content:** 100% of shipped lines ethics-reviewed; both voices complete
  for every MVP slot.
- **Ethics:** dark-pattern review against the prohibited list passes; a
  distressed-user walkthrough (Maya-at-23:00 scenario) passes.

## 5. What the MVP Must Prove (exit criteria toward v1.x investment)

1. Activation: a majority of new users reach a first start in session one.
2. The loop repeats: resilient adoption (starts on ≥3 of first 14 days) at
   a rate that justifies Horizon 2 investment.
3. Emotional register: H8 pulse ≥70% calming/clarifying.
4. The widget earns its identity billing: measurable widget→start behavior
   (H1) — or an honest thesis adjustment.

## 6. Open Items Riding With This Document

- Voice name ratification (The Coach / The Friend vs. fallback labels).
- H12 outcome → intention field in or out.
- H13–H15 spike outcomes → widget grammar; Speak Time iOS tier in/out;
  Android foreground-service need.
- Default pulse cadence (Phase 2, from Wave 1/2 research).

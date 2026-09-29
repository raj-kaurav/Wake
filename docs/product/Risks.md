# Risks

**Phase:** 1 — Product Documentation
**Status:** Draft for review
**Purpose:** Product-level risk register, expanded from
`../research/ProductOpportunityReport.md` §5. Each risk: likelihood ×
impact, early-warning signal, mitigation, and owner-of-watch (role, since
team structure is TBD). Engineering-level risks get their own register in
Phase 7 (`RiskRegister.md`); this document stays at product altitude.

Scale: L/M/H for likelihood and impact.

---

## R1 — Habituation: the awareness layer fades into wallpaper

- **L×I: H × H.** The founding bet decays: widget stops being seen, spoken
  time stops being heard (attention habituates by default).
- **Early signals:** widget→start conversion decaying week-over-week in
  cohort curves; Speak Time interval-widening/disabling (H5); pulse
  interaction decay.
- **Mitigations:** variation-within-predictability in content (Content
  Engine rotation, landmark overrides); periodic subtle visual variation
  (Phase 5 anti-habituation lever); treat decay curves as a core design KPI
  from beta onward, not a post-launch surprise.
- **Watch:** Design lead.

## R2 — Novelty churn: loved, praised, abandoned in week three

- **L×I: H × H.** The self-improvement install/abandon cycle is this
  category's gravity.
- **Early signals:** activation without repetition (first start, no third
  day); H8 pulse positive but D14 resilient-adoption low.
- **Mitigations:** week-one experience engineered around felt wins (honest
  completion moments, peak–end); weightless re-entry (the lapse is the
  churn moment — we designed for it); fresh-start landmark re-activation
  via *user-scheduled* pulses only (no re-engagement spam — P5 constrains
  us here and we accept the handicap).
- **Watch:** Product owner.

## R3 — Category confusion: "so it's a timer with quotes?"

- **L×I: M-H × H.** Mispositioning kills differentiation; comparisons to
  todo/Pomodoro apps are lost on feature count.
- **Early signals:** store reviews describing Wake as timer/quotes app;
  press shorthand; H10 copy tests failing.
- **Mitigations:** "time awareness" category language enforced everywhere
  (this was a Phase 0 review decision); sell the moment ("for when you
  can't start"); screenshots lead with widget + voice choice, never the
  timer digits.
- **Watch:** Product owner (positioning is top-three work, per Opportunity
  Report).

## R4 — The challenging voice executed badly

- **L×I: M × H.** One viral screenshot of a bullying line = brand damage +
  real user harm; one bland corpus = the voice's promise broken.
- **Early signals:** ethics-checklist rejection rate in authoring (too high
  = contract misunderstood; zero = review too soft); Coach→Friend switch
  spikes after specific lines (line-level telemetry, aggregate only).
- **Mitigations:** binding content contract + per-line checklist; small
  launch corpus over large unreviewed one; line-level kill-switch via
  content versioning; H6/H7 preview research before launch.
- **Watch:** Content/editorial owner.

## R5 — Platform ceilings degrade the loop (iOS especially)

- **L×I: M × M-H.** Widget refresh budgets, Speak Time background limits,
  OEM alarm-killing (Android) — reliability failures read as broken
  promises (P8) and kill trust fast (Freedom's lesson: reliability is a
  feature).
- **Early signals:** H13–H15 spike results; beta device-matrix failures;
  "widget frozen" support reports.
- **Mitigations:** tiered design accepted upfront (no parity promises);
  spikes scheduled before architecture lock; visual grammar designed *for*
  coarse updates; honest platform-difference copy.
- **Watch:** Engineering lead.

## R6 — Fast followers / incumbent feature-copies

- **L×I: M × M.** Low technical moat, accepted consciously.
- **Early signals:** watchlist items in `CompetitiveAnalysis.md` §5.
- **Mitigations:** speed to polished v1; corpus and voice quality; category
  authorship; constitutional stance incumbents can't adopt.
- **Watch:** Product owner.

## R7 — The mechanism bet partially fails

- **L×I: M × M.** Felt time may not move behavior for enough users (H1);
  the honest possibility is the widget decorates while Start Now does the
  work.
- **Early signals:** H1 A/B flat; widget retention high but conversion
  absent (pleasant ≠ effective).
- **Mitigations:** instrument from day one; the loop still functions on
  Start Now alone; thesis adjustment path pre-written (Opportunity Report
  §6) — marketing retreats to the start moment without pivot theater.
- **Watch:** Product owner + design lead.

## R8 — Scope drift back into the graveyard patterns

- **L×I: M × H.** Every failed productivity app started with one helpful
  addition; user requests will pull toward lists, stats, streaks
  (tripwires already catalogued in `OutOfScope.md`).
- **Early signals:** roadmap PRs citing "users are asking for…" against
  Tier-1 exclusions; metrics debates proposing engagement KPIs.
- **Mitigations:** the constitution + amendment friction; Phase 6 rules
  encode exclusions for AI-assisted development; OutOfScope tripwires in
  the review checklist.
- **Watch:** Everyone; enforcement via review process.

## R9 — Emotional-register failure for vulnerable users (new at product level)

- **L×I: L-M × H.** Despite the contract, some distressed users may
  experience any time-signal as pressure (H8's failure mode), or The Stoic
  pack (later) could reach the wrong user at the wrong moment.
- **Early signals:** H7/H8 segment data; support contacts mentioning
  anxiety; reviews with distress language.
- **Mitigations:** calm defaults (P9); every channel disableable in one
  tap; the Stoic pack's consent-gate + dedicated ethics review before it
  ever ships; distress-safe copy rules (2 a.m. test).
- **Watch:** Content/editorial owner + product owner.

## R10 — Content economics underestimated (new at product level)

- **L×I: M × M.** 400–800 reviewed lines × two voices is real editorial
  work; quality drift under deadline pressure produces exactly R4;
  localization later multiplies it.
- **Early signals:** corpus behind schedule at Phase 7 planning; variant
  counts per slot below anti-habituation minimums (R1 coupling).
- **Mitigations:** treat corpus as a scheduled workstream with an owner
  (MVP definition already does); cut slots before cutting per-slot variant
  depth; defer localization without apology.
- **Watch:** Content/editorial owner.

## R11 — Store/platform policy friction (new at product level)

- **L×I: L-M × M.** Exact-alarm permission justification (Android),
  notification-sound usage review (iOS), and "wellness" store-category
  policies could challenge features or listing language.
- **Early signals:** policy updates in platform release notes; review
  rejections in beta distribution.
- **Mitigations:** accessibility/time-awareness rationale documented for
  the exact-alarm ask (genuine, not pretextual); iOS tier already designed
  within notification rules; no medical claims anywhere (already
  constitutional).
- **Watch:** Engineering lead.

---

## Risk Interactions Worth Naming

- **R1 × R10:** anti-habituation depends on content depth — cutting corpus
  to ship faster silently raises the habituation risk.
- **R2 × P5:** we fight churn with one hand tied (no re-engagement spam);
  this is accepted and priced in — the mitigation budget goes into the
  week-one experience instead.
- **R5 × R3:** a degraded iOS Speak Time that we *oversell* becomes a
  category-confusion and trust problem; honest tiering copy is the joint
  mitigation.

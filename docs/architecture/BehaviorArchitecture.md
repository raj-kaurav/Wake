# Behavior Architecture

**Phase:** Bridge document (created during Phase 2 review resolution;
foundational for Phase 3)
**Status:** Draft for review
**Purpose:** Bridge UX and engineering. Matrix mapping every MVP surface
to the behavior transition it serves, the emotional goal it aims for, the
success signal that validates it, and the ethical / anti-goal guardrails
that constrain it. Phase 3 architecture docs should implement *to* this
matrix — not invent parallel feature rationale.

**Sources of truth:** `../ux/BehaviorChangeModel.md`,
`../ux/EmotionalJourney.md`, `../ux/Rituals.md`,
`../product/SuccessMetrics.md`, `../ux/AntiGoals.md`,
`../product/ProductPrinciples.md`.

**Terminology:** Internal mechanic name = **MicroStart**
(`../ux/Terminology.md`). User-facing copy remains "Start".

---

## 1. MVP Behavior Matrix

| Feature / surface | Behavior transition(s) | Emotional goal | Success signal | Anti-goal / ethical guardrails |
|---|---|---|---|---|
| **Time Awareness Widget** (Day Dots V1 default) | → Notice; supports Identity→Notice over tenure | Calm orientation; day feels finite without dread | Widget retained ≥30d; widget→MicroStart conversion (H1); H8 not "pressuring" | A2 compulsive checking (coarse 15-min); A5 totalization (rest face); P1 no history on widget; P2 Start co-located |
| **MicroStart** (button + 2-min timer + close) | Offer→Start→Momentum→Reflection | Action; then proportionate Confidence | MicroStarts / active user / day; time-to-start ≤10s; completion without upsell | A1 engagement (sparse UI); A4 scorekeeping (no history UI); P8 honest 120s; P5 yield after close |
| **Voice system** (coach/friend ids) | Unblocks Motivation across loop; protects Offer→Start | Chosen care; emotional parity between voices | Voice choice with preview (H6); switch available ≤2 taps; H7 safety | P4 challenge behavior never person; P9 never paywall switch; ethics checklist per line |
| **Content Engine** | Notice, Offer, Reflection, Fresh Start (by type/slot/temperature) | Temperature-appropriate: Calm→Focused→Recovering→Celebratory | Pulse→start by line cohort; no blank holes; Recovering lock post-gap | A7 shame relocation; T5 quote cap; no generative runtime content; Emotional Temperature constraints |
| **Awareness pulses** | Rest→Notice→Offer | Hand on shoulder, not alarm | User-scheduled only; action rate; respectful-silence activations | A3 prompt dependence (silence ramp); A6 rest; P5 zero unsolicited; F8 in-context permission |
| **Speak Time** (tiered) | → Notice (absorption interrupt) | Neutral lighthouse; orientation | Enabled-retention (H5); starts near spoken pulse; a11y coexistence | A2 vigilance (interval defaults 60); battery honesty P8; defer to screen reader; iOS honesty D9 |
| **Lapse re-entry / Fresh Start ritual** | Return → Relief → Fresh Start → Offer | **"I'm still welcome."** Relief before Confidence | Return-after-gap ≥20%; MicroStart within 24h of return (H9 ext.); Relief pulse research | A7; P3 zero debt; D6 identical layout; Recovering temperature; no auto-re-escalate pulses |
| **Onboarding** | Curiosity→Hope→ first Offer | Under-promised hope; first Action available | ≤5 decisions; ≤60s to possible MicroStart; session-one MicroStart ≥50% | P6 zero setup tax; no permission wall; no account; AntiGoals misuse review |
| **Completion moment** | Reflection; feeds Identity | Proportionate warmth; user-credited | Repeat rate; session end ≤15s after close; sentiment | A1; A4; P8 no bait-and-switch; Celebratory temperature only here |
| **Settings / retreat controls** | Enables P9; protects all transitions | Competence; control | Quiet-today usage; voice switch latency; analytics opt-out without loss | A8 tinkering (≤12 settings); P9 safety never buried; P11 |

## 2. Ritual overlay (same matrix, user-meaning view)

| Ritual | Primary features | Emotional arc stage |
|---|---|---|
| Morning Awareness | Widget, S1 content, optional pulse | Curiosity / Calm |
| Tiny Start | MicroStart stack | Action → Confidence |
| Fresh Start | Lapse re-entry + Recovering content | Lapse → **Relief** |
| Midday Reset | Pulse / Speak Time + S2 | Momentum / Grounded |
| Evening Reflection | S3 content, rest face | Reflective → Rest |

## 3. Engineering implications (non-implementing notes for Phase 3)

1. **Event names** should follow MicroStart vocabulary
   (`microstart_started`, `microstart_completed`, `microstart_abandoned_lt_20s`)
   — never "session" as the primary noun.
2. **Content serving** must accept `emotional_temperature` as a first-class
   filter dimension (schema already in `ContentSystem.md`).
3. **Gap-return flag** is a one-shot UX state, not a stored "days missed"
   counter — implementing a counter that could ever be displayed violates
   P1/P3 even if "only used internally" (leak risk).
4. **Respectful-silence** and **post-start cooldown** are behavior-
   architecture requirements, not notification nice-to-haves.
5. Every new surface PR in Phase 3+ must add or update a row in §1 and
   pass `AntiGoals.md` mandatory misuse questions.

## 4. Open items carried into Phase 3

- Confirm analytics event dictionary against this matrix
  (`Analytics.md` TBD).
- Widget long-term concept remains open (`Widgets.md` §2); behavior
  contract (Notice + Start co-located + no debt) is fixed even if visuals
  change.
- Voice display labels open (`ToneNamingExploration.md`); ids fixed.

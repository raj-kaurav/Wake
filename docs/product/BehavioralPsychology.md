# Behavioral Psychology — The Applied Model

**Phase:** 1 — Product Documentation
**Status:** Draft for review
**Purpose:** The single-page-deep account of *how Wake works on a human*,
distilled from the Phase 0 research corpus into the model that every
designer, engineer, and copywriter on this project must hold in their head.
Full evidence and citations live in `../research/`.

---

## 1. The Wake Behavioral Model

A person facing a task at any moment sits on a balance:

```
                 anticipated aversiveness of starting
  RESISTANCE  =  ------------------------------------
                 felt reality of time & consequence
```

Procrastination wins when the numerator is inflated (the task *feels* huge,
vague, and threatening) and the denominator is deflated (today feels
infinite, the deadline abstract, the future self a stranger).

Every Wake surface works on exactly one side of that fraction:

| Surface | Side | Mechanism (research doc) |
|---|---|---|
| Time Awareness Widget | ↑ denominator | Delay discounting attacked by ambient, granular, finite-day rendering (`ProcrastinationScience.md` §2.1, §3.1) |
| Speak Time | ↑ denominator | Interrupts absorption via auditory channel; externalizes time for time-blind users (`ExecutiveFunctionADHD.md`) |
| Start Now | ↓ numerator | Sub-threshold first action + 120-second self-contract + just-get-started affect shift (`EvidenceBasedInterventions.md` §1) |
| Content Engine | both | Reframes shrink the numerator ("you don't need ready"); granular time facts raise the denominator ("this week is 40% over") |
| Voice system & lapse recovery | keeps the fraction honest | Shame *inflates* the numerator on the next approach; self-compassion deflates it (`ProcrastinationScience.md` §2.2) |

The model's two management rules:

1. **Never raise the denominator by force** (fear, catastrophe, fake
   urgency) — under low self-efficacy that produces avoidance, not action.
   Raise it by *perception*: make real time visible, audible, near.
2. **Never let anything we ship raise the numerator** — every notification,
   every line of copy, every empty state is checked against "does this make
   the next start feel bigger?"

## 2. The Core Loop, Psychologically Annotated

**Glance** (widget: the day has a shape; today is finite) →
**Cue** (optional pulse: "It's 14:00" — a synthetic implementation-
intention trigger) →
**Offer** (one button; the ask is 120 seconds — anchored small,
autonomy-supportive, no "should") →
**Start** (the contract begins; the app goes silent — the work is the
experience) →
**Shift** (2 minutes in, anticipated aversiveness collapses toward
experienced reality; Ovsiankina pull toward continuing appears) →
**Honest end** (timer ends as promised; genuine credit *to the user*;
peak–end rule makes this the session's memory) →
**Re-loop or rest** (continuing is the user's silent choice; stopping is a
full win; absence is never punished).

One pass through this loop is the product. Everything else in the app
exists to make passes more likely.

## 3. The Anti-Spiral: Lapse Psychology

The delay → guilt → anxiety → avoidance spiral is broken at the guilt
stage, because that is where the evidence gives us leverage
(self-forgiveness → less subsequent procrastination):

- Absence accumulates nothing (P3). There is no streak to have broken.
- Re-entry surface = today's time + one button + one fresh-start line
  ("The afternoon is a clean page") — landmark framing recruited
  deliberately (`BehavioralEconomics.md` §2).
- The word "again," the word "still," and all references to the gap are
  banned from every surface (`MicrocopyStrategy.md`).

## 4. Individual Differences the Model Respects

- **Voice preference is real:** challenge reads as respect to some, threat
  to others; chosen registers are better tolerated (self-determination).
  Hence two voices under one contract.
- **Time blindness is literal** for a large minority: the perceptual layer
  is assistive, not decorative — shape over digits, sound over sight,
  externalized intention over memory.
- **Anxiety tilts framing:** depletion framing threatens where opportunity
  framing activates (H2). Framing is voice- and user-tunable, with the calm
  default (P9).

## 5. What We Deliberately Do Not Use

Documented with evidence in `../research/EvidenceBasedInterventions.md` §4;
constitutionally banned by `ProductPrinciples.md`:

shame/guilt messaging · fear appeals · streaks as motivation ·
loss-gamification (dead trees) · statistics dashboards · generic
inspiration · manufactured urgency · variable-reward mechanics ·
mortality salience as a blunt instrument (the opt-in Stoic pack is
reflective practice, never pressure, and ships only after dedicated
ethics review).

## 6. Where the Model Is a Bet

Honesty ledger (P12): sub-threshold starting and self-compassion effects
are strongly evidenced; the *ambient widget* and *spoken time* mechanics
are plausible extrapolations, not proven interventions. They are
instrumented as hypotheses H1–H5 (`UserResearchHypothesis.md`), and this
document gets revised if the data disagrees.

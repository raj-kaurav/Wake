# Product Goals

**Phase:** 1 — Product Documentation
**Status:** Draft for review
**Purpose:** The goal hierarchy connecting vision to measurable outcomes.
Metrics definitions and instrumentation live in `SuccessMetrics.md`; this
document says *what we are trying to cause*.

---

## Goal Hierarchy

### North-Star Outcome (the user's life)

> **Users start meaningful work more often, sooner, and with less distress
> than before Wake.**

Everything below serves this. Note the third clause: a version of Wake that
increased starts *and* anxiety would be a failure (P4, H8).

### G1 — Perception: users feel time passing

Users report and demonstrate increased awareness of the day's passage —
the widget is glanced at, spoken time is kept enabled, and users describe
the day as having a felt shape.

- Signals: widget retention (kept installed ≥30 days), Speak Time
  enabled-and-retained rate, qualitative "I notice the day now" reports.
- Constitutional constraint: perception must read as clarity, not dread
  (H8 guardrail).

### G2 — Action: awareness converts to starts

The felt day produces real two-minute starts.

- Signals: starts per active user per day (primary product metric);
  widget/notification → start conversion; time-from-cue-to-start.
- Constraint: a start is a *user action in their life*, not an app event
  to maximize by nagging — cue volume is capped by user schedule (P9).

### G3 — Momentum without pressure: starts recur and survive lapses

The loop repeats across days and, critically, resumes after gaps.

- Signals: proportion of users starting on ≥3 days in their first 14
  ("resilient adoption" — deliberately not a streak); return-after-gap rate
  (≥7-day absence followed by a start); re-entry-to-start time.
- Constraint: measured without ever being shown to the user as a record
  (P1, P3).

### G4 — Emotional safety: the product never adds harm

Wake is experienced as calming/clarifying, in both voices, including at
low moments.

- Signals: week-1 sentiment pulse (target ≥70% calm/clarifying, H8);
  voice-switch patterns (Coach→Friend switches after low-activity days as a
  distress proxy — research signal only, never a trigger for messaging);
  absence of shame-related complaints in reviews/support.
- This goal has veto power: features that lift G2 but damage G4 are
  rejected (conflict rule in `ProductPrinciples.md`).

### G5 — Trust and restraint: the product stays small and honest

The app remains one loop deep, keeps its promises, and wants users to
leave.

- Signals: median session length stays *low* (guardrail: if it grows,
  something is wrong); timer promises kept 100% (no auto-extensions);
  settings decision count ≤ the five-decision ceiling; zero dark-pattern
  findings in review.

## Business Goals (subordinate, constrained)

Sustainability without corrupting the above:

- B1: Organic-led growth from Tier-1/2 segments (the product's restraint
  *is* the story; press/community interest in "the app that wants you to
  leave" positioning).
- B2: A monetization model that survives the ethics floor
  (`../research/EthicalConsiderations.md` §4.5): no paywalled safety
  controls, no guilt upsells, no urgency theater. Model selection is a
  post-MVP-validation decision; both Forest-style one-time and honest
  subscription remain candidates.
- B3: Cost structure compatible with local-first architecture (no
  per-user server costs for core loop) — keeps B2 honest.

## Non-Goals (binding)

- Maximizing engagement, sessions, opens, or time-in-app.
- Becoming a system of record for tasks, habits, or schedules (P7).
- Team/enterprise features, manager visibility, social graphs.
- Clinical outcomes or medical claims (`ExecutiveFunctionADHD.md` §4).
- Being everything to everyone — Tier-3 audiences are served incidentally,
  never targeted at the cost of Tier-1 sharpness.

## Goal Conflicts, Pre-Decided

| Conflict | Ruling |
|---|---|
| G2 (more starts) vs. G4 (no pressure) | G4 wins; cue volume stays user-controlled |
| G3 (recurrence) vs. P3 (no streaks) | Recurrence is measured, never displayed as a chain |
| B-goals vs. any G-goal | G-goals win; the constitution outranks revenue |
| Growth (B1) vs. restraint (G5) | Restraint is the growth strategy; no viral mechanics that violate P5 |

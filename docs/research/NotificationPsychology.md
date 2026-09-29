# Notification Psychology Research

**Phase:** 0 — Discovery & Research (added in revision 1)
**Status:** Draft for review
**Purpose:** Ground Wake's notification behavior in interruption and
receptivity research. Notifications are our most invasive surface and the
fastest way to lose a user's trust; this document defines the science-derived
constraints that Phase 2's `NotificationStrategy.md` must satisfy.

---

## 1. The Baseline Reality

- Smartphone users receive on the order of 60–100+ notifications daily
  (industry telemetry; Pielot et al.'s field studies found dozens/day years
  ago, trending upward). We enter a hostile, saturated channel.
- Interruptions carry real cognitive cost: task-switch recovery is measured
  in minutes (Mark et al.'s office studies; the popularized "23 minutes"
  figure is context-specific, but the direction is uncontested).
- Yet users keep notifications on because intermittent relevance pays off —
  a variable-reinforcement dynamic we must *not* exploit (prohibited in
  `EthicalConsiderations.md` §2) but must design within.

**The paradox we must resolve:** Wake's premise involves interrupting
absorption (that is what an awareness pulse *is*), while interruption science
warns interruptions are costly. Resolution: our interruptions are (a) chosen,
(b) scheduled by the user, (c) content-light, (d) actionable in one tap, and
(e) cheap to dismiss. An interruption the user commissioned is an alarm
clock, not spam.

## 2. Receptivity: When Notifications Land

- Receptivity varies enormously with context: transitions between activities
  are the best moments; mid-task and high-cognitive-load moments the worst
  (Mehrotra et al.; Pejovic & Musolesi's interruptibility research).
- **Design consequence:** Fixed-interval Speak Time will inevitably hit bad
  moments; the mitigations are user-controlled quiet hours, one-tap
  "silence for today," and honoring OS Focus/DND absolutely. Smart
  context-aware timing (activity recognition) is a v2+ research topic — it
  requires sensors/permissions that violate MVP minimalism.
- **Deliberate simplification:** predictable timing has its own virtue — the
  user *knows* 12:30 is coming, which builds the time-scaffold habit
  (`HabitFormation.md` §4.2). We trade optimal receptivity for
  predictability and consent. Documented as a conscious trade-off.

## 3. Habituation & Alert Fatigue

- Repeated identical alerts stop reaching consciousness within days
  (habituation is the nervous system's default response to repetition
  without consequence; alarm-fatigue literature in clinical settings is
  stark).
- **Design consequences:**
  1. **Variation within predictability:** timing stays fixed; *content*
     rotates (Content Engine slots) and spoken phrasing can vary subtly
     ("12:30" / "half past twelve" — voice-dependent).
  2. **Scarcity of voice:** the fewer notifications we send, the longer each
     retains power. Default budget: awareness pulses the user scheduled +
     timer completion + nothing else. **Zero unsolicited notifications.**
  3. **Instrument decay:** interval-widening or disabling within week one is
     our habituation telemetry (Open Question Q5).

## 4. Notification Content Psychology

- **Actionability:** notifications with a clear immediate action outperform
  informational ones; every Wake notification carries the Start action
  (Android action button / iOS notification action) — awareness and action
  ship as one unit (design law from `WhyProductivityAppsFail.md` F6).
- **Brevity and concreteness:** long or abstract notification text is
  skimmed as noise. Budget: ≤ ~40 characters of primary text where feasible.
- **Autonomy-supportive language** ("could," invitation, choice) outperforms
  controlling language ("must," "should," "don't forget!") for intrinsic
  motivation (self-determination theory; Legault's autonomy-support work) —
  full treatment in `MicrocopyStrategy.md`.
- **No guilt hooks.** Re-engagement notifications ("We miss you!", "Your
  streak is in danger!") are the industry standard and are prohibited here
  (`EthicalConsiderations.md` §2). A user who ignores Wake for two weeks
  hears nothing from us; their scheduled pulses continue only if *they*
  scheduled them, and even those auto-quiet after sustained non-interaction
  (respectful-silence rule — to be specified in Phase 2).

## 5. Permission Psychology

- Cold permission prompts at first launch are the highest-refusal pattern;
  priming screens that explain value before the OS dialog substantially
  raise grant rates (industry-standard finding, replicated widely).
- iOS "provisional authorization" (quiet delivery without a prompt) is an
  option worth evaluating — though quiet delivery undermines Speak Time's
  sound, so the explicit prompt at the right moment is likely better for us.
- **Design consequence:** Wake asks for notification permission only at the
  moment the user schedules their first awareness pulse or Speak Time — the
  value is self-evident right then. Onboarding never front-loads permission
  dialogs. Denial degrades gracefully (widget + in-app remain fully
  functional) and the ask can be revisited from the feature's own settings.

## 6. Batching & Well-Being Evidence

- Fitz et al. (2019): batching notifications to a few predictable times
  improved attentional and affective outcomes vs. unpredictable delivery;
  total silence performed worse than batching (FOMO effects).
- **Relevance:** Direct support for Wake's model — a small number of
  *scheduled, predictable* signals is the empirically favored notification
  diet. We are, in a sense, a notification-batching philosophy applied to
  time itself.

## 7. Constraints Handed to Phase 2 (`NotificationStrategy.md`)

1. Every notification is user-scheduled or user-caused. Zero marketing, zero
   re-engagement, zero streak threats.
2. Every notification carries exactly one action (Start) plus cheap dismiss.
3. Respect DND/Focus without exception; quiet hours default on (sleep
   window from onboarding).
4. One-tap "quiet today" on every awareness notification.
5. Content varies; schedule doesn't. Rotation from Content Engine slots.
6. Permission requested in-context, never at first launch; graceful denial
   path.
7. Respectful-silence rule: sustained non-interaction downgrades frequency
   automatically (spec in Phase 2).
8. Budget ceiling: a user following defaults receives ≤ ~12 wake-window
   pulses/day (60-min interval) — and the *default* Speak Time state is a
   choice for Phase 1/2 to make deliberately (proposal: off until invited
   during onboarding's "how loud should time be?" step).

## 8. Key Sources

- Pielot, M., et al. — field studies of mobile notification volume/response.
- Mark, G., et al. — interruption and task-switch recovery studies.
- Mehrotra, A., et al.; Pejovic, V., & Musolesi, M. — interruptibility and
  receptivity modeling.
- Fitz, N., et al. (2019). Batching smartphone notifications can improve
  well-being. *Computers in Human Behavior.*
- Legault, L., et al. — autonomy-supportive vs. controlling messaging.
- Deci, E., & Ryan, R. — self-determination theory.

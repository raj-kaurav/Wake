# Product Principles — The Wake Constitution

**Phase:** 1 — Product Documentation (permanent document)
**Status:** Draft for ratification
**Authority:** This is the project's constitution. Every feature, screen,
line of copy, metric, and architectural decision must satisfy these
principles. A proposal that violates a principle is rejected by default; the
only override is an explicit product-owner amendment to this document, with
the rationale recorded in the changelog. Later-phase documents (UX,
architecture, engineering rules, `.cursor/` AI-development rules) must
implement — never dilute — what is written here.

---

## The Two Pillars

> **Pillar I — Make time felt, not tracked.**
> Time is rendered as a perceptible, ambient, emotional experience — never
> as accounting, dashboards, or audit trails.

> **Pillar II — Make starting smaller than resisting.**
> At every moment of awareness, the smallest possible real action is one tap
> away. The product exists to shrink the first step below the user's
> resistance threshold.

Short form, used as the product philosophy everywhere:
**"Make time felt. Make starting small."**

Everything below elaborates these pillars into testable rules.

---

## P1 — Time felt, not tracked

The product shows the *present* — today's shape, the hours remaining, the
now. It does not account for the past.

**Test:** Does this feature show time as experience (shape, sound, moment)
rather than as records (charts, histories, totals)?
**Violations:** weekly reports, usage graphs, "you focused 3h this week,"
any surface whose subject is the past.

## P2 — Awareness always carries an exit ramp

Every "time is passing" signal is paired with exactly one immediate action
(Start) or an explicit grant of rest. Awareness without an action affordance
manufactures anxiety, which increases procrastination.

**Test:** From this surface, is a real start exactly one tap away?
**Violations:** informational notifications with no action; widget states
that only display; content that inspires without pointing at a next step.

## P3 — No visible debt, ever

The app never accumulates or displays failure: no overdue states, no missed
days, no broken streaks, no "you last opened this 12 days ago." Yesterday
does not exist in the UI. Lapse re-entry is weightless and warm.

**Test:** Can any screen make a returning user feel accused? Then it fails.
**Violations:** streaks, red badges, ledgers, "we missed you," dead trees,
disappointed mascots, any state that is worse *because the user was away*.

## P4 — Challenge the behavior, never the person

Both voices target the behavior and the moment. Neither voice — however
challenging — may attack identity, invoke shame, catastrophize, compare the
user to others, or reference accumulated failure. Self-compassion is an
evidence-based intervention, not a soft option.

**Test:** Every content line passes the review checklist in
`../research/EthicalConsiderations.md` §5 before shipping.
**Violations:** "you're lazy," "still not started?," "everyone else is ahead
of you," profanity-as-edge, guilt hooks.

## P5 — Success is the user leaving the app

The product optimizes time-to-exit-into-action, never session length,
opens, or engagement. No feature may exist to generate app time.

**Test:** Does this feature move the user toward real work, or toward more
app? Metrics derived from it must reward the former
(`SuccessMetrics.md`).
**Violations:** feeds, browsable content libraries, engagement streaks,
variable-reward mechanics, re-engagement notifications.

## P6 — Zero setup before value

The core loop (feel time → start) is reachable within 60 seconds of first
open: no account, no goal wizard, no permission wall. Configuration is
optional, later, and minimal.

**Test:** Can a brand-new user start a two-minute session before making any
decision except (optionally) choosing a voice?
**Violations:** mandatory registration, multi-step goal setup, cold
permission prompts at first launch.

## P7 — No lists, no ledger, no lecture

The app stores at most **one current intention** — never a list of tasks,
never a schedule that can break, never educational sermons. We are not a
todo app, a habit tracker, a Pomodoro manager, or a calendar. Plans that can
break create broken-day psychology; we have no breakable plans.

**Test:** Does this feature create a second stored obligation, or a plan
with a failure state? Rejected.
**Violations:** task lists, projects, time-blocking, habit schedules,
multi-step programs, "day 3 of your journey."

## P8 — Honest mechanics only

Every promise the UI makes is kept literally. The two-minute timer ends in
two minutes with genuine congratulation and no bait-and-switch. No fake
urgency, no manufactured scarcity, no dark patterns. The user's trust in the
button is the entire asset. The standing test: *would the user endorse this
mechanic if they fully understood how and why it works?*

**Violations:** auto-extending timers, countdown pressure detached from real
time, fake "limited offer" anything, deceptive defaults.

## P9 — Chosen intensity, instant retreat

Every awareness channel (widget framing, spoken time, notification pulses,
future philosophy pack) is opted into knowingly, tunable, and disableable in
one obvious step. Safety-relevant controls (voice switch, quiet hours,
mute today, disable feature) are never buried and never paywalled. The
default configuration is the calmest coherent product; intensity is
invited, not imposed. Mortality-themed content ("The Stoic" pack) is
disabled by default and gated behind explicit consent, permanently.

**Test:** Can the user retreat from any signal in one tap, without losing
anything else?

## P10 — Accessibility is the premise, not a checklist

Wake's founding feature is accessibility-inspired (spoken time). Time must
be feelable through sight, sound, and touch: every visual carries a text
alternative, every audio signal a visual one; contrast, font scaling, screen
readers, and reduced motion are launch requirements. Design assumes a large
minority of users experience time-blindness (the curb-cut effect: it makes
the product better for everyone).

**Test:** Can a blind user, a deaf user, and a user with a screen reader
each complete the full core loop?

## P11 — Local-first, minimal data

Core features work offline, without an account. We collect the minimum
(a voice choice, a wake window, optional intervals, one optional intention
string — all stored on-device). No behavioral data is sold or shared;
analytics are minimal, aggregate, and honest. Speech is generated on-device.
Any future cloud feature must re-clear this principle explicitly.

**Test:** Would we be comfortable if this data flow were shown to the user
in plain language? Is each collected field defensible one by one?

## P12 — Evidence over intuition

Every feature traces to a documented mechanism in the Phase 0 research; new
feature proposals must name their mechanism and its evidence rating. Where
our mechanics are unvalidated (the widget's effect, spoken time), we
instrument honestly and let results overrule preference. When evidence and
aesthetics conflict, evidence wins.

**Test:** Can the proposer cite the research document and section this
feature operationalizes?

## P13 — Restraint is the brand

One button, few words, silence while the user works, no feature added
because it would be easy. Complexity is the tax every failed productivity
app paid; we do not pay it. When in doubt, leave it out.

**Test:** Does removing this element break the core loop? If not, it must
argue for its existence.

---

## How to Use This Document

- **Feature reviews:** every proposal names, in writing, how it satisfies
  each pillar and which principles it touches (template to be defined in
  Phase 4's review checklist).
- **Conflicts:** if two principles appear to conflict, P4 (never shame) and
  P8 (honesty) outrank all others; then P5 (user leaves); then the rest.
- **Amendments:** product-owner approval + changelog entry + review of all
  documents that cited the amended principle.

## Changelog

- **v0.1** — Created in Phase 1 per Phase 0 review feedback ("a permanent
  constitution defining non-negotiable principles"). Consolidates the design
  laws of `../research/ProcrastinationScience.md` §6, the counter-principles
  of `../research/WhyProductivityAppsFail.md`, and the standing ethical
  commitments of `../research/EthicalConsiderations.md` §6.

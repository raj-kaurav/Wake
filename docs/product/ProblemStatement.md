# Problem Statement

**Phase:** 1 — Product Documentation
**Status:** Draft for review
**Research basis:** `../research/ProcrastinationScience.md`,
`../research/WhyProductivityAppsFail.md`

---

## The Problem

Capable people voluntarily delay the actions they themselves judge most
important — despite knowing better, despite wanting otherwise, and despite
an entire industry of productivity tools. The delay is not caused by missing
information, missing plans, or missing discipline. It is caused by two
perceptual-emotional failures that current tools do not address:

1. **Time passes invisibly.** The present day has no felt shape; futures
   are abstract; deadlines are unreal until panic makes them real. In
   behavioral-economic terms: delayed outcomes are steeply discounted, and
   nothing in the environment counteracts the discount until it is too late
   (present bias; temporal motivation theory).
2. **Starting feels worse than it is.** Task aversiveness is front-loaded:
   the anticipation is worse than the doing. Avoidance delivers immediate
   relief, which reinforces itself (mood-repair model). Each avoided start
   adds guilt, which makes the next approach more aversive — the
   delay → guilt → anxiety → avoidance spiral.

## Who Has This Problem, and How Badly

- Nearly everyone situationally; an estimated 15–20% of adults chronically,
  and roughly half of students report procrastination as a serious problem
  (Steel, 2007).
- Concentrated in self-directed work: students, developers, designers,
  creators, founders — people with autonomy over their hours and therefore
  maximal exposure to the starting problem.
- Disproportionately severe for people with executive-function differences
  (time blindness in ADHD), for whom time is literally harder to perceive —
  and who are failed hardest by shame-based and plan-based tools
  (`../research/ExecutiveFunctionADHD.md`).

**Costs:** missed deadlines and opportunities, chronic background anxiety,
eroded self-trust ("I can't rely on myself"), health effects documented in
the procrastination–stress literature, and the cumulative unlived potential
the brief calls the quiet tragedy.

## Why Existing Solutions Don't Solve It

Full analysis in `../research/WhyProductivityAppsFail.md`; the essence:

- **Task managers** (Todoist, TickTick) organize obligations; organization
  was never the deficit. Their overdue-red ledgers convert the tool itself
  into a guilt artifact that users learn to avoid.
- **Blockers** (Forest, Opal, Freedom, One Sec) remove distractions — the
  *escape route* — but do nothing about the *wall*: a blocked phone beside
  an unstarted task is still an unstarted task.
- **Planners/time-blockers** (Structured) presume the executive function
  they are supposed to replace, and shatter visibly at the first slipped
  block.
- **Motivation/quote apps** decorate the avoidance with inspiration that
  decays in minutes and carries no action.
- **All of them** measure success in engagement, which points their design
  incentives *into* the app and away from the user's actual work.

The common blind spot: **no product operates at the moment between "I
should" and "I am"** — the moment where the evidence says leverage is
highest, and the moment Wake is built for.

## The Problem, Restated as Design Requirements

| Problem mechanism | Requirement |
|---|---|
| Time passes invisibly | Render today as an ambient, glanceable, feelable shape (Pillar I) |
| Futures feel unreal | Granular, near-term time language; finite-day framing |
| Starting feels too big | A first action smaller than resistance, one tap away, everywhere awareness appears (Pillar II) |
| Avoidance is self-reinforcing | Let users experience, repeatedly, that starting feels better than dreading — the loop that unlearns avoidance |
| Guilt fuels the spiral | Zero shame, zero visible debt, designed lapse re-entry (P3, P4) |
| Tools become guilt artifacts | The app never carries a record that can accuse (P1, P3) |

## What Success Against This Problem Looks Like

A user who, weeks in, says some version of: *"I notice the day now. When I
notice it, starting something small is easy. And when I disappear for a
week, coming back costs nothing."* Measured concretely in
`SuccessMetrics.md`.

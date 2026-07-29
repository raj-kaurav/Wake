# Habit Formation Research

**Phase:** 0 — Discovery & Research (added in revision 1)
**Status:** Draft for review
**Purpose:** Establish what habit science says about how starting behavior can
become automatic, and where habit mechanics help or harm this product.
Wake is not a habit tracker — but we do want one habit to form: *reaching for
the start button instead of the escape hatch.*

---

## 1. What a Habit Actually Is

A habit is a context–response association learned through repetition: a cue
in the environment triggers a behavior with reduced deliberation (Wood &
Neal, 2007; Wood & Rünger, 2016). Key properties relevant to us:

- **Habits are cue-dependent, not goal-dependent.** Once formed, they fire on
  context, even when motivation is absent. This is precisely the property we
  need, because our users' problem is acting *without* motivation.
- **Formation takes longer than folklore says.** Lally et al. (2010): median
  ~66 days to automaticity, with a range of 18–254 days, and — importantly —
  **missing a single day did not derail formation.** This single finding
  undermines the streak-anxiety model of most habit apps and supports our
  no-visible-debt principle with direct evidence.
- **Simplicity accelerates formation.** Simpler actions reached automaticity
  faster in Lally's data. A two-minute start is a formable habit; "work for
  three hours" is not.
- **Stable context is the strongest predictor.** Same cue, same place, same
  time → faster automaticity. Product implication: encourage (never require)
  a consistent daily "first start" moment.

## 2. The Habit Loop, Mapped to Wake

Using the cue → routine → reward frame (Duhigg's popularization of the
underlying associative-learning research):

| Loop element | Wake's implementation | Design risk to avoid |
|---|---|---|
| **Cue** | Widget glance; spoken time; a scheduled awareness notification | Cues that fire when action is impossible (in a meeting) train ignoring |
| **Routine** | Press Start Now → two minutes of real work | Any added step (choose task, configure timer) weakens the association |
| **Reward** | Genuine completion moment + the *intrinsic* relief of having started (the just-get-started affect shift is the true reward) | Over-rewarding with app confetti shifts the reward from the work to the app |

The deepest point: **the natural reward already exists** — starting feels
better than dreading. Our job is to get the user to experience that
contingency enough times for it to be learned. Artificial rewards (points,
pets) risk overshadowing the real one (an overjustification-adjacent
concern), and they anchor the habit to the app rather than to the work.

## 3. Streaks: The Evidence-Honest Position

- Streaks exploit loss aversion and do increase short-term engagement — the
  industry's revealed preference proves that much.
- But: the abstinence-violation effect (Marlatt's relapse research) and the
  Lally finding above both say a broken chain should be a non-event, while
  streak UIs make it a catastrophe. Post-break churn cliffs are a widely
  reported pattern in habit-app analytics.
- **Position:** No streaks in Wake. If we ever surface continuity at all, it
  must be *resilient* continuity (e.g., "you've started 9 of the last 14
  days" — a rate that a miss dents but never zeroes). Even that is deferred:
  it is a statistics surface and must clear Principle "time felt, not
  tracked" review.

## 4. Habit Formation Applied to Our Surfaces

1. **The widget is a passive cue-in-training.** Dozens of daily glances at
   the day-shape build the association "phone glance → time is moving." The
   widget's job in habit terms is to *classically condition* time-salience
   onto an existing behavior (checking the phone) that needs no new habit.
2. **Speak Time is a temporal cue with built-in spacing.** Fixed intervals
   create predictable cue moments; predictability aids conditioning but
   accelerates habituation — see `NotificationPsychology.md` §3 for the
   mitigation (variation within predictability).
3. **Start Now benefits from an anchor.** Implementation-intention research
   plus habit-stacking practice (Fogg's "after I X, I will Y"; Clear's
   habit stacking) suggests onboarding should invite — with one optional
   question — an anchor moment: "When do you most want to start? After
   coffee? At 9:00?" One anchor, not a schedule.
4. **Lapse recovery is habit-protective, not just kind.** Since misses don't
   break formation (Lally), the honest message after a gap is "nothing is
   lost — same cue, same tiny start." Our compassionate re-entry flow is
   thus *technically correct* habit science, not merely gentle branding.

## 5. The Habit We Must NOT Build

App-checking habits. An engagement-optimized product would happily train
"bored → open Wake → browse content." That habit competes with the work.
Guardrails (feeding into `SuccessMetrics.md` and the Phase 6 rules):

- No feeds, no browsable content library in-app.
- Session-length is a guardrail metric to keep *low*.
- Notifications never exist to generate opens; they exist to trigger starts.

## 6. Key Sources

- Lally, P., et al. (2010). How are habits formed: modelling habit formation
  in the real world. *European Journal of Social Psychology.*
- Wood, W., & Neal, D. (2007). A new look at habits and the habit–goal
  interface. *Psychological Review.*
- Wood, W., & Rünger, D. (2016). Psychology of habit. *Annual Review of
  Psychology.*
- Marlatt, G. A. — relapse prevention research (abstinence-violation effect).
- Fogg, B. J. (2019). *Tiny Habits.* (practice-derived, consistent with the
  implementation-intention literature)
- Gollwitzer, P., & Sheeran, P. (2006) — see shared bibliography.

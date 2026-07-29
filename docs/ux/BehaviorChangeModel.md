# Behavior Change Model

**Phase:** 2 — UX Documentation (added per Phase 1 review feedback)
**Status:** Draft for review
**Purpose:** Formalize the behavioral loop the product is designed to
influence, so that every UX decision can be located on the loop and every
loop transition has named design levers and measurements. This
operationalizes `../product/BehavioralPsychology.md` (the mechanism) into
a state machine (the design object).

---

## 1. The Formal Frame

We use Fogg's parsimonious model as the spine — **Behavior happens when
Motivation, Ability, and a Prompt converge (B = MAP)** — because it maps
cleanly onto product surfaces:

- **Prompt** — Wake supplies it: widget glance, awareness pulse, spoken
  time.
- **Ability** — Wake maximizes it: the ask is 120 seconds, one tap, no
  decisions.
- **Motivation** — Wake does *not* try to inflate it (motivation is
  volatile and fear-inflation is banned); instead the voice/content system
  *unblocks* it by lowering the emotional cost (reframes, permission,
  no shame).

The strategic statement: **most products chase motivation; Wake engineers
ability and prompts, and merely protects motivation from shame damage.**

## 2. The Wake Loop (target behavior cycle)

```
        ┌────────────────────────────────────────────────────┐
        │                                                    │
        ▼                                                    │
   [1 NOTICE] ──► [2 OFFER] ──► [3 START] ──► [4 SHIFT] ──► [5 CLOSE]
   time felt      one tap       contract      2-min          honest end
   (widget,       (Start,       begins        affect         (credit,
   pulse,         everywhere)   (silence)     change         rest or
   spoken time)                               (dread<real)   continue)
        ▲                                                    │
        │                                                    ▼
        └──────────────── [6 REST / LIFE] ◄──────────────────┘
                                │
                     (absence of any length)
                                │
                                ▼
                     [L1 RETURN] ──► [L2 FRESH START] ──► rejoins at [2]
                     weightless      landmark framing
```

### Transition specifications

| Transition | What must happen in the user | Design levers | Failure mode | Measured by |
|---|---|---|---|---|
| →1 NOTICE | Time becomes salient without threat | Widget shape, granular copy, spoken pulse; calm register | Salience reads as dread (R9) | Widget adds/retention; H8 pulse |
| 1→2 OFFER | Salience meets an available act | Start affordance co-located with every awareness surface (D3) | Awareness without exit ramp (P2 violation) | Prompt→offer view rate |
| 2→3 START | Resistance < 120-second ask | One tap, no decisions, anchor-small copy, optional intention prefilled | Any interposed choice; oversized ask | Offer→start conversion; time-to-start ≤10 s |
| 3→4 SHIFT | Experienced task < anticipated task | Silence (D5); no mid-timer interference | Mid-timer interjections restore self-consciousness | Cancel rate in first 20 s vs. after |
| 4→5 CLOSE | The start is banked as a win, whatever comes next | Honest end; proportionate credit to *user*; continue = silent option, stop = full win | Bait-and-switch upsell (P8); inflated praise | Completion-screen sentiment; repeat rate |
| 5→6 REST | Wake exits the user's attention | Nothing follows the close; no "one more?" | Post-completion engagement hooks (P5) | Session ends ≤15 s after close |
| 6→1 (re-loop) | Next natural prompt lands | Scheduled pulses; landmark slots | Prompt fatigue (R1) | Pulse→start decay slope |
| 6→L1 RETURN | Coming back costs nothing | Zero-trace absence (D6); standard home | Any gap acknowledgment | Return-after-gap rate (≥20% target) |
| L1→L2 FRESH START | Past is closed; now is a clean page | Fresh-start line (landmark framing); one button | Ledger leakage ("still", "again") | Post-return start rate |

## 3. The Competing Loop (what we are displacing)

The avoidance loop we intervene against, stated formally so designers know
the enemy's shape:

```
[task cue] → [anticipatory aversion] → [escape act (scroll/clean/watch)]
     ▲            (inflated by shame          │
     │             from prior cycles)         ▼
     └──────── [relief (negative reinforcement)] ← [guilt accrual]
```

Interception points and which Wake element owns each:

1. **Task cue → aversion:** Content Engine reframes shrink the imagined
   task (construal repair).
2. **Aversion → escape:** the Offer must be *cheaper than the escape* —
   this is why one tap and zero decisions is a hard budget, not polish:
   we compete with an infinitely low-friction scroll.
3. **Relief reinforcement:** the 4-SHIFT stage supplies a *better relief*
   (started > escaped) — the only sustainable substitute reinforcer.
4. **Guilt accrual:** severed by design — no ledger, no shame, weightless
   return (the loop's compounding term is deleted).

## 4. Stage Model Across the User Lifetime

The loop's operation changes with tenure (companion doc:
`EmotionalJourney.md`):

| Tenure stage | Loop reality | Design posture |
|---|---|---|
| **Scaffolding** (weeks 0–2) | Prompts are external (pulses, widget); ability engineered; every close matters | Maximum reliability of prompts; peak–end investment |
| **Association** (weeks 2–8) | Context cues begin firing without Wake (desk → start); habit forming per `../research/HabitFormation.md` | Stable cue timing; anti-habituation content variation |
| **Internalization** (months 2+) | Self-initiated starts dominate; Wake is confirmation, not cause | Prompt-dependence must *fall* (SuccessMetrics §5 guardrail); never fight this with re-engagement |
| **Autonomy / graduation** | User needs Wake rarely; time-feel persists unaided | Celebrate by absence of resistance: no win-back, no guilt; the door stays open (P3) |

**The model's most countercultural commitment:** stage 4 is success, not
churn (`UserSuccessDefinition.md`). All lifecycle UX must be built to
*hand control back*.

## 5. Model Boundaries (what this loop does not claim)

- It produces **starts**, not finished projects — downstream completion
  belongs to the user's life, not our loop (P7 keeps us out of it).
- It does not treat clinical conditions; for users whose aversion has
  clinical roots the loop must merely be *safe*, per the medical boundary.
- It assumes the user already knows their task (audience definition);
  the loop has no task-selection stage by design.

## 6. Using This Model

- Every UX proposal must name the transition(s) it serves. A feature
  serving no transition is decoration (P13).
- Every experiment (H-series) maps to a transition metric in §2's table.
- Anti-goals are loop corruptions — each entry in `AntiGoals.md` names the
  transition it corrupts.

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

### 2.1 Sequential view (one pass)

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
                     (Relief first — EmotionalJourney)
```

### 2.2 Reinforcing loop (how Identity strengthens future Notice)

One pass is necessary but incomplete. Over tenure, closes accumulate into
a self-story that changes how the *next* Notice lands — that is the
reinforcing loop. Conceptual only; product behavior does not change.

```
   NOTICE ──► OFFER ──► START (MicroStart) ──► MOMENTUM (shift)
      ▲                                            │
      │                                            ▼
   IDENTITY ◄── REFLECTION (close / credit) ◄──────┘
   ("I start")     (honest end; user-attributed)
```

| Node | What it adds beyond the sequential pass |
|---|---|
| **Momentum** | Same as SHIFT: experienced aversiveness collapses; Ovsiankina pull appears — the felt "I could keep going" |
| **Reflection** | CLOSE made conscious: the T6 line banks the win as *the user's*, not the app's (IKEA / effort-justification rule) |
| **Identity** | Repeated Reflections revise the self-story from "I procrastinate" toward "I start" (`EmotionalJourney.md` Identity stage; `UserSuccessDefinition.md` rung 6) |
| **Identity → Notice** | The next glance / pulse lands on a person who already believes starting is *like them* — Notice reads as orientation, not as accusation; Offer conversion rises without Wake increasing pressure |

**Why behavior becomes easier over time (habit strengthening):**

1. **Cue association** — stable pulse times + widget glances classically
   condition time-salience onto existing phone checks
   (`../research/HabitFormation.md`).
2. **Ability stays constant; resistance falls** — each banked MicroStart
   shrinks anticipated aversiveness for the next (just-get-started
   learning).
3. **Identity as motivation substitute** — once "I start" is part of the
   self-story, Motivation in B=MAP needs less protection; Ability + Prompt
   suffice more often.
4. **Shame deleted** — weightless lapses (Relief) prevent the compounding
   term that usually undoes habit formation after the first miss (Lally:
   missed days do not derail automaticity).

**Why Wake must gradually reduce dependence:**

If Identity → Notice works, external prompts become optional scaffolding.
Fighting that (re-engagement, louder pulses, engagement features) would
steal the Identity credit back to the app and deepen prompt dependence
(AntiGoal A3). Graduation design (`BehavioralDesign.md` §7) is therefore
required by this reinforcing loop, not optional ethics: **Wake's job is
to make itself less necessary.** Measured by the prompt-dependence
guardrail (self-initiated share rising with tenure).

### Transition specifications

| Transition | What must happen in the user | Design levers | Failure mode | Measured by |
|---|---|---|---|---|
| →1 NOTICE | Time becomes salient without threat | Widget shape, granular copy, spoken pulse; calm register | Salience reads as dread (R9) | Widget adds/retention; H8 pulse |
| 1→2 OFFER | Salience meets an available act | Start affordance co-located with every awareness surface (D3) | Awareness without exit ramp (P2 violation) | Prompt→offer view rate |
| 2→3 START | Resistance < 120-second ask | One tap, no decisions, anchor-small copy, optional intention prefilled | Any interposed choice; oversized ask | Offer→start conversion; time-to-start ≤10 s |
| 3→4 SHIFT / MOMENTUM | Experienced task < anticipated task | Silence (D5); no mid-timer interference | Mid-timer interjections restore self-consciousness | Cancel rate in first 20 s vs. after |
| 4→5 CLOSE / REFLECTION | The start is banked as a win, whatever comes next | Honest end; proportionate credit to *user*; continue = silent option, stop = full win | Bait-and-switch upsell (P8); inflated praise | Completion-screen sentiment; repeat rate |
| 5→ IDENTITY (over tenure) | Self-story shifts toward "I start" | Repeated honest closes; no ledger; graduation posture | App taking credit; scorekeeping (A4) | Qualitative identity language; self-initiated share |
| IDENTITY →1 NOTICE | Next Notice lands as orientation, not threat | Same calm surfaces; lower intensity as tenure grows | Re-escalating prompts that fight graduation | Prompt-dependence declining (SuccessMetrics §5) |
| 5→6 REST | Wake exits the user's attention | Nothing follows the close; no "one more?" | Post-completion engagement hooks (P5) | Session ends ≤15 s after close |
| 6→1 (re-loop) | Next natural prompt lands | Scheduled pulses; landmark slots | Prompt fatigue (R1) | Pulse→start decay slope |
| 6→L1 RETURN | Coming back costs nothing (**Relief**) | Zero-trace absence (D6); standard home | Any gap acknowledgment | Return-after-gap rate (≥20% target) |
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

# Executive Function & ADHD Considerations

**Phase:** 0 — Discovery & Research (added in revision 1)
**Status:** Draft for review
**Purpose:** Deepen the ADHD/executive-function analysis sketched in
`ProcrastinationScience.md` §5 into concrete design guidance. Wake is not a
medical product and makes no clinical claims; but designing for impaired
executive function makes the product better for every user (curb-cut
effect), and this audience will find us whether we plan for them or not.

---

## 1. Executive Function: The Relevant Subsystems

Executive functions (Barkley's hybrid model; Brown's clinical model) most
implicated in task initiation:

| Function | Deficit expression | Wake surface it touches |
|---|---|---|
| **Time perception / temporal foresight** | "Time blindness": now vs. not-now as the only categories; futures feel unreal | Widget, Speak Time — the core product |
| **Task initiation (activation)** | Knowing, wanting, and still not starting; described clinically as a wall, not a choice | Start Now |
| **Working memory** | Intentions evaporate between rooms; out of sight = out of mind | Single visible intention; externalized cues |
| **Emotional self-regulation** | Frustration/shame flood faster and bigger | Voice system, lapse recovery |
| **Prospective memory** | Remembering to remember; missed self-appointments | Scheduled pulses as external prospective memory |

Two points the design must internalize:

1. **Time blindness is literal, not metaphorical.** Barkley documents genuine
   deficits in time reproduction/estimation in ADHD. For this population an
   ambient time display is assistive technology, not a nudge. Wake's core
   thesis is *strongest* here.
2. **Initiation failure is not motivation failure.** The clinical framing —
   activation deficit — matches our mood-repair model but adds: for ADHD
   brains, stimulation/interest gates action (the "interest-based nervous
   system" in clinical shorthand). Urgency, novelty, and immediacy are the
   accessible levers; long-horizon value is not. Start Now's 120-second
   immediacy is exactly the right shape.

## 2. Prevalence & Overlap With Our Audience

- Adult ADHD prevalence ≈ 2.5–5% diagnosed; substantially more subclinical.
- Procrastination severity correlates strongly with ADHD symptoms; among
  self-selected users of anti-procrastination tools, the ADHD-adjacent share
  is plausibly several times the base rate (see Structured's and Finch's
  visibly ADHD-heavy communities).
- **Planning consequence:** ADHD-adjacent users are not an edge segment; they
  are plausibly a plurality of our most engaged users and our loudest
  organic channel (ADHD TikTok/Reddit made Structured and Finch grow).
  Design defaults must work for them; marketing must not make claims at
  them (§5).

## 3. Design Guidance (the ADHD-informed checklist)

Each item benefits all users; the ADHD lens just makes the requirement
non-negotiable.

1. **Externalize; never rely on user memory.** The current intention (if
   set) is visible on the widget and start screen — never buried a tap away.
2. **Zero-step availability.** Cue → action distance must be one tap.
   Every additional screen is where ADHD users evaporate. (Cold start < 1 s
   budget already flagged.)
3. **Visual time, not numeric time, where possible.** Time Timer's success
   in ADHD settings argues for the shape-based widget over digit-based
   (numbers are *read*; shapes are *felt* — and reading is skippable).
4. **Immediate, honest reward.** Completion moment lands within the same
   breath as the action. Delayed or abstract rewards don't reinforce.
5. **No punishment mechanics, ever.** Rejection-sensitivity patterns
   (community-salient as "RSD," clinically debated but experientially real)
   mean our failure states must be weightless. A missed pulse, an unstarted
   day: zero visual residue.
6. **Novelty budget.** ADHD habituation to stimuli is faster; the Content
   Engine's variation-within-predictability (`NotificationPsychology.md` §3)
   is load-bearing here. Consider periodic subtle widget re-skins as an
   anti-habituation lever (Phase 5 design-system question).
7. **Hyperfocus is also a failure mode we serve.** Time blindness cuts both
   ways: users lose hours *inside* work or games. Speak Time is the only
   feature in our set that reaches a hyperfocused user (auditory channel
   while eyes are captured) — an argument for its priority despite platform
   pain.
8. **Settings simplicity.** Every configuration surface must pass a
   "decidable in 5 seconds" test; option paralysis is a real abandonment
   cause. Defaults + one alternative (`BehavioralEconomics.md` §4).
9. **Text minimalism.** Long onboarding copy is skipped; show, don't
   explain. (Also a general fluency rule.)

## 4. What We Deliberately Do NOT Build (medical boundary)

- No symptom screeners, no ADHD self-tests, no diagnosis language.
- No medication reminders, no clinical-outcome claims ("reduces ADHD
  symptoms" — never).
- No claims of being an "ADHD app" in store metadata. If ADHD communities
  adopt Wake (likely), that is organic; our copy stays about time and
  starting. Rationale: regulatory exposure (wellness vs. medical-device
  boundaries), ethics of overpromising, and the positioning decision that
  Wake is a **time awareness product for everyone**.
- Accessibility statement may honestly note the app's design is informed by
  executive-function research — factual, not clinical.

## 5. Research Opportunities Specific to This Segment

- Q5/Q1 instrumentation should segment (opt-in, self-described) "I lose
  track of time easily" users — a non-clinical proxy question at onboarding
  research stage (not in the shipped product's onboarding for MVP).
- Beta recruiting should deliberately include ADHD-community testers; their
  failure modes surface at 10× speed and predict the general population's.

## 6. Key Sources

- Barkley, R. (1997; 2012). ADHD and the nature of self-control; executive
  functions research program (time-perception studies).
- Brown, T. — executive function model of ADHD.
- Ptacek, R., et al. (2019). Clinical implications of the perception of time
  in ADHD (review).
- Sonuga-Barke, E. — delay aversion model of ADHD.
- Community/practice sources (Time Timer adoption in ADHD education; "body
  doubling" practice) — practice-based, flagged as such.

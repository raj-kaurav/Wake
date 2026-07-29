# Evidence-Based Interventions Against Procrastination

**Phase:** 0 — Discovery & Research
**Status:** Draft for review
**Purpose:** Catalog interventions with empirical support, rate the strength of
evidence, and assess whether each can be delivered by a mobile app. This is the
menu Phase 1 will select from.

Evidence ratings used below:

- **Strong** — meta-analytic support or multiple RCTs.
- **Moderate** — several studies, consistent direction, or one good RCT.
- **Emerging** — plausible mechanism, limited direct studies.
- **Folk** — popular and plausible but not directly validated.

---

## 1. Interventions That Reduce the Cost of Starting

### 1.1 Implementation intentions ("when X, then I will Y")

- **Evidence: Strong.** Gollwitzer & Sheeran (2006) meta-analysis, d ≈ .65
  across 94 studies; specifically shown to help procrastinators close the
  intention–action gap.
- **Mechanism:** Delegates initiation to the situation instead of to in-the-
  moment willpower. The decision is pre-made, so there is nothing to negotiate
  with oneself when the moment arrives.
- **App fit: Excellent.** A notification is a synthetic "when X" trigger. The
  app can turn a vague intention ("write the report") into "at 9:15, when the
  chime sounds, open the document and write one sentence."
- **Design constraint:** The trigger must be specific and the action tiny;
  generic reminders ("Don't forget your goals!") do not qualify and perform
  like noise.

### 1.2 Task decomposition to a sub-threshold first action

- **Evidence: Moderate–Strong** (as a component of CBT for procrastination;
  Rozental & Carlbring's work; behavioral activation literature).
- **Mechanism:** Anticipated aversiveness scales with the imagined size of the
  task. A first action small enough ("open the file") slips under the
  resistance threshold; the Ovsiankina/just-get-started effect then does the
  heavy lifting.
- **App fit: Excellent** — this is the behavioral core of "Start Now."
- **Note:** The specific "2 minutes" duration is **Folk** (Allen's two-minute
  rule, Clear's *Atomic Habits*). The validated principle is "smaller than
  resistance," not "120 seconds." Design should treat the duration as a
  tunable parameter, not a law.

### 1.3 Structured micro-commitment (time-boxing / Pomodoro-style sprints)

- **Evidence: Moderate.** Time-boxing per se is under-studied academically,
  but bounded work intervals show consistent benefits in applied studies, and
  boundedness reduces the open-endedness that makes tasks aversive.
- **App fit: Good**, with a caveat from the product constraints: we must not
  become "another Pomodoro clone." The differentiator is that our timer is an
  *ignition device* (get from zero to started), not a *work-cadence manager*
  (25/5 cycles all day).

### 1.4 Reducing friction / adding friction asymmetrically

- **Evidence: Strong** for friction effects generally (defaults and effort
  asymmetries are among the most robust findings in behavioral economics);
  **Moderate and growing** for app-based friction: the *one sec* intervention
  (brief breathing exercise interposed before opening a target app) showed
  large reductions in target-app opens in a published field experiment with
  RCT elements (PNAS, 2023).
- **Mechanism:** Behavior follows the path of least resistance far more than
  it follows values. Make starting cheaper than avoiding.
- **App fit: Excellent** — and note the competitive insight: One Sec proved
  that a *single-moment micro-intervention* can be a product. Ours is the
  mirror image: they add friction to distraction; we remove friction from
  starting.

## 2. Interventions That Change Time Perception

### 2.1 Granular time framing

- **Evidence: Moderate.** Lewis & Oyserman (2015): representing a future event
  in days rather than years made it feel closer and moved planned action
  earlier ("the future begins sooner in days").
- **App fit: Excellent, cheap.** Copy and widget decisions: "16 waking hours
  left this week" beats "it's Wednesday."

### 2.2 Visible depletion / progress representations of time

- **Evidence: Emerging.** Direct studies of "day progress bars" are scarce.
  Adjacent support: goal-gradient effects (effort increases near goal
  completion), scarcity increasing perceived value, and the general finding
  that salient feedback changes behavior. Honest assessment: **our core
  widget concept is plausible but not yet directly validated — this is a
  primary candidate for our own A/B research** (see `OpenQuestions.md`).
- **Risk:** For anxious users, depletion framing ("day is 71% gone") can read
  as threat rather than information. Tone/mode interaction matters; framing
  research (loss vs. opportunity) should inform variants.

### 2.3 Episodic future thinking / future-self connection

- **Evidence: Moderate–Strong** in adjacent domains. Hershfield et al. (2011)
  for saving; episodic future thinking reliably reduces delay discounting in
  lab studies (Peters & Büchel, 2010, and a sizable literature since).
- **App fit: Good but heavier.** Guided "vividly imagine tomorrow-you at
  9 a.m. with this done/not done" prompts are feasible; age-progressed
  avatars etc. are out of MVP scope. Candidate for the Quote Engine's more
  substantive content and for post-MVP features.

### 2.4 Externalized time for time-blind users (spoken time, ambient clocks)

- **Evidence: Emerging/clinical-practice-based.** Externalizing time (visible
  analog timers, auditory time cues) is standard clinical advice in ADHD
  management (Barkley) and is the mechanism behind widely adopted tools like
  Time Timer. Direct RCTs on *spoken* time announcements for procrastination
  are absent — again, a chance to generate our own evidence.
- **App fit: Good in principle;** platform constraints are the real question
  (see `FeatureIdeaAssessment.md` §3).

## 3. Interventions That Repair the Emotional Loop

### 3.1 Self-compassion / self-forgiveness

- **Evidence: Strong direction, moderate volume.** Wohl et al. (2010)
  self-forgiveness study; Sirois (2014) correlational + mediation work;
  self-compassion interventions reduce rumination and improve re-engagement
  after failure across many domains (Neff's research program).
- **App fit: Excellent and differentiating.** Almost no productivity app has
  a designed "lapse recovery" experience. A first-class "you skipped
  everything today → here's the smallest way back in, no accounting, no red
  streak-breaking X" flow is both evidence-based and unique.

### 3.2 Cognitive reframing (CBT techniques)

- **Evidence: Strong** for CBT on procrastination overall — van Eerde &
  Klingsieck's (2018) meta-analysis of intervention studies found CBT-based
  interventions produced the largest reductions in procrastination.
- **App fit: Partial.** Full CBT is a therapy product (and a regulatory
  posture we should avoid). But lightweight, single-thought reframes are
  legitimate content: "You don't need to feel like it. You need 120 seconds."
  The Quote Engine should be seeded with reframes, not just motivation.

### 3.3 Values connection ("why this matters to you")

- **Evidence: Moderate** (self-affirmation and values-affirmation literatures;
  ACT-based procrastination interventions show promise).
- **App fit: Light-touch only for MVP.** One onboarding question ("what are
  you putting off, and what does it cost you?") can personalize urgency
  without building a goals system (which would violate the "not another todo
  app" constraint).

## 4. Interventions With Weak or Negative Evidence (Do Not Build)

| Intervention | Evidence verdict | Why not |
|---|---|---|
| Shame/guilt-based messaging | **Negative** — increases procrastination (Wohl et al., 2010; Sirois & Pychyl, 2013) | Fuels the mood-repair spiral |
| Raw fear appeals without efficacy support | **Negative/backfire** (Witte & Allen, 2000) | Produces defensive avoidance in low-efficacy users — i.e., our users |
| Pure statistics dashboards | **Weak** | Screen Time/Digital Wellbeing show awareness alone ≠ behavior change |
| Streaks as primary motivator | **Mixed, risky** | Motivating until first break, then demotivating cliff; punishes the exact lapse-recovery moment we must protect |
| Punishment/loss-based gamification | **Mixed** | Forest's dead-tree loss aversion works for focus sessions but transfers poorly to *starting*, and adds guilt |
| Generic daily motivational quotes | **Folk, near-zero** | Inspiration without an action affordance decays within minutes; also positions us with low-credibility apps |

The last row matters: the Quote Engine as currently conceived is the weakest
of the six feature ideas *if* it ships generic motivation. It becomes
defensible only as a delivery vehicle for reframes, implementation-intention
prompts, and time-granularity framing. See `FeatureIdeaAssessment.md` §4.

## 5. Synthesis: The Intervention Stack This Product Should Own

Ordered by evidence strength × fit with the product philosophy:

1. **Sub-threshold starting** (implementation intentions + tiny first action
   + immediate timer) — the behavioral core. Strongest evidence, strongest
   differentiation from blockers and task managers.
2. **Ambient time perception** (granular framing, visible day depletion,
   optional spoken time) — the identity of the product. Moderate/emerging
   evidence; we should instrument it and generate evidence.
3. **Compassionate lapse recovery** — evidence-based, almost uncontested in
   the market, and the ethical backbone that makes the whole product safe.
4. **Tone-adaptive reframing content** (the evolved Quote Engine) — support
   layer for 1–3, not a standalone feature.

Everything in the MVP should be traceable to one of these four.

## 6. Sources

See `ProcrastinationScience.md` §7 for the shared bibliography; additional to
that list:

- Rozental, A., & Carlbring, P. — research program on internet-delivered CBT for procrastination.
- Peters, J., & Büchel, C. (2010). Episodic future thinking reduces delay discounting. *Neuron.*
- Neff, K. — self-compassion research program.
- Grüning et al. (2023). Directing smartphone use through the self-nudge app *one sec*. *PNAS.*
- Barkley, R. — time perception and self-regulation deficits in ADHD.

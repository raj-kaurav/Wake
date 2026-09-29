# Market Gaps

**Phase:** 0 — Discovery & Research
**Status:** Draft for review
**Purpose:** Name the specific unmet needs identified by the science review and
the competitive review, and state which we should target.

---

## Gap 1 — No product intervenes at the moment of starting

Blockers act before *distraction*. Task managers act at *planning*. Timers act
*during* work. **Nothing in the mainstream market acts at the instant a person
faces a task and can't begin** — the single point where, per the evidence
(implementation intentions, just-get-started effect), leverage is highest.

- Evidence of demand: "how to start when you can't" is perennial top content
  in ADHD/productivity communities; "body doubling" services (Focusmate,
  ADHD body-doubling streams) exist purely to solve task initiation, but via
  scheduled human sessions — heavyweight and socially demanding.
- **Verdict: primary gap. This is the product's core.**

## Gap 2 — Time awareness exists only as data, never as feeling

Screen Time and Digital Wellbeing present time as *accounting after the
fact*. Clock and calendar widgets present time as *coordinates*. Time Timer
(the closest thing to "felt time") is a physical-first product for a
specialist audience and carries no behavioral layer.

**No mainstream mobile product renders the passage of the present day as an
ambient, emotional, glanceable experience tied to action.** The popularity of
Structured's timeline and of "year progress" novelty bots/accounts shows
latent demand for time-as-shape.

- **Verdict: primary gap; it is also our identity and the hardest to copy
  credibly** (a task-manager incumbent adding a progress bar still carries
  its guilt ledger).

## Gap 3 — Tone is one-size-fits-all

Finch proves gentle wins a large audience; "tough love" alarm apps and
drill-sergeant fitness apps prove a directness niche exists. **No significant
product lets the user choose the emotional register of the entire experience**
(copy, notifications, visuals) at onboarding. Personalization today means
themes and icon packs, not voice.

- **Verdict: strong differentiator gap — with the ethical guardrails in
  `EthicalConsiderations.md` as a hard precondition.**

## Gap 4 — Lapse recovery is designed by nobody

Every retention mechanic in the market (streaks, pets, trees, scores) makes
returning after a lapse *worse* than never leaving. The evidence
(self-forgiveness, abstinence-violation effect) says the lapse moment is the
highest-value intervention point for chronic procrastinators.

**No competitor has a designed "welcome back, zero judgment, here's the
smallest way in" experience.**

- **Verdict: high-value gap, cheap to serve, ethically aligned; adopt as a
  core design principle rather than a marketed feature.**

## Gap 5 — Auditory time externalization on mobile

Spoken-time exists as an accessibility niche (VoiceOver/TalkBack, "Speaking
Clock" utilities) and in watchOS Taptic Time, but never as a *behavioral*
feature integrated with action prompts. Clinical ADHD practice endorses
auditory time cues; the market ignores them.

- **Verdict: genuine gap, but gated on hard platform constraints
  (background execution, battery) — see `FeatureIdeaAssessment.md` §3.
  Treat as differentiating-if-feasible, not as a foundation.**

## Gaps We Should NOT Chase

| Tempting gap | Why we decline |
|---|---|
| "Smarter" task management (AI prioritization etc.) | Re-enters the todo category against incumbents; violates product constraints |
| Screen-time analytics with better charts | Awareness-without-action failure mode; Apple/Google own the data and the surface |
| Social accountability network | Heavy moderation/network-effect burden; conflicts with low-friction philosophy; Focusmate already owns the niche |
| Full ADHD clinical tool | Regulatory posture, clinical validation burden; we design *informed by* ADHD needs without medical claims |
| General mental-health/CBT therapy app | Crowded (Woebot etc.), regulated, and beyond our scope; we borrow single techniques only |

## Synthesis

The defensible position: **the only app that lives in the moment between
"I should" and "I am"** — rendering time as something felt (Gap 2), in a
voice the user chose (Gap 3), with one button that makes starting smaller
than resisting (Gap 1), and a shame-free way back after every lapse (Gap 4).

Each gap alone is copyable; the combination — plus a strict "no lists, no
ledger, no lecture" scope discipline — is a coherent product identity that
incumbents would have to break their own engagement models to imitate
(see `WhyProductivityAppsFail.md` F5).

# Phase 0 — Discovery & Research: Overview

**Status:** Complete — awaiting product-owner review and approval.
**Gate:** No Phase 1 (Product Documentation) work begins until this phase is
approved. See `docs/README.md` for the full phase-gate process.

This phase answers the questions posed in the project brief's Phase 0
mandate: what procrastination actually is, which interventions have
evidence, why existing apps fail, where the market gaps are, whether our
vision is differentiated enough, and what the ethical hazards are.

---

## Documents in This Phase

| Document | Answers |
|---|---|
| [`ProcrastinationScience.md`](ProcrastinationScience.md) | What is procrastination, behaviorally? Which mechanisms can a product act on? |
| [`EvidenceBasedInterventions.md`](EvidenceBasedInterventions.md) | Which interventions have empirical support, how strong, and do they fit a mobile app? |
| [`WhyProductivityAppsFail.md`](WhyProductivityAppsFail.md) | The eight systematic failure modes of existing tools, each converted into a design law for us |
| [`CompetitiveLandscape.md`](CompetitiveLandscape.md) | App-by-app review: Forest, One Sec, Opal, Freedom, Finch, Todoist, TickTick, Structured, Be Focused, quote apps, adjacent inspirations |
| [`MarketGaps.md`](MarketGaps.md) | The five real gaps, and the five tempting gaps we decline |
| [`FeatureIdeaAssessment.md`](FeatureIdeaAssessment.md) | Evidence-based critique of the six proposed features: impact, complexity, accessibility, ethics, battery, privacy, priority |
| [`EthicalConsiderations.md`](EthicalConsiderations.md) | The manipulation/persuasion line, the full "Brutal mode" analysis, and eight standing ethical commitments |
| [`ProductOpportunityReport.md`](ProductOpportunityReport.md) | **The go/no-go recommendation and differentiation verdict** — read this first if short on time |
| [`OpenQuestions.md`](OpenQuestions.md) | Fifteen falsifiable open questions and five conscious assumptions, each with a validation method |

## Key Findings (one paragraph each)

**1. The vision is scientifically sound — with one correction.** The brief's
insight ("people don't feel the cost of waiting") maps onto Temporal
Motivation Theory (future rewards are discounted). But the complementary
mechanism is equally important: procrastination is short-term *mood repair* —
avoidance feels good now. So the product must both make time felt **and**
make starting feel smaller, and it must never add shame, because shame
demonstrably increases procrastination.

**2. "Brutally Honest" mode must be reframed.** The strongest finding in the
literature (self-forgiveness and self-compassion reduce procrastination;
guilt increases it) is directly against a literal brutal mode — which would
also concentrate harm on the most vulnerable users, who are drawn to
self-punishment. We recommend keeping the two-voice architecture but
redefining the pole as **Direct** (a straight-talking coach: targets the
behavior and the moment, never the person or the past) under a binding
content contract. This is the single most important challenge Phase 0 raises
against the brief.

**3. The market quadrant is empty.** Blockers (Forest, One Sec, Opal,
Freedom) act on avoidance; task managers (Todoist, TickTick, Structured) act
on planning; quote apps decorate. **No mainstream product intervenes at the
moment of starting, and none renders time as a felt, ambient experience.**
Finch proves the emotional-design market; One Sec proves single-moment
micro-interventions work (published field evidence); Structured proves
demand for seeing the day as a shape. Nobody combines them.

**4. Recommended MVP shape.** Widget (feel time) → Start Now (two-minute
ignition; strongest evidence of all six ideas) → tone-aware content system
(the evolved Quote Engine — demoted from feature to infrastructure; generic
quotes rejected) → Speak Time (full on Android; notification-sound
approximation on iOS due to hard background-execution limits; feasibility
spike required). Everything else — including Death Clock and regret
simulation, both flagged as backfire risks — stays out.

**5. The durable moat is philosophical, not technical.** The MVP is
technically simple and copyable feature-by-feature. What incumbents cannot
copy without dismantling their own engagement economics is the stance: no
lists, no failure ledger, no attention optimization — success measured by
the user *leaving* the app to act. This stance must be codified as binding
principles in Phase 1 and enforced by the Phase 6 development rules.

## Verdict

**GO**, conditional on: (1) Direct-not-Brutal reframe, (2) radical scope
discipline ("no lists, no ledger, no lecture"), (3) action-not-attention
metrics adopted from day one. Full argument in
[`ProductOpportunityReport.md`](ProductOpportunityReport.md).

## Decisions Requested from the Product Owner

To close this gate, please approve, amend, or reject each of the following:

1. **Approve the Direct-not-Brutal reframe** (or direct us to the Gentle-only
   fallback; we advise against literal Brutal).
2. **Approve the recommended MVP shape** (§4 above) as the starting point for
   Phase 1's `MVPDefinition.md`.
3. **Ratify the eight standing ethical commitments**
   (`EthicalConsiderations.md` §6) as binding on all later phases.
4. **Confirm the parked/rejected list** for Feature 6 ideas
   (`FeatureIdeaAssessment.md` §6), notably the rejection of regret
   simulation and the research-only status of mortality features.
5. **Acknowledge the platform reality** that Speak Time and widget fidelity
   will differ between Android and iOS (tiered design accepted upfront).

Upon approval, Phase 1 begins with `docs/product/` per the brief, importing
this phase's outputs as its foundation.

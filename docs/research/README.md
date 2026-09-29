# Phase 0 — Discovery & Research: Overview

**Status:** ✅ Approved with revisions (revisions applied — see changelog below).
**Gate:** Closed. Phase 1 (Product Documentation) is in progress per the
product owner's approval. See `docs/README.md` for the full phase-gate
process.

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
| [`HabitFormation.md`](HabitFormation.md) | How does starting become automatic; what do streaks and misses really do? *(added in revision)* |
| [`BehavioralEconomics.md`](BehavioralEconomics.md) | Present bias, fresh starts, framing, defaults, commitment devices — each with a design consequence *(added in revision)* |
| [`NotificationPsychology.md`](NotificationPsychology.md) | Interruption science, receptivity, habituation, permission psychology; the constraints for our notification strategy *(added in revision)* |
| [`MicrocopyStrategy.md`](MicrocopyStrategy.md) | The research basis for how Wake speaks; the two-voice system and tone matrix *(added in revision)* |
| [`ExecutiveFunctionADHD.md`](ExecutiveFunctionADHD.md) | Executive function, time blindness, and the ADHD-informed design checklist; the medical boundary *(added in revision)* |
| [`WhyProductivityAppsFail.md`](WhyProductivityAppsFail.md) | The eight systematic failure modes of existing tools, each converted into a design law for us |
| [`CompetitiveLandscape.md`](CompetitiveLandscape.md) | App-by-app review: Forest, One Sec, Opal, Freedom, Finch, Todoist, TickTick, Structured, Be Focused, quote apps, adjacent inspirations |
| [`MarketGaps.md`](MarketGaps.md) | The five real gaps, and the five tempting gaps we decline |
| [`FeatureIdeaAssessment.md`](FeatureIdeaAssessment.md) | Evidence-based critique of the six proposed features: impact, complexity, accessibility, ethics, battery, privacy, priority |
| [`ToneNamingExploration.md`](ToneNamingExploration.md) | Alternatives to the "Direct" label with UX rationale; the "Voices" recommendation *(added in revision)* |
| [`EthicalConsiderations.md`](EthicalConsiderations.md) | The manipulation/persuasion line, the challenging-voice analysis, and eight standing ethical commitments |
| [`ProductOpportunityReport.md`](ProductOpportunityReport.md) | **The go/no-go recommendation and differentiation verdict** — read this first if short on time |
| [`OpenQuestions.md`](OpenQuestions.md) | Fifteen falsifiable open questions and five conscious assumptions, each with a validation method |

## Key Findings (one paragraph each)

**1. The vision is scientifically sound — and rests on two pillars.** The
brief's insight ("people don't feel the cost of waiting") maps onto Temporal
Motivation Theory (future rewards are discounted). The complementary
mechanism is equally important: procrastination is short-term *mood repair* —
avoidance feels good now. The product philosophy therefore has two explicit
pillars: **make time felt** and **make starting smaller** — and it must
never add shame, because shame demonstrably increases procrastination.

**2. The challenging voice keeps its contract; its name is an open set.**
The strongest finding in the literature (self-forgiveness and
self-compassion reduce procrastination; guilt increases it) rules out a
literal brutal mode. The two-voice architecture stands, bound by the
behavioral contract (challenge the behavior and the moment, never the person
or the past). Label alternatives are explored in `ToneNamingExploration.md`,
with a provisional recommendation to frame the system as **Voices** — "The
Coach" and "The Friend" — extensible to future voices such as the optional
"Stoic" philosophy pack.

**3. The market quadrant is empty, and we claim it as a category.** Blockers
(Forest, One Sec, Opal, Freedom) act on avoidance; task managers (Todoist,
TickTick, Structured) act on planning; quote apps decorate. No mainstream
product intervenes at the moment of starting, and none renders time as a
felt, ambient experience. Wake positions as a **time awareness product** — a
category of its own — with anti-procrastination as the outcome, not the
label.

**4. Recommended MVP shape.** Widget (feel time) → Start Now (two-minute
ignition; strongest evidence of all six ideas) → **Content Engine** (the
reframed Quote Engine: a voice-aware content system in which quotes are one
content type among five) → Speak Time (full on Android; notification-sound
approximation on iOS due to hard background-execution limits; feasibility
spike required). Death Clock/Memento Mori is recast as an **optional
philosophy pack, disabled by default**, post-MVP, with hard ethics
guardrails; regret simulation remains rejected.

**5. The durable moat is philosophical, not technical.** The MVP is
technically simple and copyable feature-by-feature. What incumbents cannot
copy without dismantling their own engagement economics is the stance: no
lists, no failure ledger, no attention optimization — success measured by
the user *leaving* the app to act. This stance is codified as the project
constitution in `../product/ProductPrinciples.md` and will be enforced by
the Phase 6 development rules.

## Verdict

**GO** — approved by the product owner with revisions, under three binding
conditions now reflected throughout: (1) the challenging-voice contract
(never the person, never the past), (2) radical scope discipline ("no lists,
no ledger, no lecture"), (3) action-not-attention metrics from day one.
Full argument in [`ProductOpportunityReport.md`](ProductOpportunityReport.md).

## Revision Changelog (Phase 0 review, revision 1)

Product-owner feedback and how it was incorporated:

1. **Explore alternatives to "Direct"** → `ToneNamingExploration.md` added;
   provisional recommendation: "Voices" system (The Coach / The Friend);
   final name to be ratified with Phase 1.
2. **Philosophy includes both pillars** → canonical statement updated
   everywhere to *"Make time felt. Make starting small."* (long form: make
   time felt, not tracked — and make starting smaller than resisting).
3. **Quote Engine → Content Engine** → reframed across all documents;
   quotes are one of five content types.
4. **Death Clock / Memento Mori as optional philosophy pack** → recast as
   "The Stoic" pack, disabled by default, post-MVP, ethics guardrails
   binding (`EthicalConsiderations.md` §4.2, `FeatureIdeaAssessment.md` §6).
5. **Added research** → `HabitFormation.md`, `BehavioralEconomics.md`,
   `NotificationPsychology.md`, `MicrocopyStrategy.md`,
   `ExecutiveFunctionADHD.md`.
6. **Permanent product constitution** → `../product/ProductPrinciples.md`
   created as the first Phase 1 document.
7. **Position as a Time Awareness product** → positioning updated across
   documents; category language adopted.

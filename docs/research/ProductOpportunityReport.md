# Product Opportunity Report

**Phase:** 0 — Discovery & Research
**Status:** Draft for review
**Purpose:** Synthesize the Phase 0 research into a single recommendation:
is this product worth building, is the vision differentiated enough, and
under what conditions? This is the document to read if you read only one.

---

## 1. Executive Summary

**Recommendation: GO — with three binding conditions.**

The vision ("make time felt, not tracked") targets a real, evidence-backed
mechanism gap that no mainstream product occupies. The core loop implied by
the feature ideas — ambient time awareness feeding a friction-free start
action, delivered in a user-chosen voice — sits in an empty quadrant of the
market (emotionally designed, approach-side interventions; see
`CompetitiveLandscape.md` positioning map) and rests on interventions with
strong-to-moderate scientific support (`EvidenceBasedInterventions.md`).

The three conditions:

1. **Reframe "Brutally Honest" as "Direct" with a binding content contract.**
   Literal brutality contradicts the strongest finding in the field (shame
   increases procrastination) and concentrates harm on the most vulnerable
   users. Full analysis in `EthicalConsiderations.md` §3.
2. **Enforce radical scope discipline: no lists, no ledger, no lecture.**
   The product stores at most one current intention, never displays failure
   history, and never becomes a content feed. Every failure mode documented
   in `WhyProductivityAppsFail.md` begins with a "helpful" scope addition.
3. **Adopt action-not-attention metrics from day one.** North-star: starts
   per user-day (and starts that lead the user *out* of the app). Session
   length is a guardrail metric to keep *low*, not a KPI. This choice is
   what keeps the ethics durable under commercial pressure.

## 2. Is the Vision Differentiated Enough? (the question the brief asked)

**Yes — as a combination, not as any single feature.** Honest breakdown:

| Element | Alone, is it defensible? | In combination |
|---|---|---|
| Time-awareness widget | No — a progress bar is copyable in a sprint | Identity anchor; incumbents copying it still carry their guilt ledgers and task piles |
| Start Now button | No — "it's just a timer" | Owns the unserved moment (Gap 1); paired with the widget it forms a loop no one else has |
| Tone modes | Partially — novel at experience level | Doubles the felt personalization of everything else; hard to retrofit into an existing brand voice |
| Compassionate lapse recovery | Yes, quietly | No competitor can adopt it without dismantling streak/pet economics |
| Anti-engagement stance | Yes | A structural moat: incumbents' business models depend on the engagement loops we refuse |

The durable differentiation is **positional and philosophical**: a product
whose success metric is the user leaving it to act cannot be imitated by
engagement-funded incumbents without self-harm, and cannot be credibly
imitated by quote-app opportunists because the value is in restraint and
execution quality, not in feature count.

**Differentiation risks stated honestly:**

- *Low technical moat.* The MVP is technically simple. Speed to a
  well-executed v1, brand voice, and content quality are the defenses; we
  should expect fast followers if the concept demonstrates traction.
- *Category ambiguity.* "What is it — a clock? a timer? a quotes app?" is a
  real marketing problem. The store listing must sell the *moment* ("for
  when you can't start"), not the mechanics. Naming/positioning work in
  Phase 1 must treat this as a top-three problem.
- *Evidence gap on the identity feature.* The widget's mechanic is plausible
  but not directly validated (`EvidenceBasedInterventions.md` §2.2). We
  mitigate by instrumenting it and being ready to iterate the representation,
  not the thesis.

## 3. The Opportunity, Stated Precisely

**For** ambitious people who know exactly what they should be doing and
cannot make themselves begin,
**who are failed by** task managers (organize the guilt), blockers (block the
escape but not the wall), and motivational apps (decorate the avoidance),
**this product** makes the passage of today perceptible and makes starting a
two-minute act smaller than the resistance to it,
**in a voice the user chose**, with zero setup, zero record of failure, and
zero interest in keeping them in the app.

Target segments (from the brief, ranked by fit): students under deadline
regimes and knowledge workers/creators with self-directed work are primary
(highest pain frequency, proven willingness to try tools); entrepreneurs and
the ADHD-adjacent community are high-affinity early-adopter channels (with
the no-medical-claims boundary from `EthicalConsiderations.md` §4.3).

## 4. What Phase 0 Says the MVP Should Be

Handed to Phase 1 as a strong recommendation, not a fait accompli
(full reasoning in `FeatureIdeaAssessment.md`):

1. **Time Awareness Widget** — day-as-shape, granularity-framed; the identity.
2. **Start Now** — the behavioral core; the button the whole product serves.
3. **Tone system (Direct/Gentle)** — architecture from day one; content
   system (evolved Quote Engine) as its delivery mechanism, including
   designed lapse recovery.
4. **Speak Time** — Android-first full version; iOS notification-sound
   approximation; feasibility spike before final commitment.

Explicitly out of MVP (park in Phase 1 `OutOfScope.md`): everything in
Feature 6, calendar integration, any statistics surface, any social feature,
any AI feature, task storage beyond one intention string.

## 5. Principal Risks (register to be formalized in Phase 1 `Risks.md`)

| # | Risk | Severity | Mitigation direction |
|---|---|---|---|
| R1 | Habituation: widget becomes wallpaper, spoken time becomes noise | High | Variation in rendering/content; instrument decay curves; treat as a core design research question, not polish |
| R2 | Novelty churn: app is liked, praised, and abandoned in week 3 | High | The Start Now loop must produce felt wins in week 1; lapse-recovery design; low-motivation-state usability target |
| R3 | Category confusion in marketing | Medium-High | Position around the moment of starting; never lead with "timer/quotes/clock" |
| R4 | Direct mode executed badly → brand damage & user harm | Medium-High | Content contract + review checklist (`EthicalConsiderations.md` §3, §5); small reviewed corpus at launch |
| R5 | iOS platform ceiling degrades Speak Time & widget fidelity | Medium | Tiered design accepted upfront; feasibility spikes in Phase 3; honest cross-platform messaging |
| R6 | Fast followers | Medium | Speed, voice, execution quality; accept low technical moat consciously |
| R7 | Mechanism risk: felt time doesn't move behavior for enough users | Medium | The bet is explicit; instrument widget→start conversion; Start Now works even if the widget only decorates |
| R8 | Team scope drift back toward todo/tracker patterns | Medium | Constraints codified in Phase 1 and enforced via Phase 6 development rules |

## 6. What Would Change This Recommendation

- Evidence from Phase 1 user research that target users read ambient time
  cues predominantly as anxiety rather than activation (would force a
  redesign of the awareness layer around opportunity-framing, or a pivot to
  Start-Now-first identity).
- Discovery of a well-executed incumbent in the same quadrant (none found as
  of this review).
- A product-owner decision to keep literal "Brutal" mode — this would flip
  the ethics assessment and our recommendation to Gentle-only at launch.

## 7. Immediate Next Steps (upon Phase 0 approval)

1. Phase 1 kickoff: draft `docs/product/` per the brief's list, importing
   this report's MVP recommendation, risk register seed, and the standing
   ethical commitments (`EthicalConsiderations.md` §6) for ratification.
2. Carry `OpenQuestions.md` hypotheses into Phase 1
   `UserResearchHypothesis.md` with a validation plan.
3. Schedule the two Phase 3 feasibility spikes now flagged (iOS widget
   fidelity; Speak Time background execution) so architecture work isn't
   blocked later.

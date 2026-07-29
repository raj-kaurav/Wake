# Open Questions & Assumptions to Validate

**Phase:** 0 — Discovery & Research
**Status:** Draft for review
**Purpose:** Honest register of what we do *not* yet know. Each item is
phrased as a falsifiable hypothesis where possible, with the cheapest
credible validation method. Feeds Phase 1 `UserResearchHypothesis.md`.

---

## A. Core Mechanism Questions

**Q1. Does ambient time visualization actually increase starting behavior?**
The widget's mechanic is plausible (TMT, granularity effects) but not
directly validated. *Hypothesis:* users with the widget installed initiate
more Start Now sessions per day than users without it. *Validation:* built-in
A/B instrumentation post-launch; before that, 1-week diary study with a
Figma-widget lookalike or a lightweight test widget.

**Q2. Depletion framing vs. opportunity framing — which activates, which
threatens, and for whom?** *Hypothesis:* opportunity framing ("6h left")
outperforms depletion ("71% gone") for high-anxiety users, with no penalty
for others. *Validation:* copy/visual variant testing in prototype
interviews; instrumented variant test later.

**Q3. Is two minutes the right default for Start Now?** The number is folk
wisdom. *Hypothesis:* defaults in the 2–5 min range don't materially change
start rates, but do change continue-after-timer rates. *Validation:*
instrument duration as a remote-config parameter from v1.

**Q4. What happens at the end of the timer matters more than the timer — but
what exactly should happen?* *Validation:* prototype the three end-states
(`FeatureIdeaAssessment.md` §5) in moderated tests; watch for the
bait-and-switch trust failure specifically.

**Q5. Does spoken time interrupt absorption in practice, or does it
habituate into silence within days?** *Hypothesis:* awareness effect persists
≥2 weeks at 30/60-min intervals but decays at 15-min. *Validation:*
2-week self-report + usage study during beta; decay curves from settings
changes.

## B. Audience Questions

**Q6. Mode selection distribution:** what share of the target audience
actually picks Direct over Gentle, and does the choice correlate with the
shame-spiral profile we are worried about? *Validation:* onboarding analytics
+ optional 1-question well-being pulse in beta; interview Direct-choosers.

**Q7. Do users experience the product as calming or as pressuring after a
week?** This is the emotional-register bet underneath everything.
*Validation:* week-1 in-app single-question pulse + exit interviews with
churned beta users (churned users are the key sample).

**Q8. Which segment converts best** (students / developers / creators /
entrepreneurs), and does the ADHD-adjacent channel adopt organically without
medical positioning? *Validation:* beta cohort tagging; community soft
launches.

## C. Platform & Technical Questions (spikes flagged for Phase 3)

**Q9. iOS widget fidelity:** can `Text(.timer)`-style continuous rendering +
coarse timeline entries deliver a day-progress visual that feels alive within
WidgetKit refresh budgets? *Validation:* 1–2 day spike; decides the widget's
visual grammar.

**Q10. Speak Time on iOS via notification sounds:** do pre-rendered
"It's HH:MM" notification sounds feel acceptable or cheap? Do Focus modes
swallow them in practice? *Validation:* spike + hallway test on real devices.

**Q11. Android reliability across OEMs:** do exact alarms + TTS survive
Samsung/Xiaomi battery management at 30–60 min intervals overnight?
*Validation:* device-lab spike; informs whether foreground service is
required (and its notification cost).

**Q12. Framework choice consequences:** given that widgets and background
audio are largely native on both platforms regardless, what does that imply
for Flutter/RN/KMP/native choice? *Deferred to Phase 3 with this constraint
recorded.*

## D. Product & Business Questions (for Phase 1, not blocking)

**Q13. Name and category framing** — how do we describe this in seven words
without saying timer, todo, or quotes? (Top-three marketing problem per
`ProductOpportunityReport.md` §2.)

**Q14. Monetization model** — one-time (Forest precedent) vs. subscription
(Opal/Finch precedent), constrained by the ethics floor in
`EthicalConsiderations.md` §4.5. No position taken in Phase 0 beyond the
constraints.

**Q15. Does the single "current intention" field add value or reintroduce
todo-app gravity?** *Hypothesis:* optional intention text increases start
completion but its absence must never block the button. *Validation:*
prototype tests; instrument as optional from v1.

## E. Assumptions We Are Consciously Making

Recorded so they can be challenged in review:

1. The target user already knows what task matters (we do not help choose).
2. A meaningful share of procrastination episodes happen within reach of the
   phone's home screen (the widget's delivery assumption).
3. Users will grant notification permission when the value is framed at the
   right moment (no cold permission walls).
4. Two authored tones are enough at launch (no third "neutral" mode) — to be
   sanity-checked in Phase 1 research.
5. English-only content at launch is acceptable; the tone-doubling cost of
   localization is deferred (flagged for Phase 3 `Localization.md`).

# Wake — Documentation

> **Product philosophy:** Make time felt. Make starting small.

Wake is a **time awareness app**: it makes today feel finite and starting
feel two minutes small. It is deliberately not positioned as a productivity,
todo, or anti-procrastination app — anti-procrastination is the outcome, not
the category.

This repository follows a phase-gated, documentation-first product
development lifecycle. **No production code is written until the relevant
documentation has been reviewed and approved by the product owner.**

## Phase Gate Status

| Phase | Scope | Directory | Status |
|-------|-------|-----------|--------|
| **Phase 0** | Discovery & Research | `docs/research/` | ✅ Approved with revisions (revisions applied) |
| **Phase 1** | Product Documentation | `docs/product/` | ✅ Complete — **awaiting approval** |
| Phase 2 | UX Documentation | `docs/ux/` | ⛔ Blocked on Phase 1 approval |
| Phase 3 | Technical Planning | `docs/architecture/` | ⛔ Blocked |
| Phase 4 | Engineering Standards | `docs/engineering/` | ⛔ Blocked |
| Phase 5 | Design System | `docs/design-system/` | ⛔ Blocked |
| Phase 6 | Development Rules | `.cursor/` | ⛔ Blocked |
| Phase 7 | Implementation Plan | `docs/plan/` | ⛔ Blocked |
| Phase 8 | Implementation | `app/` (TBD) | ⛔ Blocked |

### Gate rules

1. Each phase ends with a review. Work on the next phase does not start until
   the product owner approves the current one.
2. Feedback is incorporated by revising the documents in place; revisions are
   noted in each phase's changelog (see `research/README.md` for Phase 0's).
3. Decisions made in an approved phase are binding on later phases. Changing
   an approved decision requires reopening the earlier document, not silently
   diverging.
4. `product/ProductPrinciples.md` is the project constitution: permanent,
   binding on every phase, amendable only by explicit product-owner decision.

## Phase 1 Reading Order (current review)

1. [`product/ProductPrinciples.md`](product/ProductPrinciples.md) — **the constitution**: two pillars, thirteen principles
2. [`product/Vision.md`](product/Vision.md) — the world we want; the time-awareness category
3. [`product/Mission.md`](product/Mission.md) — what we do and how we work
4. [`product/ProblemStatement.md`](product/ProblemStatement.md) — the problem, restated as design requirements
5. [`product/TargetAudience.md`](product/TargetAudience.md) — segments, priorities, non-audience
6. [`product/Personas.md`](product/Personas.md) — Maya, Daniel, Priya, Tomás — and the constraints they enforce
7. [`product/BehavioralPsychology.md`](product/BehavioralPsychology.md) — the applied model behind every surface
8. [`product/ProductGoals.md`](product/ProductGoals.md) — goal hierarchy with pre-decided conflicts
9. [`product/MVPDefinition.md`](product/MVPDefinition.md) — **the binding MVP scope contract**
10. [`product/OutOfScope.md`](product/OutOfScope.md) — three exclusion tiers + scope-creep tripwires
11. [`product/FeatureRoadmap.md`](product/FeatureRoadmap.md) — horizons with evidence gates, not dates
12. [`product/CompetitiveAnalysis.md`](product/CompetitiveAnalysis.md) — positioning, defense, watchlist
13. [`product/UserResearchHypothesis.md`](product/UserResearchHypothesis.md) — 15 hypotheses, 4 research waves
14. [`product/Risks.md`](product/Risks.md) — 11 product risks with signals and owners
15. [`product/SuccessMetrics.md`](product/SuccessMetrics.md) — action-not-attention measurement contract

## Phase 0 (approved)

Start at [`research/README.md`](research/README.md) — overview, key
findings, and the revision changelog. The single best summary document is
[`research/ProductOpportunityReport.md`](research/ProductOpportunityReport.md).

## A Note on Evidence

The research documents cite published behavioral-science literature by author
and year. Citations reflect the research team's working knowledge of the
literature; before any claim is used in marketing copy or app content, it must
be verified against the primary source. Claims that are contested or based on
weaker evidence are explicitly flagged as such in the documents.

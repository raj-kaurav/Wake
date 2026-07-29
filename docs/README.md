# Anti-Procrastination App — Documentation

> **Product philosophy:** Make time felt, not tracked.

This repository follows a phase-gated, documentation-first product development
lifecycle. **No production code is written until the relevant documentation has
been reviewed and approved by the product owner.**

## Phase Gate Status

| Phase | Scope | Directory | Status |
|-------|-------|-----------|--------|
| **Phase 0** | Discovery & Research | `docs/research/` | ✅ Complete — **awaiting approval** |
| Phase 1 | Product Documentation | `docs/product/` | ⛔ Blocked on Phase 0 approval |
| Phase 2 | UX Documentation | `docs/ux/` | ⛔ Blocked |
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
   noted in each document's changelog section where material.
3. Decisions made in an approved phase are binding on later phases. Changing an
   approved decision requires reopening the earlier document, not silently
   diverging.

## Phase 0 Reading Order

Start with the research overview, which summarizes the findings and the
decisions we recommend:

1. [`research/README.md`](research/README.md) — overview, key findings, recommendations
2. [`research/ProcrastinationScience.md`](research/ProcrastinationScience.md) — what procrastination actually is
3. [`research/EvidenceBasedInterventions.md`](research/EvidenceBasedInterventions.md) — what demonstrably helps
4. [`research/WhyProductivityAppsFail.md`](research/WhyProductivityAppsFail.md) — failure modes of existing tools
5. [`research/CompetitiveLandscape.md`](research/CompetitiveLandscape.md) — app-by-app review
6. [`research/MarketGaps.md`](research/MarketGaps.md) — where the openings are
7. [`research/FeatureIdeaAssessment.md`](research/FeatureIdeaAssessment.md) — evidence-based critique of the six proposed features
8. [`research/EthicalConsiderations.md`](research/EthicalConsiderations.md) — ethics, incl. the "Brutal mode" problem
9. [`research/ProductOpportunityReport.md`](research/ProductOpportunityReport.md) — the go/no-go recommendation
10. [`research/OpenQuestions.md`](research/OpenQuestions.md) — assumptions that still need validation

## A Note on Evidence

The research documents cite published behavioral-science literature by author
and year. Citations reflect the research team's working knowledge of the
literature; before any claim is used in marketing copy or app content, it must
be verified against the primary source. Claims that are contested or based on
weaker evidence are explicitly flagged as such in the documents.

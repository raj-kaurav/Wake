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
| **Phase 1** | Product Documentation | `docs/product/` | ✅ Approved |
| **Phase 2** | UX Documentation | `docs/ux/` | ✅ Complete — **awaiting approval** |
| Phase 3 | Technical Planning | `docs/architecture/` | ⛔ Blocked on Phase 2 approval |
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

## Phase 2 Reading Order (current review)

Foundations first, then surfaces, then the lifetime view:

1. [`ux/DesignPrinciples.md`](ux/DesignPrinciples.md) — twelve UX principles implementing the constitution
2. [`ux/BehaviorChangeModel.md`](ux/BehaviorChangeModel.md) — **the formalized Wake Loop** every UX decision maps to *(added per review)*
3. [`ux/InformationArchitecture.md`](ux/InformationArchitecture.md) — surfaces, six screens, object model, illegal states
4. [`ux/Navigation.md`](ux/Navigation.md) — the deliberately trivial navigation model
5. [`ux/UserFlows.md`](ux/UserFlows.md) — ten canonical flows with budgets and edge cases
6. [`ux/Onboarding.md`](ux/Onboarding.md) — five decisions, sixty seconds, zero permissions
7. [`ux/Widgets.md`](ux/Widgets.md) — concept exploration; **"Day Dots" recommended** (decision requested)
8. [`ux/NotificationStrategy.md`](ux/NotificationStrategy.md) — the exhaustive notification inventory + respectful-silence spec
9. [`ux/ContentSystem.md`](ux/ContentSystem.md) — **the structured behavioral content system** (expanded per review)
10. [`ux/Microcopy.md`](ux/Microcopy.md) — voice contracts, terminology law, edge-state copy
11. [`ux/Accessibility.md`](ux/Accessibility.md) — the multi-sensory time contract; launch requirements
12. [`ux/EmotionalDesign.md`](ux/EmotionalDesign.md) — per-moment emotional specification
13. [`ux/BehavioralDesign.md`](ux/BehavioralDesign.md) — friction budgets, defaults, anti-habituation, graduation design
14. [`ux/EmotionalJourney.md`](ux/EmotionalJourney.md) — install → autonomy progression *(added per review)*
15. [`ux/UserSuccessDefinition.md`](ux/UserSuccessDefinition.md) — success from the user's side *(added per review)*
16. [`ux/AntiGoals.md`](ux/AntiGoals.md) — eight outcomes we must not cause *(added per review)*
17. [`ux/WireframeDescriptions.md`](ux/WireframeDescriptions.md) — textual wireframes for every screen and surface
18. [`ux/FutureUXIdeas.md`](ux/FutureUXIdeas.md) — the parking lot

Voice naming continues in parallel (round 2:
[`research/ToneNamingExploration.md`](research/ToneNamingExploration.md) §5)
without blocking UX work; final label ratification deadline is end of
Phase 5.

## Phase 1 (approved)

Start at [`product/ProductPrinciples.md`](product/ProductPrinciples.md)
(the constitution), then [`product/MVPDefinition.md`](product/MVPDefinition.md)
(the binding scope contract). Full set in `docs/product/`.

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

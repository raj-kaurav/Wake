# Wake — Documentation

> **Product philosophy:** Make time felt. Make starting small.

Wake is a **time awareness app**. Canonical terminology:
[`product/LanguageSystem.md`](product/LanguageSystem.md). Decision history:
[`product/ProductDecisionLog.md`](product/ProductDecisionLog.md).

## Phase Gate Status

| Phase | Scope | Directory | Status |
|-------|-------|-----------|--------|
| **Phase 0** | Discovery & Research | `docs/research/` | ✅ Approved (frozen) |
| **Phase 1** | Product Documentation | `docs/product/` | ✅ Approved (frozen) |
| **Phase 2** | UX Documentation | `docs/ux/` | ✅ Approved (frozen) |
| **Phase 3** | Technical Planning | `docs/architecture/` | ✅ Complete — **awaiting approval** |
| Phase 4 | Engineering Standards | `docs/engineering/` | ⛔ Blocked on Phase 3 approval |
| Phase 5 | Design System | `docs/design-system/` | ⛔ Blocked |
| Phase 6 | Development Rules | `.cursor/` | ⛔ Blocked |
| Phase 7 | Implementation Plan | `docs/plan/` | ⛔ Blocked |
| Phase 8 | Implementation | `app/` (TBD) | ⛔ Blocked |

### Gate rules

1. Each phase ends with review/approval before the next begins.
2. `product/ProductPrinciples.md` — constitution.
3. `architecture/BehaviorArchitecture.md` — behavioral API contract (D-007);
   every technical proposal must map to transition, ritual, emotion, metric,
   anti-goal, principle.
4. `product/LanguageSystem.md` — canonical terms (MicroStart, VoiceA/B, Ritual).

## Phase 3 Reading Order (current review)

1. [`product/LanguageSystem.md`](product/LanguageSystem.md) — glossary freeze
2. [`product/ProductDecisionLog.md`](product/ProductDecisionLog.md) — D-001…D-012
3. [`architecture/BehaviorArchitecture.md`](architecture/BehaviorArchitecture.md) — authoritative contract
4. [`architecture/Architecture.md`](architecture/Architecture.md) — overview + thesis
5. [`architecture/AppStructure.md`](architecture/AppStructure.md) — modules + creep firewall
6. [`architecture/StateManagement.md`](architecture/StateManagement.md) — MicroStartSession + FreshStartFlag
7. [`architecture/OfflineStrategy.md`](architecture/OfflineStrategy.md)
8. [`architecture/WidgetArchitecture.md`](architecture/WidgetArchitecture.md) + [`WidgetEvolutionProgram.md`](architecture/WidgetEvolutionProgram.md)
9. [`architecture/NotificationArchitecture.md`](architecture/NotificationArchitecture.md)
10. [`architecture/BackgroundServices.md`](architecture/BackgroundServices.md)
11. [`architecture/Permissions.md`](architecture/Permissions.md)
12. [`architecture/AccessibilitySupport.md`](architecture/AccessibilitySupport.md)
13. [`architecture/Localization.md`](architecture/Localization.md)
14. [`architecture/Performance.md`](architecture/Performance.md) · [`BatteryOptimization.md`](architecture/BatteryOptimization.md)
15. [`architecture/Privacy.md`](architecture/Privacy.md) · [`Security.md`](architecture/Security.md)
16. [`architecture/Analytics.md`](architecture/Analytics.md) — MicroStart event dictionary
17. [`architecture/FutureArchitecture.md`](architecture/FutureArchitecture.md)

## Prior phases (frozen)

- Phase 2: `docs/ux/` — start at DesignPrinciples + BehaviorChangeModel
- Phase 1: `docs/product/` — ProductPrinciples + MVPDefinition
- Phase 0: `docs/research/` — ProductOpportunityReport

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
| **Phase 2** | UX Documentation | `docs/ux/` | ✅ Approved / Frozen |
| **Phase 3** | Technical Planning | `docs/architecture/` | ✅ Approved / Frozen |
| Phase 4 | Engineering Standards | `docs/engineering/` | Not started |
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

## Phase 3 Reading Order (frozen)

1. [`product/LanguageSystem.md`](product/LanguageSystem.md) — glossary freeze
2. [`product/ProductDecisionLog.md`](product/ProductDecisionLog.md) — D-001…D-018
3. [`architecture/BehaviorArchitecture.md`](architecture/BehaviorArchitecture.md) — authoritative contract
4. [`architecture/Architecture.md`](architecture/Architecture.md) — overview, complexity firewall, anti-goal firewall
5. [`architecture/FrameworkDecision.md`](architecture/FrameworkDecision.md) — **OPEN** pending spikes
6. [`architecture/Spikes.md`](architecture/Spikes.md) — H13, H14, H15
7. [`architecture/AppStructure.md`](architecture/AppStructure.md) — modules + creep firewall
8. [`architecture/StateManagement.md`](architecture/StateManagement.md) — MicroStartSession + FreshStartFlag boolean
9. [`architecture/OfflineStrategy.md`](architecture/OfflineStrategy.md)
10. [`architecture/WidgetArchitecture.md`](architecture/WidgetArchitecture.md) + [`WidgetEvolutionProgram.md`](architecture/WidgetEvolutionProgram.md)
11. [`architecture/NotificationArchitecture.md`](architecture/NotificationArchitecture.md)
12. [`architecture/BackgroundServices.md`](architecture/BackgroundServices.md)
13. [`architecture/Permissions.md`](architecture/Permissions.md)
14. [`architecture/AccessibilitySupport.md`](architecture/AccessibilitySupport.md)
15. [`architecture/Localization.md`](architecture/Localization.md)
16. [`architecture/Performance.md`](architecture/Performance.md) · [`BatteryOptimization.md`](architecture/BatteryOptimization.md)
17. [`architecture/Privacy.md`](architecture/Privacy.md) · [`AnalyticsPrivacy.md`](architecture/AnalyticsPrivacy.md) · [`Security.md`](architecture/Security.md)
18. [`architecture/Analytics.md`](architecture/Analytics.md) — behavioral event dictionary
19. [`architecture/FutureArchitecture.md`](architecture/FutureArchitecture.md)

Phase 4 has not started. Implementation has not started.

## Prior phases (frozen)

- Phase 2: `docs/ux/` — start at DesignPrinciples + BehaviorChangeModel
- Phase 1: `docs/product/` — ProductPrinciples + MVPDefinition
- Phase 0: `docs/research/` — ProductOpportunityReport

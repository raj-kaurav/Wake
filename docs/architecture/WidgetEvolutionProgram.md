# Widget Evolution Program

**Phase:** 3 — Technical Planning (governance from Phase 2 ratification D-006)
**Status:** Active program — Default V1 frozen; long-term language open
**Authority:** Complements `../ux/Widgets.md`. Engineering optimizes for
**platform honesty, consistency, and accessibility** — not forced visual
parity through hacks.

---

## 1. Program charter

| Item | Decision |
|---|---|
| **Default V1** | Day Dots — launch-ready |
| **Permanent identity?** | **No** — explicitly open |
| **Success of V1** | Honest on both platforms; Notice + MicroStart co-located; a11y complete |
| **Success of evolution** | Beta-validated alternate that beats Day Dots on H1/H8 without violating P1/P2/D6 |

## 2. Engineering principles (binding)

1. **Platform honesty over fake parity** — If iOS cannot animate a ribbon
   smoothly, ship stepped faces that look intentional; do not burn battery
   or App Review goodwill on hacks.
2. **Shared behavior contract, pluggable visuals** — All widget variants
   implement the same contract: day-state rendering, caption, optional
   content line, MicroStart action, rest face, Fresh Start content swap,
   stale face. Visuals are themes behind `DayShapeRenderer`.
3. **Accessibility first** — Every variant ships with a complete text
   alternative; meaning never hue-only; reduced-motion path required.
4. **No debt surfaces** — Evolution must never introduce history, counts,
   or yesterday (D6 / P1).
5. **Remote-config / build-time flags** — Alternate renderers gated for
   beta; Day Dots remains default until Decision Log entry promotes another.

## 3. Candidate pipeline

| ID | Concept | Stage | Next gate |
|---|---|---|---|
| W-A | Day Dots | **Default V1** | Ship; instrument H1 |
| W-B | Day Arc | Horizon 2 lock/watch | Native circular slots |
| W-C | Remaining field | Alt / a11y style | Optional settings style |
| W-D | Opportunity Tiles | Beta explore | Diary + conversion test |
| W-E | Timeline Blocks | Beta explore | Planner-resemblance review |
| W-F | Living Horizon | Research only | Battery + meaning test |
| W-G | Remaining Ribbon | Beta explore | Depletion vs opportunity framing (H2) |
| W-H | Segmented Day | Beta explore | A5 quota-implication review |

## 4. Architecture implication (for WidgetArchitecture.md)

```
DayShapeWidget (shell: sizes, actions, a11y)
  └── DayShapeRenderer (interface)
        ├── DayDotsRenderer      ← V1 default
        ├── OpportunityTilesRenderer  ← flag
        ├── RemainingRibbonRenderer   ← flag
        └── …future
```

Shell owns MicroStart deep link, FreshStartFlag content slot, rest/stale
states. Renderers own geometry only.

## 5. Behavioral mapping (contract)

| Question | Answer for every widget variant |
|---|---|
| Behavior transition | → Notice; Offer co-located |
| Ritual | Morning Awareness / Midday / Evening (by slot); always MicroStart Ritual affordance |
| Emotional state | Calm orientation default; Recovering on Fresh Start |
| Metric | H1 widget→MicroStart; retention; H8 |
| Anti-goal | A2, A5; never A4 |
| Principle | P1, P2, P10, D4, D9 |

## 6. Review trigger

Promote a new default only via `ProductDecisionLog.md` entry after beta
evidence. Until then, Day Dots remains Default V1.

## Quality record

Phase 3 quality gate (2026-09-28). Canonical definitions stay in ProductPrinciples, LanguageSystem, ProductDecisionLog, BehaviorArchitecture, AntiGoals, and SuccessMetrics — this section does not restate them.

- **Purpose:** See the opening of this document.
- **Scope:** MVP architecture for the ritual or subsystem named above. Not Phase 4 standards and not implementation.
- **Behavioral mapping:** Present at the top of this document (or, for BehaviorArchitecture, the document is the mapping).
- **Technical decision:** As written in the body; where a choice depends on H13–H15, the decision is explicitly deferred (`Spikes.md`, `FrameworkDecision.md`).
- **Alternatives:** Considered in the body or in the Decision Log entries D-013–D-018. Rejected: accounts, streaks, history counters, re-engagement notification types, assumed foreground service, framework lock before spikes.
- **Rationale:** Preserve behavioral philosophy; least intrusive platform mechanism; local-first; platform honesty over fake parity.
- **Constraints:** Creep firewall; FreshStartFlag boolean; VoiceA/VoiceB ids; Emotional Temperature required on content; analytics optional.
- **Failure modes:** Fake precision, score UI, punishment ledger, core loop blocked on network or analytics, geometry leaked into domain, FGS added without H15 evidence.
- **Privacy implications:** See `Privacy.md` and `AnalyticsPrivacy.md` when data leaves the device. Default is local.
- **Platform implications:** Android and iOS may differ; document the difference instead of simulating parity.
- **Testing implications:** Spike protocol for H13–H15; otherwise contract tests against BehaviorArchitecture mappings. No production code in Phase 3.
- **Open questions:** Framework (OPEN); Android Speak Time mechanism (OPEN); analytics default consent copy and retention window before a sink exists.
- **Dependencies:** BehaviorArchitecture, LanguageSystem, ProductDecisionLog.

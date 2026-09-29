# Widget Architecture

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 — Day Dots is Default V1 renderer only
**UX:** `../ux/Widgets.md` · Program: `WidgetEvolutionProgram.md`

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | → Notice; Offer co-located |
| Ritual | Morning Awareness / day-long Awareness; MicroStart affordance |
| Emotional state | Calm; Recovering when FreshStartFlag |
| Metric | H1; widget retention; H13 fidelity |
| Anti-goal | A2, A4, A5 |
| Principle | P1, P2, P10, D9 platform honesty |

---

## 1. Domain state vs renderer

The domain describes **time-awareness state** only, for example:

- fraction of wake window elapsed
- remaining duration
- rest-face vs active
- FreshStartFlag (boolean)
- current content line id (or none)
- whether a MicroStart is running and its remaining time

The renderer decides geometry (dots, tiles, ribbon, arc, horizon). Widget
geometry must not leak into domain logic. Day Dots is the Default V1
renderer, not the permanent widget architecture (`WidgetEvolutionProgram.md`).

Future renderers (flagged, not V1): DayDots, OpportunityTiles,
TimelineBlocks, LivingHorizon, RemainingRibbon, DayArc.

## 2. Shell + renderer

```
DayShapeWidgetShell
  - size family (small/medium[/large])
  - MicroStartPendingIntent / deep link
  - open Now intent
  - a11y summary builder
  - applies FreshStartFlag to content request
  - rest face / stale face
  └── DayShapeRenderer (interface)
        DayDotsRenderer (V1 default)
        [flagged] OpportunityTilesRenderer, RemainingRibbonRenderer, …
```

## 3. Timeline / update model

| Platform | Strategy |
|---|---|
| iOS WidgetKit | Timeline entries at ≤15 min steps across wake window; date-relative caption text where possible (H13); reload on WakeWindow change / MicroStart start-end |
| Android AppWidget/Glance | Periodic update ≥15 min; AlarmManager for wake-aligned steps if needed; WorkManager backup |

**Honesty rule:** Never schedule 1-minute updates to fake smoothness.

## 4. Data providers

Widget reads: WakeWindow, VoiceId (for content), DayProgress calculator,
ContentEngine.serve(slot), FreshStartFlag, MicroStartSession?.remaining.

No network. No history queries.

## 5. MicroStart from widget

Must reach Running state in <1s cold-start budget (`Performance.md`).
Android: direct activity/service start. iOS: deep link + prioritized
launch; evaluate Live Activity as mirror (not alternate UI).

## 6. Accessibility

Single aggregated `contentDescription` / `Semantics` node per Widgets.md
§6. Renderer contributes non-visual summary string.

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

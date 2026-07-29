# Widget Architecture

**Phase:** 3 — Technical Planning
**Status:** Draft for review
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

## 1. Shell + renderer

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

## 2. Timeline / update model

| Platform | Strategy |
|---|---|
| iOS WidgetKit | Timeline entries at ≤15 min steps across wake window; date-relative caption text where possible (H13); reload on WakeWindow change / MicroStart start-end |
| Android AppWidget/Glance | Periodic update ≥15 min; AlarmManager for wake-aligned steps if needed; WorkManager backup |

**Honesty rule:** Never schedule 1-minute updates to fake smoothness.

## 3. Data providers

Widget reads: WakeWindow, VoiceId (for content), DayProgress calculator,
ContentEngine.serve(slot), FreshStartFlag, MicroStartSession?.remaining.

No network. No history queries.

## 4. MicroStart from widget

Must reach Running state in <1s cold-start budget (`Performance.md`).
Android: direct activity/service start. iOS: deep link + prioritized
launch; evaluate Live Activity as mirror (not alternate UI).

## 5. Accessibility

Single aggregated `contentDescription` / `Semantics` node per Widgets.md
§6. Renderer contributes non-visual summary string.

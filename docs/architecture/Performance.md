# Performance

**Phase:** 3 — Technical Planning
**Status:** Draft for review

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Offer→Start must feel instantaneous (compete with scroll) |
| Ritual | MicroStart Ritual |
| Emotional state | Competence; no waiting theater |
| Metric | Cold start → Running < 1s; time-to-start ≤10s median |
| Anti-goal | A1 (no heavy app to browse); A8 |
| Principle | P6, D3, D9 |

---

## Budgets

| Path | Budget |
|---|---|
| Widget MicroStart → Running | < 1s on mid-tier devices |
| App icon → Now interactive | < 1.5s cold |
| ContentEngine.serve | < 16ms p95 local |
| Completion UI after timer | < 100ms after 0:00 |

## Techniques

- MicroStart activity/entry point is lightweight (no onboarding, no
  content browse).
- Content pack memory-mapped / pre-indexed by (voice, slot, temperature).
- No network on critical path.
- Avoid large animation frameworks on Timer (D5 silence).

## Regression

CI performance smoke on reference devices; fail build if widget deep link
regressions exceed budget (Phase 4).

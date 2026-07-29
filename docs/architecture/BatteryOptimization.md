# Battery Optimization

**Phase:** 3 — Technical Planning
**Status:** Draft for review

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Notice reliability without device heat/distrust |
| Ritual | Speak Time, pulses, widget |
| Emotional state | Trust (P8 battery honesty in Settings) |
| Metric | No OS battery-abuser flags at defaults; H15 |
| Anti-goal | A2 (discourage 15-min default) |
| Principle | P8, P9 |

---

## Budgets by ritual

| Ritual / system | Default cost posture |
|---|---|
| Day Dots widget | 15-min steps — low |
| Pulses @ 3/day | Negligible |
| Speak Time @ 60 min | Low; on-device TTS brief |
| Speak Time @ 15 min | Measurable — Settings honesty line required |
| MicroStart | Negligible (foreground / short) |

## Strategies

- Prefer AlarmManager/WG aligned to interval boundaries over sticky FGS.
- FGS only if spike proves necessity; then minimal sticky notification.
- No continuous sensors.
- Widget: no second-level refresh.
- Batch analytics flush.

## User honesty

Settings copy states relative battery impact at 15 vs 60 min (Voice-
neutral or Voice-resolved). Never hide cost.

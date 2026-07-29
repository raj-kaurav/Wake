# State Management

**Phase:** 3 — Technical Planning
**Status:** Draft for review

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | MicroStart session state; Fresh Start flag; ritual context |
| Ritual | MicroStart, Fresh Start primarily |
| Emotional state | Weightless returns (no history state leaking into UI) |
| Metric | No lost completions (D11); Fresh Start one-shot correctness |
| Anti-goal | A4 — no scorekeeping state in UI store |
| Principle | P1, P3, D6 |

---

## 1. State domains

| Domain | Lifetime | UI-visible? |
|---|---|---|
| `MicroStartSession` | Ephemeral (running → completed/abandoned) | Timer / N3 |
| `WakeWindow`, `VoiceId`, schedules | Durable prefs | Settings |
| `Intention` | Durable single string (replace) | Optional chip |
| `FreshStartFlag` | Durable bool; cleared on first Now view after set | Only via content slot |
| `RitualContext` (slot, temperature allow-list) | Derived from clock + flags | Content line |
| `ServingLog` | Durable rolling | Never |
| Aggregate MicroStart counters | Durable for analytics | **Never** |

## 2. MicroStartSession state machine

```
Idle → Starting → Running → Completing → Idle
                 ↘ Abandoned (<20s) → Idle
                 ↘ Stopped (≥20s) → Completing → Idle
```

- `Completing` always emits `MicroStartCompleted` (or Stopped-as-complete
  per SuccessMetrics rules) and shows Completion / N2.
- Process death: recover via scheduled completion alarm/notification
  (`Navigation.md` D11).

## 3. FreshStartFlag rules

- Set when `lastMeaningfulInteractionAt` age ≥ gap threshold on next
  process start / widget timeline build.
- **Do not store gap length.**
- Consume on first presentation of Now or widget content line (S6).
- While set (until consume): ContentEngine temperature allow-list =
  `{Recovering, Calm}`.

## 4. UI state principles

- Single source of truth per domain; unidirectional data flow.
- Settings writes apply immediately (F10).
- No global "user score" object.
- Display labels for voice resolved via `VoiceLabelResolver(VoiceId)` —
  never store "Coach" as the preference value.

# State Management

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 (2026-09-28)

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

- **Type: boolean only.** Do not store missed-day counts, streak counts,
  consecutive-day counts, "days lost," or "days failed."
- Set when the age of `lastMeaningfulInteractionAt` is at least the gap
  threshold, on next process start or widget timeline build.
- **Do not store gap length** for display or scoring.
- Consume on first presentation of Now or the widget content line.
- While set (until consumed): ContentEngine temperature allow-list =
  `{Recovering, Calm}`.
- User-visible model: return → Fresh Start → today. No punishment ledger.

## 4. UI state principles

- Single source of truth per domain; unidirectional data flow.
- Settings writes apply immediately (F10).
- No global "user score" object.
- Display labels for voice resolved via `VoiceLabelResolver(VoiceId)` —
  never store "Coach" as the preference value.

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

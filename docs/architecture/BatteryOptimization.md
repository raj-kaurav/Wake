# Battery Optimization

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 (2026-09-28)

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

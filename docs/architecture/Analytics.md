# Analytics

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 — identity rules in `AnalyticsPrivacy.md`
**Product contract:** `../product/SuccessMetrics.md`

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Validates loop metrics without creating A4 UI |
| Ritual | Instrument all; display none as scores |
| Emotional state | — (measurement ethics) |
| Metric | WSU; MicroStarts/user/day; guardrails |
| Anti-goal | A4 scorekeeping (never render analytics to user as performance) |
| Principle | P5, P11, P12 |

---

## 1. Event dictionary (MicroStart vocabulary)

| Event | When |
|---|---|
| `MicroStartStarted` | Session → Running |
| `MicroStartCompleted` | Honest complete / stop ≥20s |
| `MicroStartAbandoned` | Stop/cancel <20s |
| `SelfInitiatedStart` | MicroStart with no awareness prompt in the preceding window |
| `PromptedStart` | MicroStart from pulse, Speak Time carrier, or notification action |
| `AwarenessPulseDelivered` | N1 shown |
| `AwarenessPulseStartTapped` | Action |
| `FreshStartPresented` | FreshStartFlag consumed (boolean path) |
| `LapseReturned` | App open while FreshStartFlag was set |
| `SpeakTimeDelivered` | Utterance or carrier actually played |
| `SpeakTimeSkipped` | Boundary skipped (DND, screen reader, quiet) |
| `WidgetViewed` | Timeline/update presented (coarse; not per-second) |
| `ContentPresented` | Content line id served (never line text) |
| `VoiceSelected` / `VoiceSwitched` | VoiceA/B ids only |

`SelfInitiatedStart` and `PromptedStart` exist so the product can learn
whether Wake is becoming less necessary. They are **not** user-facing
scores. Do not render independence percentages, streaks, or "your score
improved."

**Forbidden events and names:** `TaskCompleted`, `StreakUpdated`,
`ProductivityScore`, `DailyGoal`, `AchievementUnlocked`; intention text;
`days_missed`; advertising IDs; other apps' usage.

## 2. Derived metrics

WSU, resilient adoption, return-after-gap, prompt-dependence ratio,
session-length guardrail — computed server-side or locally in privacy-
preserving pipelines. **Never** bound to UI models.

## 3. Transport

Optional. Batched. Offline queue. Identity = pseudonymous local install
token per `AnalyticsPrivacy.md` (not an account). Core rituals run if
analytics is off, consent is unavailable, the network is down, or the sink
is down. Delete and reset paths are specified there.

## 4. Experiment arms

Remote config for timer duration, framing, renderer flags — binary
defaults always safe if config unreachable.

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

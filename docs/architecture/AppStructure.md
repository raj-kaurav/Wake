# App Structure

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 (2026-09-28)

### Behavioral mapping (structure itself)

| Question | Answer |
|---|---|
| Behavior transition | Enables all; structure prevents illegal transitions (ledger, lists) |
| Ritual | All MVP rituals modularized |
| Emotional state | — (structural) |
| Metric | Onboarding ≤60s; cold start <1s (Performance) |
| Anti-goal | A1, A4, A8 — no modules that host them |
| Principle | P7, P11, P13 |

---

## 1. Layering

```
Presentation/UI          Now, Timer, Completion, Settings, Onboarding
Platform adapters        WidgetKit / AppWidget, Notifications, TTS, Alarms
Application services     MicroStartService, AwarenessScheduler, ContentEngine,
                         FreshStartService, PermissionGateway
Domain                   MicroStartSession, WakeWindow, VoiceId, DayShape,
                         ContentLine, RitualContext
Persistence              Preferences, ContentPack store, ServingLog, AnalyticsBuffer
```

Dependencies point **inward** only. UI never talks to persistence directly.

## 2. Module catalog (MVP)

| Module | Responsibility | Forbidden inside |
|---|---|---|
| `microstart/` | Start, timer, complete, abandon | History list UI models |
| `awareness/` | Wake window, day progress math, Speak Time schedule | Screen-time / app-usage APIs |
| `content/` | Pack load, selection, metadata validation | Network fetch of unreviewed lines |
| `voice/` | VoiceA/VoiceB preference + display-label resolver | Personality chatbot state |
| `freshstart/` | One-shot FreshStartFlag | "days_missed" counters |
| `notifications/` | Schedule, respectful-silence, actions | Re-engagement campaigns |
| `widget/` | Shell + DayDotsRenderer (+ flagged renderers) | Stats rows |
| `settings/` | Flat settings ≤12 | Nested feature labs |
| `analytics/` | Opt-in aggregate events | Intention text; ad IDs |
| `app/` | Navigation host, DI | Business logic |

## 3. Creep firewall (architectural)

The following types **must not exist** in the codebase (lint/arch-unit
tests in Phase 4):

`Task`, `Todo`, `Project`, `Streak`, `Badge`, `Score`, `FeedItem`,
`WeeklyReport`, `SessionHistory` (as user-facing aggregate), `Account`,
`Friend`, `Leaderboard`.

Allowed: `MicroStartSession` (ephemeral), aggregate counters for analytics
only (never hydrated into UI state).

## 4. Framework posture

**Undecided.** Candidates and criteria: `FrameworkDecision.md`. Evidence
protocol: `Spikes.md` (H13–H15). Do not assume a language in this structure
document. Shared contracts (MicroStart, content schema, events) stay
framework-agnostic either way.

## 5. Ritual → module map

| Ritual | Primary modules |
|---|---|
| Morning Awareness | `widget`, `awareness`, `content` |
| MicroStart | `microstart`, `content` (T6) |
| Midday Reset | `notifications`, `awareness`, `content` |
| Evening Reflection | `content`, `widget` (rest face) |
| Fresh Start | `freshstart`, `content` (Recovering) |

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

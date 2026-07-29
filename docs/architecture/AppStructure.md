# App Structure

**Phase:** 3 — Technical Planning
**Status:** Draft for review

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

Widgets, exact alarms, and TTS are heavily native. Recommendation for
Phase 3 spikes: **prefer Kotlin Multiplatform shared domain** *or*
**separate native apps with shared content pack + identical contracts** —
final choice after H13–H15 and team constraints (`FutureArchitecture`
notes). Flutter/RN remain possible if widget/TTS bridges are first-class;
do not choose a framework that forces widget fidelity hacks
(WidgetEvolutionProgram).

## 5. Ritual → module map

| Ritual | Primary modules |
|---|---|
| Morning Awareness | `widget`, `awareness`, `content` |
| MicroStart | `microstart`, `content` (T6) |
| Midday Reset | `notifications`, `awareness`, `content` |
| Evening Reflection | `content`, `widget` (rest face) |
| Fresh Start | `freshstart`, `content` (Recovering) |

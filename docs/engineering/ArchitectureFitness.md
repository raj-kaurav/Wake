# Architecture Fitness

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Purpose:** Make creep-firewall and dependency violations detectable.
Checks are specified now. **Do not add CI, lint configs, or git hooks in
Phase 4** — those are implementation-time enforcement after Phase 4 approval
and a framework choice. Until then, the checklist in `CodeReview.md` applies.

---

## Proposed automated checks (after implementation is authorized)

Fail the build or a dedicated fitness job if any of the following hold:

| Check | Detection idea |
|---|---|
| Prohibited module names | Paths matching `task`, `todo`, `streak`, `history`, `leaderboard`, `achievement`, `social`, `account` as domain modules |
| Domain imports platform | Import graph: domain package must not reference Android, UIKit, SwiftUI, Compose, Flutter widgets, analytics SDK, HTTP client |
| Domain imports analytics | Same graph |
| UI imports infrastructure | UI package must not reference SQL, alarm managers, or TTS types |
| Network required for core | Static test: MicroStart use case constructs without a network type |
| FreshStart counter | Grep/types: no field `missedDays`, `streakCount`, `daysFailed` |
| Re-engagement notification | Enum of notification types has no re-engagement cases |
| Event vocabulary | Analytics event registry rejects `TaskCompleted`, `StreakUpdated`, `ProductivityScore`, `DailyGoal`, `AchievementUnlocked` |
| Content metadata | Pack validator fails closed |

## Review-level checks (now)

Every PR uses `CodeReview.md`. A reviewer rejects changes that would fail
the table above even before automation exists.

## False positives

Platform adapters **may** import SDKs. The check is layer-based, not
repo-wide. Shared tests live next to domain and must also stay SDK-free.

## Mapping

| Field | Answer |
|---|---|
| Behavior transition | Guards all transitions from illegal state |
| Ritual | All |
| Emotional goal | Prevents shame and scorekeeping from re-entering via code |
| Metric | Fitness job green (future) |
| Anti-goal | A1, A3, A4, A5 |
| Principle | P3, P5, P7, P13 |

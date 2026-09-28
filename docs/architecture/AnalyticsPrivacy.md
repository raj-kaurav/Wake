# Analytics Privacy

**Phase:** 3 — Technical Planning
**Status:** Approved constraint set (D-016) — frozen with Phase 3
**Companion:** `Analytics.md` (events) · `Privacy.md` (product inventory)

---

## Purpose

Allow product learning (including graduation: prompted vs self-initiated
MicroStarts) without making analytics a prerequisite for behavior, and
without identifying people.

## Scope

Optional, aggregate, pseudonymous telemetry. Core rituals do not call the
network.

## Identity model

| Property | Rule |
|---|---|
| Kind | Pseudonymous **install token** |
| Generation | Locally, random, non-human-readable |
| Meaning | Not a name, email, phone, or device advertising ID |
| Account | **None.** Do not create accounts for analytics |
| Reset | User action "reset analytics identity" rotates the token; prior token is not linked |
| Deletion | Uninstall or explicit delete request drops the queue and token |

The token is an install-scoped key for cohort metrics (WSU), not a user
profile.

## Event model

See `Analytics.md`. Vocabulary is behavioral (MicroStart, AwarenessPulse,
FreshStart, SpeakTimeDelivered, SpeakTimeSkipped, WidgetViewed,
ContentPresented, LapseReturned, SelfInitiatedStart, PromptedStart).

**Forbidden event names / concepts:** `TaskCompleted`, `StreakUpdated`,
`ProductivityScore`, `DailyGoal`, `AchievementUnlocked`, and any
user-visible score derived from independence ("72% independent").

`SelfInitiatedStart` vs `PromptedStart` is a **learning distinction only**.
It must not be rendered as a score, streak, or evaluation.

## Data minimization

Collect only fields required for SuccessMetrics and H-series. No intention
text, no content of notifications beyond content-line **id**, no contacts,
no location, no installed-app lists.

## Retention

Server-side (if a sink exists): minimal aggregate retention, documented in
the privacy notice before any sink ships. Default design allows **local-only
mode** with no sink. Exact day-count is an open question below; it must be
stated in the notice before collection starts.

## Reset behavior

Settings: reset identity → new token, queue cleared, no merge with old token.

## Offline queue behavior

Events append to a local capped queue. Flush when network exists **and**
analytics is enabled. Queue overflow drops oldest. Core UX never waits on
flush.

## Deletion behavior

Opt-out or delete: stop collection, delete local queue, rotate/discard
token. Remote deletion of already-sent aggregates follows the privacy
notice (no PII to delete beyond the token's event stream).

## Consent / opt-out

Analytics **off** is the safe default until an explicit in-app choice (or
a clearly disclosed default that still works fully when refused — product
copy decides the default; architecture requires **full function when off**).

Works when:

- analytics permission/consent unavailable
- analytics disabled
- network unavailable
- analytics service unavailable

## Failure behavior

Sink errors are ignored by ritual code. No retries that block UI. No
fallback that enables analytics implicitly.

## What is NEVER collected

- Intention string
- Display name, email, phone
- Advertising IDs / cross-app tracking
- Precise location
- Contacts or social graph
- Screen-time or other apps' usage
- Missed-day counts, streaks, "days failed"
- Voice display labels as identity
- Content line **text** (ids only, if content experiments need them)
- Any metric whose only use is to show the user a score

## Behavioral mapping

| Field | Answer |
|---|---|
| Behavior transition | Measures loop; does not alter it |
| Ritual | Instrumentation across rituals |
| Emotional goal | Safety; no surveillance feeling |
| Success metric | WSU and graduation ratio (prompted vs self-initiated) |
| Anti-goal | A4 scorekeeping; A3 if prompts are optimized against graduation |
| Principle | P5, P11, P12 |

## Quality record

- **Technical decision:** Pseudonymous local install token; analytics optional.
- **Alternatives rejected:** Accounts for analytics; advertising IDs; no telemetry ever (rejected because H-series and WSU need some opt-in signal — local-only mode remains valid).
- **Rationale:** Phase 3 review §7.
- **Constraints:** Core loop has zero analytics dependency.
- **Failure modes:** Token treated as PII; queue blocking start; score UI.
- **Privacy:** This document.
- **Platform:** Same model both OS.
- **Testing:** Airplane mode MicroStart; opt-out then start; token reset uniqueness.
- **Open questions:** Default opt-in vs opt-out copy; retention day-count before sink exists.
- **Dependencies:** Analytics.md, Privacy.md, SuccessMetrics.md.

# State Management Standards

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Architecture:** `../architecture/StateManagement.md`

---

## Source of truth

| State | Owner | UI may |
|---|---|---|
| `MicroStartSession` | Application service | Render; not invent transitions |
| `WakeWindow`, `VoiceId`, schedules | Preferences repository | Edit via use cases |
| Intention string | Preferences; **never sent to analytics** | Edit/replace |
| `FreshStartFlag` | FreshStart use case | Consume once via use case |
| `TimeAwarenessState` | Derived from clock + wake window | Read |
| Serving log | Content infrastructure | Not shown |
| Analytics counters | Analytics infrastructure | **Never bind to UI** |

One owner per fact. UI holds view state only (animation, text field draft).

## Mutation

- Mutations go through application use cases.
- Domain objects are **immutable** values. Transitions return new values.
- Infrastructure may use mutable buffers inside adapters; those must not leak.
- Settings apply immediately (no deferred save that can lose a change).

## Persistence and restoration

- Persist configuration and the in-flight MicroStart (`startedAt`, duration).
- Do not persist a list of past MicroStarts for UI.
- Restore on launch before showing Now: resolve FreshStartFlag, then session recovery (`DomainStandards.md`).

## FreshStartFlag

Boolean only. Set from age of last meaningful interaction versus the gap
threshold. Do not store the gap length for display. Do not add:

- missed-day counters
- streak counters
- consecutive-day counters
- punishment state
- engagement scores
- hidden productivity scoring

## Concurrency

- A single active `MicroStartSession`. A second start request is ignored or
  routes to the running session — it does not create a parallel timer.
- Widget, notification, and UI start paths call the same use case.
- Clock reads and session writes are serialized per process (one mutex or
  equivalent). Document the choice when a framework exists; do not add a
  distributed lock.

## Synchronization

No cloud sync in MVP (`OfflineFirst.md`). Do not add conflict resolution for
user profiles.

## Lifecycle

Backgrounding does not cancel MicroStart. Process death uses the recovery
rule. Logout does not exist (no account).

# Domain Standards

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Maps to:** `../architecture/BehaviorArchitecture.md`,
`../architecture/StateManagement.md`

---

## Domain rules

The domain is:

- deterministic given inputs (clock, configuration, prior local facts)
- platform-independent
- network-independent
- UI-independent
- analytics-independent

The domain must **not** import UI frameworks, analytics SDKs, notification
SDKs, platform APIs, network clients, or storage implementations.

Platform capabilities enter through ports, for example `Clock`,
`SchedulerPort`, `SpeakTimeCapability` (status only), `ContentPackSource`.
Implementations live in infrastructure.

## MicroStart — canonical model

MicroStart is a behavioral intervention that reduces starting friction. It
is **not** a generic task or focus-session abstraction. Do not add task
titles lists, project ids, or cadence plans (25/5).

### States

`Idle` → `Running` → `Completing` → `Idle`

Branches:

- Cancel or stop **before 20 seconds** → `Abandoned` → `Idle` (not a
  completed MicroStart).
- Stop **at or after 20 seconds** → `Completing` (counts as an honest
  completion; no scolding variant).
- Timer reaches the promised duration (default **120000 ms**) → `Completing`.

### Transitions

| From | Event | To | Domain effect |
|---|---|---|---|
| Idle | `StartRequested` | Running | Record `startedAt`, `duration`, optional intention **reference** (storage outside domain logic) |
| Running | `DurationElapsed` | Completing | Success path |
| Running | `StopRequested` if elapsed < 20s | Abandoned | No completion |
| Running | `StopRequested` if elapsed ≥ 20s | Completing | Completion |
| Completing | `Acknowledged` or timeout owned by application | Idle | Session dropped |
| Completing | `AgainRequested` | Running | New session, same intention reference, user-initiated |

No auto-extend. No transition that lengthens the promise.

### Events (domain)

`MicroStartStarted`, `MicroStartCompleted`, `MicroStartAbandoned`.
Application may additionally classify `PromptedStart` vs `SelfInitiatedStart`
from **context passed in** (was a prompt the cause?). The domain does not
query analytics to decide that.

### Persistence

The domain type `MicroStartSession` is ephemeral. Persistence of the
in-flight session (for process death) is an infrastructure concern: store
`startedAt` and `duration` so recovery can compute completion. Do not
persist a user-visible history.

### Timing, interruption, recovery

- Elapsed time uses a `Clock` port (device clock). If the clock jumps, see
  `OfflineFirst.md`: prefer honest completion if `now >= startedAt + duration`,
  and honest remaining time otherwise. Do not invent missed days.
- Interruption (call, background) does **not** cancel the session.
- Recovery after process death: if end time has passed, enter `Completing`;
  else resume `Running`. Never drop a ≥20s start.

### Behavioral mapping

| Field | Answer |
|---|---|
| Behavior transition | Offer → Start → Momentum → Reflection |
| Ritual | MicroStart Ritual |
| Emotional goal | Action, then proportionate confidence |
| Metric | `MicroStartCompleted`; time-to-start |
| Anti-goal | A1, A4, A8 |
| Principle | P2, P5, P8 |

## Other domain types

- `WakeWindow` — start/end local times.
- `TimeAwarenessState` — fraction elapsed, remaining, rest vs active. No
  widget geometry.
- `FreshStartFlag` — boolean. Rules in `StateManagementStandards.md`.
- `VoiceId` — `VoiceA` | `VoiceB` only.
- `ContentQuery` / selected `ContentLine` — metadata required; text is data.

## Determinism

Same query + same clock + same pack version + same flag → same content id,
except where the specification explicitly uses weighted random
(`../ux/ContentSystem.md`). Random draws must be injectable for tests.

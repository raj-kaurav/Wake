# Testing Strategy

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Note:** This defines tests to write **after** implementation is
authorized. Phase 4 does not add a test harness or production code.

---

## Unit tests

Domain and pure functions:

- MicroStart transitions, including the 20-second boundary and no auto-extend
- FreshStartFlag set/consume; never a counter
- Content selection filters, temperature caps, recency
- Wake-window progress and rest-face boundary
- Notification schedule generation: timezone, DST, quiet-today, no backlog burst

## Integration tests

- Preferences round-trip for VoiceId and wake window
- Process-death recovery of an in-flight MicroStart
- Analytics queue: overflow, opt-out clears, failure does not throw into MicroStart
- Content pack validation rejects incomplete lines
- Notification adapter receives a schedule and dedupes ids (fake scheduler)

## Platform tests

When a framework exists and devices are available (not Phase 4):

- Widget snapshot accessibility string
- Speak Time capability status per platform
- Notification permission denial path
- Background fire reliability — this **is** H15 evidence, not a guessed pass

## Behavioral tests (mandatory)

These protect AntiGoals and the constitution:

| Case | Must hold |
|---|---|
| Five-day absence | No missed-day count exists in stored state or UI model |
| Lapse return | FreshStartFlag boolean only; temperature Recovering/Calm; no shame copy key |
| Notification failure | `startMicroStart` still succeeds |
| Analytics throw | `startMicroStart` still succeeds |
| Completion | Duration honored; no transition to a longer forced session |
| User-visible model | No type or field named streak, score, or productivity |

## What not to test for

Maximizing session length, streak persistence, or re-engagement delivery.
Those are defects if present.

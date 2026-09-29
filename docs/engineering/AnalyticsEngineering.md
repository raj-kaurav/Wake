# Analytics Engineering

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Privacy authority:** `../architecture/AnalyticsPrivacy.md`

---

## Subordination

Analytics must **never** be a dependency of MicroStart, Awareness, Fresh
Start, Speak Time, widgets, notifications, or content delivery. Those
modules do not import the analytics SDK or queue. Application code may
emit events **after** a use case succeeds, through a port that no-ops when
disabled.

If analytics fails, throws, or is offline, the use case still returns
success.

## Naming and schema

- Event names: `../architecture/Analytics.md` and `NamingConventions.md`.
- Each event has a version integer. Adding a required field increments
  version. Consumers ignore unknown versions rather than crashing the app.
- Payload is a property bag of non-sensitive enums and ids (content line
  id, voice id, renderer id). No free text from the user.

## Queue

- Local, capped, append-only.
- Overflow drops oldest.
- Deduplicate by event id (UUID created at emit time) on flush.
- Retry with backoff only while opted in. Give up without user-visible
  errors.
- Flush never runs on the MicroStart start path as a blocking call.

## Delivery

Optional sink. No account. Identity is the install token in
AnalyticsPrivacy. Reset rotates the token and clears the queue.

## Opt-out

Disabled means: do not enqueue, delete the queue, do not retry. Core
features unchanged.

## Graduation metrics

`PromptedStart` and `SelfInitiatedStart` are emitted for product learning.
No API and no UI may format them as a percentage, grade, or streak.

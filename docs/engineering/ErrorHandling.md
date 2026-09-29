# Error Handling

**Phase:** 4 — Engineering Standards
**Status:** Draft for review

---

## Philosophy

Prefer graceful degradation over false certainty. Errors in optional
systems must not fail core rituals. User-facing copy follows S8 rules in
`../ux/Microcopy.md`: calm, factual, next step, no blame.

| Failure | Behavior |
|---|---|
| Analytics unavailable | Core app continues. Drop or queue events. No dialog. |
| Network unavailable | Core app continues. No blocking offline screen. |
| Speak Time unavailable | Capability status `Unavailable` or `PartiallySupported`. Do not pretend precision. |
| Notification permission denied | Core app continues. Settings explains how to grant later. |
| Widget refresh restricted | Honest coarse or stale face ("tap to refresh"), not a frozen clock presented as live. |
| Content item invalid | Skip line. If none remain, bundled fallback line with full metadata. |
| MicroStart process death | Recover from `startedAt` + duration. Bank completion if time elapsed. |
| Clock jump | See `OfflineFirst.md`. Do not emit punishment state. |

## Internal errors

- Domain functions return explicit results (`ok` / `rejected` with a
  reason code), not UI strings.
- Adapters translate reason codes to catalog strings.
- Do not catch-and-swallow in a way that marks a MicroStart completed when
  it did not run.
- Crashes: reporters must scrub intention text and tokens (`PrivacyEngineering.md`).

## False certainty

If the system is unsure (alarm drift, stale widget), say so or go quiet.
Do not show a precise remaining-minute animation that the platform is not
updating.

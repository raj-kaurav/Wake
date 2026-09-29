# Notification Engineering Standards

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Architecture:** `../architecture/NotificationArchitecture.md`,
`../ux/NotificationStrategy.md`

---

## Purpose

Notifications support Awareness and MicroStart. They do not maximize
retention.

## Names

Use the architecture types only:

`AwarenessPulse`, `MicroStartCompleted`, `MicroStartRunning`,
`SpeakTimeCarrier` (iOS tier), `ForegroundServiceNotice` (Android **only if**
H15 evidence later requires it — not the default).

**Do not add:** `ReEngagement`, `WeMissYou`, `ComeBack`,
`YourStreakIsBreaking`, guilt copy, streak preservation, or escalating
frequency after ignores beyond the already-specified respectful-silence
**reduction**.

## Scheduling

- Compute fire times from `WakeWindow`, cadence, quiet hours, and quiet-today.
- One scheduler implementation shared by tests; platform adapters only
  register with the OS.
- Suppress pulses while a MicroStart is running.
- Post-completion cooldown is a constant owned by application policy
  (beta-tunable within the architecture ceiling, not unlimited).

## Cancellation and deduplication

- Changing wake window or cadence cancels future pulses and reschedules.
- Idempotent schedule ids: `awareness-{localDate}-{slot}` so duplicates
  collapse.
- Quiet-today cancels remaining pulses until the next wake window.
- Completing or abandoning a MicroStart cancels `MicroStartRunning` and
  schedules completion notification only if the app is not in front.

## Permissions

Denied permission does not block MicroStart or the widget. Surface honest
settings copy. No re-prompt loop (`../architecture/Permissions.md`).

## Time changes

| Event | Behavior |
|---|---|
| Timezone change | Reschedule in the new local wake window. Do not "catch up" missed pulses with a burst. |
| DST | Same: reschedule forward. Do not fire a backlog. |
| Device reboot | Reschedule from stored preferences. No guilt notification about downtime. |
| Clock set backward/forward | Do not emit a pile of overdue pulses. Next boundary only. |

## Offline and failure

Scheduling is local. If the OS drops a notification, do not retry with a
more aggressive campaign. MicroStart remains available in-app and from the
widget if the widget still works.

## Copy

Notification text comes from the Content Engine (or Speak Time's fixed
utterance), not ad-hoc strings in the adapter.

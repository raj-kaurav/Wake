# Offline-First Standards

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Architecture:** `../architecture/OfflineStrategy.md`

---

## Local persistence

All MVP ritual state is local: preferences, content pack, serving log,
in-flight MicroStart, analytics queue. Core behavior does not call the
network.

## Synchronization boundaries

**No cloud synchronization in MVP.** Do not add account sync, CRDTs, or
server profiles. A future backend must be additive and needs a Product
Decision.

The only optional outbound path is the analytics flush, which is
non-blocking and skippable.

## Offline queues

Analytics queue only (`AnalyticsEngineering.md`). There is no "outbox" of
MicroStarts to upload.

## Retry

Analytics retries with backoff. Notification scheduling does not retry a
missed pulse as a burst. Content does not retry a network fetch (there is
none for the corpus).

## Conflicts

None for MVP user data (single device, no sync). If two UI surfaces start
a MicroStart, the single-session rule applies (`StateManagementStandards.md`).

## Timestamps and clocks

- Store instants in UTC plus the wake window as local civil times.
- On timezone or DST change: recompute schedules forward; do not backfill.
- If the device clock jumps past a MicroStart end, complete honestly.
- If the clock jumps backward during a run, remaining time may increase;
  do not create a negative "missed" record. Cap displayed remaining at the
  original duration.

## Offline test

A release candidate must complete a MicroStart, render day state, and
select content with the network disabled.

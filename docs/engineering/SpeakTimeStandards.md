# Speak Time Engineering Standards

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**H15 is OPEN.** This document defines the abstraction only. It does **not**
choose a foreground service or any other Android mechanism.

---

## Capability port

Conceptual port (not an implementation):

```
SpeakTimeCapability
  status(): Supported | PartiallySupported | Unavailable
  schedule(plan): void
  cancel(): void
  describeLimitation(): user-facing reason key
```

| Status | Meaning |
|---|---|
| `Supported` | Chosen mechanism meets the reliability bar on this device |
| `PartiallySupported` | Works with documented drift or fewer intervals |
| `Unavailable` | Do not offer the ritual as if it works |

Android and iOS are **not** assumed equivalent. iOS may be
`PartiallySupported` via notification sounds. Android status waits on H15.

## Rules

- Exact timing is never described as guaranteed when status is partial or
  when the mechanism is inexact.
- Settings copy uses `describeLimitation()`, not a hardcoded "always on time."
- Audio policy: skip calls; respect DND; defer to an active screen reader;
  headphone-only is a user setting implemented in the adapter.
- Utterance text is the clock phrase only ("It's 12:30."), not motivational
  speech.
- If status is `Unavailable`, MicroStart and the widget still work.
- Do not select FGS vs non-FGS until `../architecture/Spikes.md` H15 has
  Evidence and Decision. Least intrusive reliable mechanism wins
  (`../product/ProductDecisionLog.md` D-015).

## Behavioral mapping

| Field | Answer |
|---|---|
| Behavior transition | Notice |
| Ritual | Awareness / Midday Reset |
| Emotional goal | Neutral orientation |
| Metric | `SpeakTimeDelivered`, `SpeakTimeSkipped` |
| Anti-goal | A2 vigilance; false certainty |
| Principle | P8, P10 |

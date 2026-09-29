# Privacy Engineering

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Authority:** `../architecture/Privacy.md`, `../architecture/AnalyticsPrivacy.md`,
principle P11

---

## Minimization

Collect a field only if a named metric or setting requires it. Do not store
data because it might be useful later.

## Local-first storage

Configuration, intention, content pack, serving log, and in-flight
MicroStart live in app-private storage. No MVP cloud profile.

## Install token

- Random, local, non-human-readable, not derived from hardware ids.
- Reset: new token, queue deleted, no link to the old token.
- Deletion: same, plus discard of unsent events.
- Never put the token in logs.

## Retention

Unsent queue: until flush, opt-out, or overflow drop.
On-device serving log: capped rolling window for recency suppression only.
Server retention: unset until a sink exists; must be written in the privacy
notice **before** collection. This standard does not invent a backend.

## Consent

Analytics off by architecture when consent is absent. Document the product
default in UX copy later; engineering must honor off as full function.

## Sensitive data

| Data | Rule |
|---|---|
| Intention text | Local only. Never analytics, never logs, never crashes |
| Future private notes | Same, if ever approved |
| Behavioral history | No UI history; no missed-day series |
| PII | Do not collect |
| Productivity scores | Do not compute |
| Inferred psychological states | Do not compute or store |

## Logging

See `LoggingStandards.md`. Redact by default.

## Offline data

Queues and preferences remain on device. No sync conflict. Uninstall clears
them via normal app sandbox deletion.

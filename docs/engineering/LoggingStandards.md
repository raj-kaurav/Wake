# Logging Standards

**Phase:** 4 — Engineering Standards
**Status:** Draft for review

---

## Levels

| Level | Use |
|---|---|
| Error | Unexpected failure that a developer must see (adapter crash, corrupt pack) |
| Warn | Degraded but handled (Speak Time partial, widget stale, analytics drop) |
| Info | Lifecycle boundaries in debug builds (MicroStart started) — **ids only** |
| Debug | Development only; stripped or no-op in production |

## Production

Default production level: Warn and Error. Info for MicroStart is off unless
a temporary, documented diagnostic build is used. No remote log pipeline in
MVP. If crash reporting is added later, it needs a Product Decision and the
redaction rules below.

## Structured fields

Prefer key-value: `event`, `voiceId`, `contentId`, `capabilityStatus`,
`reasonCode`. No sentences built from user input.

## Never log

- Intention text
- Future private notes
- Install token
- Analytics payloads that include free text
- Identifiable personal information
- Productivity scores or inferred psychological states
- Notification body copy if it could include an intention interpolation
- Full content line text in production (content id is enough)

## Redaction

A single logging wrapper is the only allowed logger. It drops forbidden
keys. Reviewers reject direct `print` / `Log.*` of session objects that
contain the intention field.

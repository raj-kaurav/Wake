# Content Engineering

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Schema authority:** `../ux/ContentSystem.md` (mandatory metadata, D-011)

---

## Content is product data

Lines are not arbitrary UI strings. UI chrome (buttons, settings labels)
lives in string catalogs. Behavioral lines live in the content pack and
pass the ethics checklist before `review.status = active`.

## Required fields

Every item must have: content id, voice id (`VoiceA` or `VoiceB`), content
type, context/slots, intensity, emotional temperature, landmark eligibility,
copy, review status, locale, version. Missing any field **fails validation**.
Display labels are not fields.

## Loading

- Load the signed or binary-bundled pack at startup.
- Reject the whole file if the container version is unknown; fall back to
  the last valid bundled pack.
- Do not fetch unreviewed lines from the network in MVP.

## Validation (release-blocking)

Fail the pack if:

- Any active line lacks mandatory metadata.
- A slot/voice cell is below the minimum variant depth in ContentSystem
  (or the pack declares a documented exception).
- Temperature rules are violated (for example Urgent on a Fresh Start slot).
- Copy contains banned ledger words where the slot forbids them (S6).
- Voice id is a display name (`Coach`, `Friend`) instead of `VoiceA`/`VoiceB`.

Invalid individual lines are dropped; if a query then has no survivor,
serve a tiny built-in fallback line that still has full metadata
(`ErrorHandling.md`). Never show an empty quote error.

## Versioning

Pack `content-vN`. Line ids are immutable. Retired lines stay in the file
with status `retired` so analytics ids remain meaningful.

## Selection

Implement the documented filter order (voice, slot, locale, intensity cap,
temperature allow-list, landmark, recency). Tests must pin Fresh Start to
Recovering/Calm only.

## Locale

English at launch. Additional locales are new packs, not runtime translation
of wit. See `../architecture/Localization.md`.

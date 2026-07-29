# Localization

**Phase:** 3 — Technical Planning
**Status:** Draft for review

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Content Engine delivery in locale |
| Ritual | All copy-bearing rituals |
| Emotional state | Voice contracts re-expressed culturally |
| Metric | Launch = `en` completeness; schema ready |
| Anti-goal | A7 (bad translations that shame) |
| Principle | P4, LanguageSystem |

---

## 1. Launch scope

English-only corpus and UI. Schema carries `locale` on every ContentLine.

## 2. String architecture

| Layer | Mechanism |
|---|---|
| UI chrome | Platform string catalogs |
| Voice **display** labels | Separate keys (`voice_a_label`, `voice_b_label`) — swappable at Phase 5 |
| Content Engine | Per-locale packs; VoiceA/VoiceB IDs stable across locales |
| Speak Time | Locale-appropriate time phrasing / pre-rendered assets |

## 3. Non-negotiables for future locales

- Re-author VoiceA/VoiceB contracts; do not literal-translate wit.
- Ethics checklist per line in each locale.
- Temperature + intensity metadata preserved.
- RTL layout support when locale requires.

## 4. What not to localize away

MicroStart (internal identifier) stays English token in code/events
worldwide. User-facing "Start" localizes normally.

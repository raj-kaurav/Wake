# Localization

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 (2026-09-28)

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

## Quality record

Phase 3 quality gate (2026-09-28). Canonical definitions stay in ProductPrinciples, LanguageSystem, ProductDecisionLog, BehaviorArchitecture, AntiGoals, and SuccessMetrics — this section does not restate them.

- **Purpose:** See the opening of this document.
- **Scope:** MVP architecture for the ritual or subsystem named above. Not Phase 4 standards and not implementation.
- **Behavioral mapping:** Present at the top of this document (or, for BehaviorArchitecture, the document is the mapping).
- **Technical decision:** As written in the body; where a choice depends on H13–H15, the decision is explicitly deferred (`Spikes.md`, `FrameworkDecision.md`).
- **Alternatives:** Considered in the body or in the Decision Log entries D-013–D-018. Rejected: accounts, streaks, history counters, re-engagement notification types, assumed foreground service, framework lock before spikes.
- **Rationale:** Preserve behavioral philosophy; least intrusive platform mechanism; local-first; platform honesty over fake parity.
- **Constraints:** Creep firewall; FreshStartFlag boolean; VoiceA/VoiceB ids; Emotional Temperature required on content; analytics optional.
- **Failure modes:** Fake precision, score UI, punishment ledger, core loop blocked on network or analytics, geometry leaked into domain, FGS added without H15 evidence.
- **Privacy implications:** See `Privacy.md` and `AnalyticsPrivacy.md` when data leaves the device. Default is local.
- **Platform implications:** Android and iOS may differ; document the difference instead of simulating parity.
- **Testing implications:** Spike protocol for H13–H15; otherwise contract tests against BehaviorArchitecture mappings. No production code in Phase 3.
- **Open questions:** Framework (OPEN); Android Speak Time mechanism (OPEN); analytics default consent copy and retention window before a sink exists.
- **Dependencies:** BehaviorArchitecture, LanguageSystem, ProductDecisionLog.

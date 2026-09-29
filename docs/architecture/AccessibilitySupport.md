# Accessibility Support

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 (2026-09-28)
**UX:** `../ux/Accessibility.md` (incl. cognitive §9)

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Full loop via sight/sound/touch/text |
| Ritual | All |
| Emotional state | Competence; Speak Time deferral to screen reader = respect |
| Metric | Release-blocking a11y suite pass |
| Anti-goal | — (accessibility is premise) |
| Principle | P10 |

---

## Implementation requirements

1. **Semantics:** Every control labeled; widget aggregated description;
   Timer pollable not chatty.
2. **Dynamic type / font scale:** Layouts reflow; no truncated critical
   copy.
3. **Contrast:** AA both Voice palettes × light/dark; widget owns
   background.
4. **Reduced motion:** Renderer + transitions honor platform flags.
5. **TTS coexistence:** Speak Time skips when VoiceOver/TalkBack speaking.
6. **Switch access:** Focus order per WireframeDescriptions.
7. **Cognitive:** Decision-count tests; Fresh Start path in UI tests;
   no badge APIs used.

Automated + manual matrix per release (Accessibility.md §10).

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

# Performance

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 (2026-09-28)

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Offer→Start must feel instantaneous (compete with scroll) |
| Ritual | MicroStart Ritual |
| Emotional state | Competence; no waiting theater |
| Metric | Cold start → Running < 1s; time-to-start ≤10s median |
| Anti-goal | A1 (no heavy app to browse); A8 |
| Principle | P6, D3, D9 |

---

## Budgets

| Path | Budget |
|---|---|
| Widget MicroStart → Running | < 1s on mid-tier devices |
| App icon → Now interactive | < 1.5s cold |
| ContentEngine.serve | < 16ms p95 local |
| Completion UI after timer | < 100ms after 0:00 |

## Techniques

- MicroStart activity/entry point is lightweight (no onboarding, no
  content browse).
- Content pack memory-mapped / pre-indexed by (voice, slot, temperature).
- No network on critical path.
- Avoid large animation frameworks on Timer (D5 silence).

## Regression

CI performance smoke on reference devices; fail build if widget deep link
regressions exceed budget (Phase 4).

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

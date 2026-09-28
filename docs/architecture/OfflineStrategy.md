# Offline Strategy

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 (2026-09-28)

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Entire loop must work offline (Notice→MicroStart→Reflection) |
| Ritual | All MVP rituals |
| Emotional state | Competence; no "you're offline" shame wall |
| Metric | Core loop success rate with network disabled = 100% |
| Anti-goal | A1 (no online destination to browse) |
| Principle | P11 local-first |

---

## Guarantees

1. **MicroStart Ritual** works with airplane mode from cold start.
2. **Day Dots widget** computes from local clock + WakeWindow.
3. **Content Engine** serves from packaged pack (no CDN required).
4. **Speak Time** (Android) uses on-device TTS only.
5. **Analytics** queue locally and flush when online; failure to flush
   never blocks ritual UX (`EmptyStates.md` offline).

## Non-guarantees (honest)

- Store listing / remote config fetch for experiment arms may be stale
  offline — defaults ship in binary.
- Future Stoic pack download (if ever networked) is Horizon 2+ and must
  remain optional.

## Storage

| Data | Location | Sync |
|---|---|---|
| VoiceId, WakeWindow, schedules | Local prefs/db | None |
| Intention string | Local only | **Never transmitted** |
| Content pack | App bundle (+ optional update package signed) | Versioned |
| ServingLog | Local rolling | None |
| Analytics buffer | Local queue | Opt-in flush |

## Empty-state policy

No full-screen offline blocker. If a future online-only surface exists, it
degrades; MicroStart affordance never does.

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

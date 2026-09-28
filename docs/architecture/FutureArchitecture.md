# Future Architecture

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 (2026-09-28) — planning only
**Constraint:** No future item bypasses BehaviorArchitecture mapping or
OutOfScope constitutional bans.

---

## 1. Horizon 2 technical themes

| Theme | Architectural note | Gate |
|---|---|---|
| Lock screen / AOD / watch | Same DayShapeRenderer contract; Arc renderer for circular | Widget Evolution Program |
| The Stoic pack | New VoiceId e.g. `VoiceStoic`; consent store; separate content pack; ethics review | D-008 |
| Calendar-aware T2 | Read-only calendar adapter behind ContentEngine time-fact provider | Research demand |
| Live wallpaper (Android) | NOTICE-only; must not own MicroStart (no affordance) — P2 via widget still required | Battery |
| Own-voice prompts | Local audio store; never upload | P11 |
| Speak Time iOS parity | OS API dependent | H14 revisits |

## 2. Explicitly not architected

Cloud AI coach · sync accounts · social graph · screen-time SDK · regret
simulation · streak service · task DB.

## 3. Extensibility rules

1. New VoiceId = content pack + contract doc + Decision Log.
2. New Ritual = BehaviorArchitecture row before any module.
3. New Renderer = implements DayShapeRenderer; flag default off.
4. Any network requirement for a ritual → Privacy + P11 re-review.

## 4. Framework evolution

If MVP is dual-native, shared domain (KMP) may expand. If MVP is
cross-platform, native widget/TTS bridges remain owned adapters — never
leak into domain.

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

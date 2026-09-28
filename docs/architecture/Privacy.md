# Privacy

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 (2026-09-28)
**Ethics:** `../research/EthicalConsiderations.md` §4.4 · Principle P11

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Trust enables Offer→Start (users won't engage if surveilled) |
| Ritual | All |
| Emotional state | Safety |
| Metric | Zero intention exfiltration; opt-out honored |
| Anti-goal | — |
| Principle | P11 |

---

## Data inventory (complete for MVP)

| Data | Purpose | Leaves device? |
|---|---|---|
| VoiceId (VoiceA/B) | Content selection | Only as aggregate segment if analytics on |
| WakeWindow | Day shape / schedules | Aggregate optional |
| Schedules / silence level | Awareness | Aggregate optional |
| Intention string | MicroStart label | **Never** |
| ServingLog | Anti-habituation | Never |
| MicroStart aggregates | WSU / H-series | Opt-in analytics only |
| FreshStartFlag | Recovering content | Never as "days missed" |

## Policies

- No account. No ads. No data brokers. No ATT tracking use.
- Analytics: plain-language disclosure; feature-loss-free opt-out.
- On-device TTS only.
- Privacy nutrition label / Play Data Safety accurate to this inventory.
- Future cloud features require Decision Log + P11 re-clear.

## Empty / About

About screen lists the five local items in grade-6 language (`EmptyStates`
/ Microcopy).

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

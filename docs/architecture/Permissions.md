# Permissions

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 (2026-09-28)
**UX:** F8 in-context pattern (`../ux/UserFlows.md`)

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Enables Notice rituals; never blocks MicroStart |
| Ritual | Pulses, Speak Time only |
| Emotional state | Competence; no pleading |
| Metric | Grant rate after priming; denial ≠ loop failure |
| Anti-goal | A8 (no permission maze in onboarding) |
| Principle | P6, P9, P10 |

---

## 1. Permission inventory

| Permission | When asked | If denied |
|---|---|---|
| Notifications | User enables pulses or Speak Time carrier | Settings deep link; core loop intact |
| Exact alarms (Android 12+) | Enabling Speak Time / precise pulses | Drift honesty copy; coarser schedule |
| Foreground service (Android) | Only if H15 forces Speak Time FGS | Feature limited |
| Battery exemption (OEM) | Optional help screen after detected kills | Documented; never required for MicroStart |

**Never asked:** contacts, location, microphone (recording Horizon 2),
motion, photo library, tracking/ATT (no ads), usage-access/screen-time.

## 2. Flow

1. User toggles ritual on.
2. Priming line in active Voice display label / VoiceId tone.
3. OS dialog.
4. Persist grant state; serve S8 copy if denied.

## 3. Onboarding

Zero OS permission dialogs (P6). Invitations only.

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

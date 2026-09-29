# Notification Architecture

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 (2026-09-28)
**UX contract:** `../ux/NotificationStrategy.md`

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Rest→Notice→Offer; Reflection via N2 |
| Ritual | Midday Reset, Morning Awareness, Evening Reflection, MicroStart close |
| Emotional state | Hand-on-shoulder; never alarm theater |
| Metric | Action rate; respectful-silence activations; zero unsolicited count=0 |
| Anti-goal | A3, A6; P5 re-engagement ban |
| Principle | P2, P5, P9 |

---

## 1. Types (exhaustive — matches UX N1–N5)

| Code | Trigger | Actions |
|---|---|---|
| `PulseNotification` | AwarenessScheduler | MicroStart, QuietToday |
| `MicroStartCompletedNotification` | Session end backgrounded | Open Completion, Again |
| `MicroStartRunningNotification` | Session running | Stop |
| `SpeakTimeCarrierNotification` (iOS) | Speak Time schedule | MicroStart |
| `ForegroundServiceNotice` (Android, if required) | Speak Time reliability | Open Settings |

**Structurally absent** (do not add these types): `ReEngagement`,
`WeMissYou`, `ComeBack`, `YourStreakIsBreaking`, marketing, setup nag.
A lapse is handled when the user returns (Fresh Start). Do not manufacture
anxiety to raise retention. Adding any such type requires a Product
Decision and a BehaviorArchitecture row.

## 2. AwarenessScheduler

Inputs: WakeWindow, pulse cadence, quiet hours, QuietToday, Focus/DND,
MicroStart running?, respectful-silence level, FreshStartFlag (content
only).

Outputs: scheduled platform notifications with ContentEngine line
(`VoiceId`, slot, temperature-filtered).

Rules from UX: suppress while MicroStart running; post-complete cooldown;
landmark restyles morning pulse content, never adds volume.

## 3. RespectfulSilenceEngine

```
ignored_streak >= threshold → downgrade cadence → floor pause
restore = explicit Settings only
```

Persists level locally; emits analytics `awareness_silence_downgraded`
(aggregate).

## 4. Platform notes

- **iOS:** UNNotificationRequest budgets; Speak Time = pre-rendered sound
  assets per HH:MM boundary; Focus respected; no critical alerts.
- **Android:** Notification channels (`awareness`, `microstart`,
  `speak_time`); exact alarms permission path in Permissions.md.

## 5. Deep links

`wake://microstart/start` → MicroStartService.start()
`wake://now` → Now
`wake://microstart/complete` → Completion
Trampoline-free on Android where possible (cold-start budget).

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

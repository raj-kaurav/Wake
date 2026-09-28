# Background Services

**Phase:** 3 — Technical Planning
**Status:** Approved / frozen with Phase 3 — Android Speak Time path is
**not** locked; see `Spikes.md` H15 (D-015)

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | → Notice (Speak Time); MicroStart completion reliability |
| Ritual | Midday Reset / Awareness; MicroStart |
| Emotional state | Neutral lighthouse; trust (kept schedules) |
| Metric | H14/H15; completion never lost |
| Anti-goal | A2 (default 60 min); battery abuse ≠ trust |
| Principle | P8 honesty, P9, P10 |

---

## 1. Responsibilities allowed in background

1. Fire scheduled pulses / Speak Time boundaries.
2. Complete MicroStart when app killed.
3. Update widget timelines at coarse steps.
4. Flush analytics queue (opportunistic).

**Not allowed:** fetch motivational feeds, geofence stalking, always-on mic,
background social sync.

## 2. Speak Time — Android (spike-gated)

**Do not assume a foreground service is required.** H15 (`Spikes.md`) must
supply evidence. The rule is: use the **least intrusive** platform
mechanism that can reliably deliver the behavior.

Until H15 evidence exists, the architecture only commits to:

- Schedule boundaries inside the wake window.
- On-device TTS utterance "It's HH:MM."
- Audio-focus policy: skip during calls; duck or skip during media per
  setting; defer if a screen reader is speaking.
- Honest degradation when exact delivery is impossible: tell the user
  timing may drift, or disable Speak Time on that device — never pretend
  precision (`ProductPrinciples` P8).

A foreground service is **out of the default design**. If H15 shows it is
the minimum viable path, a Decision Log entry must record why, when it
activates, how long it runs, its notification, battery impact, user
visibility, failure modes, and fallback. Possibility alone is not a reason
to add one.

Permissions that *might* be involved (`SCHEDULE_EXACT_ALARM` or equivalent)
stay in `Permissions.md` and are requested only if the chosen mechanism
needs them.

## 3. Speak Time — iOS

No arbitrary background TTS. **Carrier notifications** with pre-rendered
audio assets for each quarter-hour (or configured interval grid) across
24h. Schedule rolling window of requests within pending limits. Honor
Focus. Document tier in Settings (D9).

## 4. MicroStart completion

On start: schedule absolute completion callback (notification + state
finalize). On foreground resume: reconcile. Never drop a ≥20s start
without Completing path.

## 5. Doze / App Standby / OEM

Device lab matrix (Pixel, Samsung, Xiaomi minimum). BatteryOptimization
doc owns user-facing guidance when OEM restricts.

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

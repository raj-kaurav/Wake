# Technical Spikes — H13, H14, H15

**Phase:** 3 — Technical Planning
**Status:** Planned — **not executed**
**Rule:** Do not convert a spike into a permanent architecture decision
without filling Evidence and Decision below. Opinion is not evidence.

---

## Spike template

Each spike uses:

## Question
## Hypothesis
## Experiment
## Platform
## Evidence
## Constraints
## Product Impact
## Architecture Impact
## Decision
## Confidence

---

## H13 — Widget Fidelity

### Question
Can Day Dots (and the renderer shell) communicate finite-day awareness
honestly within WidgetKit and Android widget update budgets, without
implying minute-level motion the OS will not deliver?

### Hypothesis
15-minute stepped Day Dots plus date-relative caption text will feel
intentional on both platforms (not "broken").

### Experiment
Minimal widget shells rendering wake-window progress at 15-minute steps
for a full wake window; measure refresh counts, stale intervals, caption
accuracy, cold-start MicroStart from widget, accessibility summary.

### Platform
Both.

### Evidence
*Not yet collected.*

### Constraints
*To be filled from platform APIs during the spike (WidgetKit timeline
budget, Android update intervals).*

### Product Impact
Determines whether Default V1 Day Dots ships as specified or needs a
coarser caption strategy. Does **not** by itself pick a long-term renderer.

### Architecture Impact
Validates `DayShapeRenderer` boundary: domain exposes time-awareness state
only; geometry stays in the renderer.

### Decision
**Deferred** until evidence exists.

### Confidence
Low (no experiment yet).

---

## H14 — Cross-platform / native capability

### Question
For each candidate in `FrameworkDecision.md` (A/B/C), which platform
capabilities required by MVP rituals are first-class vs bridge-degraded?

### Hypothesis
Widget actions, exact-ish scheduling, notification actions, and TTS differ
enough that candidate C may fail criterion 1 or 4.

### Experiment
Capability matrix per candidate: widget deep link latency, notification
actions, TTS, reduced-motion, dynamic type, local storage — scored against
the ten criteria in FrameworkDecision.md. No production app.

### Platform
Both.

### Evidence
*Not yet collected.*

### Constraints
*To be filled.*

### Product Impact
May eliminate a candidate that cannot preserve behavioral UX.

### Architecture Impact
Feeds FrameworkDecision final row. Until then framework stays OPEN.

### Decision
**Deferred.**

### Confidence
Low.

---

## H15 — Speak Time / background execution

### Question
What is the **least intrusive** Android mechanism that can deliver periodic
spoken time reliably? Is a foreground service required? What honest
degradation applies when exact delivery is impossible?

### Hypothesis
Exact alarms (or inexact alarms within a stated tolerance) plus a short-lived
worker and on-device TTS can meet a 60-minute default **without** a
persistent foreground service. FGS is a fallback only if evidence shows
otherwise. *(Hypothesis — not an architecture lock.)*

### Experiment
On current Android versions and at least Pixel, Samsung, and one aggressive
OEM (e.g. Xiaomi): schedule 60-minute and 15-minute utterances across Doze;
compare (1) inexact alarms, (2) exact-while-idle alarms, (3) FGS. Record
drift, kills, battery, notification requirements, whether audio playback
itself forces a service type, and Play policy notes. Define minimum viable
path as the least intrusive option that meets a pre-written reliability bar
(proposal: ≥95% of expected utterances within ±2 minutes at 60-minute
interval over 24h on Pixel; OEM variance documented not hidden).

### Platform
Android (iOS Speak Time remains notification-sound tier; not this spike's
decision).

### Evidence
*Not yet collected.*

### Constraints
*To be filled: Doze, exact-alarm permission, background limits, audio
focus, policy.*

### Product Impact
If exact delivery is impossible: **honest degradation** — Settings copy
states drift or disables Speak Time rather than pretending precision.
Default interval remains 60 minutes. 15-minute mode may be withheld on
devices that cannot support it honestly.

### Architecture Impact
`BackgroundServices.md` must not assume FGS. If evidence later requires FGS,
document why, when it activates, duration, notification, battery, user
visibility, failure modes, and fallback — in a Decision Log entry. Do not
add FGS because it is possible.

### Decision
**Deferred.** No FGS in the architecture by default.

### Confidence
Low.

---

## Adoption rule

A spike Decision may be Adopted / Rejected / Deferred only after Evidence
is filled. FrameworkDecision.md and BackgroundServices.md link here; they
do not duplicate unverified claims.

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

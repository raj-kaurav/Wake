# User Research Hypotheses & Validation Plan

**Phase:** 1 — Product Documentation
**Status:** Draft for review
**Source:** Consolidates `../research/OpenQuestions.md` into a structured
research program. Each hypothesis is falsifiable, owned by a validation
method, and mapped to the decision it unblocks.

---

## 1. Research Principles

- We validate **mechanisms and feelings**, not feature enthusiasm. "Would
  you use this?" is banned; observed behavior and recalled specifics only.
- Churned and lapsed users are first-class research subjects — the product
  is *for* the lapse (P3).
- Where the mechanic is unvalidated in the literature (widget effect,
  spoken time), the shipped product itself is the instrument (P12):
  variants ship behind remote configuration and honest, minimal analytics.
- Ethics: research participants are procrastinators discussing a source of
  shame; interview protocols follow the same no-shame contract as the
  product (P4).

## 2. Hypothesis Register

### Cluster A — Core mechanism (decides: MVP composition)

| ID | Hypothesis | Method | Decision unblocked |
|---|---|---|---|
| H1 | Ambient day-shape visualization increases daily start actions vs. no widget | Post-launch A/B (widget prompt vs. none); pre-launch: 1-week diary study with lookalike widget | Widget's priority and marketing claim strength |
| H2 | Opportunity framing ("6h left") activates; depletion framing ("71% gone") threatens high-anxiety users without helping others | Prototype interviews (n≈12, mixed anxiety self-report) + shipped variant test | Default widget framing; voice-specific framing defaults |
| H3 | A 2-minute default start beats 5-minute on start *rate*; 5 beats 2 on continue-after-timer rate | Remote-config duration experiment post-launch | Default timer length; whether duration is user-visible setting |
| H4 | The end-of-timer moment (honest stop vs. quiet continue) determines repeat usage more than the start moment | Moderated prototype tests of 3 end-states; retention curves by observed end-behavior | Start Now completion design |
| H5 | Spoken time at 30–60 min intervals retains awareness effect ≥2 weeks; 15-min habituates within days | 2-week beta cohort with interval telemetry + weekly 1-question pulse | Speak Time defaults; whether 15-min ships at all |

### Cluster B — Emotional register (decides: voice system defaults)

| ID | Hypothesis | Method | Decision unblocked |
|---|---|---|---|
| H6 | ≥25% of users choose the challenging voice when previews are shown; choice without previews skews toward self-punishment expectations | Onboarding prototype test with/without preview lines | Whether voice preview is mandatory in onboarding |
| H7 | Users in the guilt spiral (self-reported) who choose The Coach show worse week-1 sentiment than Coach-choosers overall — unless preview calibrated expectations | Beta onboarding pulse + week-1 pulse, segmented | Safety design of the voice-choice step; possible soft check-in |
| H8 | After one week, users describe Wake as "calming/clarifying" not "pressuring" (≥70% of active users) | Week-1 single-question in-app pulse + interviews with detractors | The entire emotional-register bet; triggers §6 of the Opportunity Report if failed |
| H9 | Weightless re-entry (no comment on absence) measurably improves return-after-lapse rates vs. industry-standard "we missed you" (we will not ship the latter; comparison is against published benchmarks and qualitative report) | Lapsed-user interviews; return-rate telemetry | Confidence in P3 as retention strategy, not just ethics |

### Cluster C — Audience & positioning (decides: marketing, channels)

| ID | Hypothesis | Method | Decision unblocked |
|---|---|---|---|
| H10 | "Time awareness app" framing outperforms "anti-procrastination app" framing in comprehension and appeal for Tier-1 segments | Landing-page copy test; store-listing A/B where platform allows | Category language everywhere |
| H11 | Students (S1) and independent knowledge workers (S2) show the strongest activation; ADHD-adjacent users (S3) show the strongest retention | Beta cohort tagging (self-described, optional) | Beta recruiting mix; which persona leads store creative |
| H12 | The single optional intention field increases start completion without triggering todo-app expectations | Prototype test: button-only vs. button+intention variants | Whether intention field ships in MVP |

### Cluster D — Platform reality (decides: architecture; spikes, not user research)

| ID | Hypothesis | Method | Decision unblocked |
|---|---|---|---|
| H13 | iOS widget can feel "alive" within refresh budgets using date-relative rendering + coarse steps | Engineering spike (1–2 days) | Widget visual grammar (Phase 2/5) |
| H14 | iOS notification-sound Speak Time feels acceptable, not cheap; Focus modes don't swallow it in practice | Spike + hallway test on device | Speak Time iOS tier ships in MVP or v1.x |
| H15 | Android exact alarms + TTS survive aggressive OEM battery management at 60-min intervals | Device-lab spike (Samsung, Xiaomi, Pixel) | Foreground-service requirement; battery copy |

## 3. Validation Program (sequenced)

**Wave 1 — Concept & framing interviews (pre-design, ~2 weeks of effort)**
n≈12–15 across S1/S2/S3, screened for self-reported chronic procrastination;
includes ≥4 users who abandoned a productivity app in the last 90 days.
Instruments: lookalike widget images (H2), voice sample cards (H6),
"yesterday reconstruction" interviews (validates personas; no leading).
Output: revised personas, framing defaults, voice-preview decision.

**Wave 2 — Prototype tests (during Phase 2 UX work)**
Clickable prototype: onboarding → widget add → first start → timer end.
Tests H4, H6, H12; measures decision count and time-to-first-start against
the P6 budget (60 seconds).

**Wave 3 — Engineering spikes (during Phase 3)**
H13–H15. Two days each, written findings appended to architecture docs.

**Wave 4 — Instrumented beta (pre-launch, 4–6 weeks)**
100–300 users recruited across segments (deliberate S3 inclusion). Tests
H1 (prompted-vs-not widget), H3, H5, H7, H8, H11. Analytics per the P11
contract: minimal, aggregate, disclosed.

**Continuous — post-launch experimentation**
H1/H2/H3 variants via remote config; quarterly lapsed-user interview
cycles (H9).

## 4. Failure Criteria (what would force redesign)

- H8 fails (users feel pressured) → redesign awareness layer around
  opportunity framing / reduce default intensity; re-run Wave 1.
- H1 fails outright (widget no effect on starts) → widget remains as brand
  surface but marketing claims retreat to Start Now; thesis adjusted
  honestly (P12, P8).
- H6 shows challenging voice <10% uptake → voice system simplifies to
  nurturing + settings-level "directness" slider consideration in v2.
- H14/H15 fail → Speak Time ships Android-only (H15 pass) or moves to
  v1.x pending platform changes.

## 5. Research Ethics Notes

Informed consent for all interviews/beta telemetry; no deception; no dark
prototype patterns "just to test"; distress protocol in interview guide
(pause, no probing, signpost resources) consistent with
`../research/EthicalConsiderations.md` §4.3.

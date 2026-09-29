# Success Metrics

**Phase:** 1 — Product Documentation
**Status:** Draft for review
**Purpose:** Define what we measure, what we refuse to measure as success,
and the guardrails that keep measurement honest. Instrumentation
architecture (events, storage, opt-out) is Phase 3 (`Analytics.md`); this
document is the contract it implements.

**The founding measurement decision (ratified in Phase 0 review):** Wake's
success metrics measure **user action in real life**, never attention
captured. Session length, opens, and time-in-app are guardrails to keep
*low*, not KPIs. This inversion is what keeps the ethics durable under
commercial pressure (P5).

---

## 1. North-Star Metric

> **Weekly Started Users (WSU):** users who completed ≥1 honest two-minute
> start in the trailing 7 days.

Supported by the intensity metric **starts per active user per day**
(median, not mean — we care about the typical user, not power-user tails).

Why "starts," precisely: a start is the product's entire theory of change
made observable (Pillar II). It is also gameable only by the user actually
doing the thing we exist for — the safest possible metric to optimize.

Definition details: a start counts when the timer is launched *and* not
cancelled within the first 20 seconds (anti-accidental-tap floor); no
distinction between continued and stopped-at-two-minutes sessions (both are
full wins — P8 demands the metric agree with the copy).

## 2. The Funnel (acquisition → activation → repetition → resilience)

| Stage | Metric | Target (initial, honest guesses to be recalibrated in beta) |
|---|---|---|
| Onboarding integrity | % completing onboarding in ≤60 s and ≤5 decisions | ≥80% |
| **Activation** | % of new users with a first start in session one | ≥50% |
| Awareness adoption | % adding the widget in week one; % enabling any pulse/Speak Time | ≥40% / ≥30% |
| **Repetition** | Resilient adoption: started on ≥3 of first 14 days | ≥25% of activated |
| **Resilience** | Return-after-gap: ≥7-day absence followed by a start within the next 14 days | ≥20% of lapsed |
| Retention proxy | D30 WSU retention | benchmark-honest; category norm is 5–10%, we aim to beat it without ever buying it with engagement mechanics |

Resilience is a first-class stage — most products measure churn; we
additionally measure *recovery*, because the lapse is our designed moment
(P3, H9).

## 3. Mechanism Metrics (the P12 evidence program)

| Bet | Metric |
|---|---|
| Widget causes starts (H1) | Widget-cohort vs. no-widget-cohort starts/day; widget-glance-adjacent starts (where measurable within privacy contract) |
| Framing (H2) | Start rate + H8 sentiment by framing variant |
| Duration default (H3) | Start rate and continue-rate by 2/3/5-min remote-config arm |
| Speak Time value (H5) | Enabled-retention curve; interval churn; starts within 10 min of a spoken pulse |
| Voice system (H6/H7) | Voice choice distribution; switch patterns; sentiment by voice |
| Content anti-habituation (R1) | Pulse→start conversion decay slope per content-variant depth |

## 4. Emotional-Safety Metrics (G4 — veto power)

- **Week-1 sentiment pulse:** single in-app question ("Wake mostly feels:
  calming / clarifying / pressuring / nagging"), target ≥70%
  calming+clarifying, alarm at >15% pressuring+nagging (H8).
- **Aversive-use signals** (research input only, never triggers messaging):
  widget removal <48h after add; Speak Time disabled <24h after enable;
  Coach→Friend switches following low-activity days.
- **Review/support language monitoring:** shame/anxiety mentions tracked as
  incidents, each triaged against content and defaults.

## 5. Guardrail Metrics (kept LOW or at bounds — the anti-metrics)

| Guardrail | Bound | Rationale |
|---|---|---|
| Median session length (non-timer) | ≤ 30 s, and must not grow | The app is a doorway (P5); growth here means we built a destination |
| Time from app-open to start-tap | ≤ 10 s median | Friction telemetry for Pillar II |
| Notifications delivered per user-day | ≤ user's own schedule, hard cap; zero unsolicited | P9; volume growth is a defect, not reach |
| Notification disable/uninstall following pulses | tracked per content-slot | Early R1/R9 warning |
| Onboarding decision count | = 5 max, enforced as a test | P6 erosion tripwire |
| % of starts preceded by an app-initiated prompt vs. self-initiated | watch for prompt-dependence rising over user lifetime | Graduation thesis: self-initiated share should *grow* with tenure |

That last row operationalizes the vision's strangest claim: **a maturing
user should need our prompts less.** Prompt-dependence declining with
tenure = the product is working; the commercial instinct says opposite;
the constitution decides (P5).

## 6. Business Metrics (subordinate tier)

Organic install growth by channel/segment (H10/H11); store rating with
review-language quality (not just stars); post-monetization (model TBD):
conversion measured *only* against cohorts with healthy G-metrics — we do
not monetize users the product isn't helping (ethics floor,
`../research/EthicalConsiderations.md` §4.5).

## 7. Measurement Ethics Contract (implements P11 — binding on Phase 3 `Analytics.md`)

1. Minimal event set, aggregate analysis; no ad IDs, no third-party data
   sale/sharing, no fingerprinting.
2. Analytics disclosed in plain language; opt-out honored without feature
   loss.
3. Intention-string content is never transmitted (local only, permanently).
4. Segment analyses (H7, aversive-use) protect n-sizes; no individual-user
   targeting derived from distress signals — research input only.
5. No metric may be displayed back to users as a performance record (P1) —
   measurement is for building, not for judging users.

## 8. Review Cadence

Metrics reviewed at each phase gate pre-launch; weekly during beta; the
target numbers in §2 are explicitly provisional and get one recalibration
at beta-end before they become accountability numbers (avoids goodharting
guesses).

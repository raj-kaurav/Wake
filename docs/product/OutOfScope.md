# Out of Scope

**Phase:** 1 — Product Documentation
**Status:** Draft for review
**Purpose:** The explicit exclusion list. Three tiers: **constitutional**
(never, absent a constitutional amendment), **declined** (evaluated and
refused; revisit requires new evidence), and **deferred** (wanted later;
parked with entry gates in `FeatureRoadmap.md`). Scope creep is this
product's most likely cause of death (risk R8) — this document is the
tripwire.

---

## Tier 1 — Constitutional Exclusions (violate `ProductPrinciples.md`)

| Exclusion | Principle violated | Note |
|---|---|---|
| Task lists, projects, multiple stored intentions | P7 | The single replaceable intention string is the permanent maximum |
| Schedules, time-blocking, day planning | P7 | No plans that can break |
| Streaks, chains, badges, levels, points | P3, P5 | Includes "resilient streak" euphemisms shown to users |
| Statistics dashboards, reports, histories | P1 | Includes "gentle" weekly summaries — the past is not a surface |
| Re-engagement & marketing notifications | P5, P4 | "We miss you" is banned output, permanently |
| Engagement mechanics (feeds, variable rewards, collectible content) | P5 | The app must stay too sparse to binge |
| Manufactured urgency, fake scarcity, auto-extending timers | P8 | Honest mechanics only |
| Accounts required for core features; behavioral data sale/sharing | P11 | Local-first is constitutional |
| Manager/team visibility, enterprise admin | P11, vision | Wake is personal, full stop |
| Shame-based content in any voice | P4 | Enforced per-line by the ethics checklist |

## Tier 2 — Declined After Evaluation (Phase 0 verdicts stand)

| Exclusion | Where declined | Reopening condition |
|---|---|---|
| Regret simulation | `FeatureIdeaAssessment.md` §6 — failed ethics at concept | None foreseen; deliberate negative-affect induction contradicts the evidence base |
| Screen-time awareness / app-usage reports | Same — F6 failure mode, OS-owned surface, permission-heavy | OS-level APIs changing the privacy/effort equation *and* a P1-compatible design |
| Cloud AI coach / conversational agent | Same — subscription economics, privacy posture, therapy-adjacent claims | On-device inference + a reviewable (non-generative-at-runtime) content path + a job description no simpler mechanism serves |
| Ambient sounds / focus music | Same — commodity, media-app scope creep | None foreseen; better served by dedicated audio products |
| Habit-insight dashboards | Same — anti-vision | Only the single "rhythm hint" concept may ever be heard, via Horizon 3 review |
| Social accountability features / body-doubling network | `MarketGaps.md` (declined gaps) | A design that adds zero moderation surface and violates no privacy principle — considered unlikely |
| Pomodoro work-cadence management (25/5 cycles, session planning) | Product constraint from the brief; `FeatureIdeaAssessment.md` §5 | None — the timer is an ignition device, not a cadence manager |

## Tier 3 — Deferred (wanted, parked behind gates in `FeatureRoadmap.md`)

- **"The Stoic" philosophy pack** (Death Clock / Memento Mori recast):
  optional voice + reflective life-scale faces, **disabled by default,
  explicit consent, dedicated ethics review** — post-MVP by decision of the
  Phase 0 review.
- Lock-screen widgets; watch complications; live wallpaper (Android).
- Calendar-aware time granularity (read-only, if research demands it).
- Voice-recorded self-prompts ("message from past-you").
- Speak Time iOS parity beyond the notification-sound tier.
- Localization beyond English (content-cost decision:
  `MicrocopyStrategy.md` §3.5).
- Tablet/desktop surfaces.
- Framing/duration user-facing personalization (until H2/H3 data earns it).
- Monetization implementation (model selection post-validation; ethics
  floor pre-committed).

## MVP-Specific Exclusions (in scope for the product, not for v1)

Covered in `MVPDefinition.md` §3; notable repeats for emphasis: no
accounts/sync, no data export UI (nothing worth exporting exists), no
in-app purchase scaffolding, no A/B framework beyond remote config of
H-series variants.

## Scope-Creep Tripwires (how drift will actually look)

Team self-checks, to be embedded in the Phase 4 review checklist and
Phase 6 rules:

1. "Users are asking for a way to see their past starts" → P1/P3 pressure.
   Answer: no. Offer nothing; measure the ask (it informs the Horizon 3
   rhythm-hint review, not a dashboard).
2. "Just one more intention slot — people have two projects" → P7's exact
   failure mode. The second slot is a todo list's first cell.
3. "A tiny streak would boost D7 retention" → it would; it also converts
   the product into what it exists to replace (P3, P5).
4. "The completion screen could suggest going for 10 more minutes" →
   bait-and-switch; P8. Continuation is the user's silent act, never our
   pitch.
5. "Let's add a setup step to personalize better" → P6 erosion; onboarding
   decisions are capped at five, forever.

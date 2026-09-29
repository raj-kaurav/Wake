# Architecture Overview

**Phase:** 3 — Technical Planning
**Status:** **APPROVED / FROZEN** (2026-09-28)
**Mission:** Protect the behavioral philosophy from technical entropy.

> Engineering exists to preserve the behavioral philosophy, not to create
> opportunities for technical complexity.

**Canonical refs:** `BehaviorArchitecture.md` (API-equivalent contract) ·
`../product/LanguageSystem.md` · `../product/ProductPrinciples.md` ·
`../product/ProductDecisionLog.md`

---

## 1. Architectural thesis

Wake is a **local-first, ritual-shaped, MicroStart-centered** mobile
client. The codebase is organized so that:

- Illegal product concepts (task lists, streaks, histories, engagement
  feeds) are **structurally hard to add** (no modules, no models, no
  tables for them).
- Legal rituals map to clear modules with explicit BehaviorArchitecture
  mappings.
- Platform differences (widgets, Speak Time) are **tiered honestly**, not
  papered over.

## 2. Mapping template (mandatory on every technical proposal)

| Field | Required answer |
|---|---|
| Behavior transition | from BehaviorChangeModel |
| Ritual | from LanguageSystem ritual set |
| Emotional state | from EmotionalJourney / Temperature |
| Success metric | from SuccessMetrics |
| Anti-goal | from AntiGoals |
| Product principle | from ProductPrinciples |

## 3. System context

```
┌─────────────────────────────────────────────────────────┐
│                     Device (offline-capable)              │
│  ┌──────────┐  ┌─────────────┐  ┌─────────────────────┐ │
│  │ DayDots  │  │ Notifications│  │ App (6 screens)     │ │
│  │ Widget   │  │ Pulses/N2-N5 │  │ Now/Timer/Settings  │ │
│  └────┬─────┘  └──────┬──────┘  └──────────┬──────────┘ │
│       └───────────────┴─────────────────────┘             │
│                         │                                 │
│              ┌──────────▼──────────┐                      │
│              │   Domain Core       │                      │
│              │ MicroStartService   │                      │
│              │ ContentEngine       │                      │
│              │ AwarenessScheduler  │                      │
│              │ VoicePreference     │                      │
│              │ FreshStartFlag      │                      │
│              └──────────┬──────────┘                      │
│                         │                                 │
│         ┌───────────────┼───────────────┐                 │
│         ▼               ▼               ▼                 │
│   Local Store     On-device TTS    Optional Analytics     │
│   (prefs/db)      (Android)       (opt-in, aggregate)    │
└─────────────────────────────────────────────────────────┘
         │
         ▼  (optional, never required for core loop)
   Privacy-preserving analytics endpoint
```

**No account service. No sync backend for MVP. No cloud TTS. No content CDN
required** (packaged corpus).

## 4. Cross-cutting architectural decisions

| Decision | Choice | Mapping (abbrev.) |
|---|---|---|
| Client shape | **OPEN** — candidates A/B/C in `FrameworkDecision.md`; evidence via `Spikes.md` H13–H15 | All rituals; P10/P11 |
| Data | Local-first store; MicroStart sessions ephemeral | P1/P3/P11 |
| Content | Versioned on-device pack; VoiceA/B + Temperature mandatory | Content Engine; P4 |
| Time | Device clock + user wake window; no server time | Notice rituals |
| Identity | None (no auth) | P6/P11 |
| Creep firewall | No Task/Streak/History modules exist; CI/arch tests forbid them | P7; OutOfScope |

## 5. Document map (Phase 3)

| Doc | Owns |
|---|---|
| `AppStructure.md` | Modules, layers, creep firewall |
| `OfflineStrategy.md` | Local-first guarantees |
| `StateManagement.md` | Session/UI/domain state |
| `NotificationArchitecture.md` | Pulses, respectful-silence |
| `WidgetArchitecture.md` | Shell + renderers |
| `WidgetEvolutionProgram.md` | V1 vs long-term |
| `BackgroundServices.md` | Speak Time, alarms, Doze |
| `Permissions.md` | In-context permission flows |
| `AccessibilitySupport.md` | Platform a11y implementation |
| `Localization.md` | VoiceA/B string model |
| `Performance.md` | Cold-start / MicroStart budgets |
| `BatteryOptimization.md` | Speak Time / widget budgets |
| `Privacy.md` / `Security.md` | P11 / threat model |
| `Analytics.md` | WSU / MicroStart events |
| `AnalyticsPrivacy.md` | Install-token identity, minimization, opt-out |
| `FrameworkDecision.md` | Candidates A/B/C; decision OPEN |
| `Spikes.md` | H13, H14, H15 evidence protocol |
| `FutureArchitecture.md` | Stoic pack, watch, etc. |

## 6. Non-goals of this architecture

Backend multiplayer · recommendation ML · cloud accounts · plugin
marketplaces · theming engines · "insights" data warehouses · Task,
Streak, History, Social, Account, Leaderboard, Achievement, or
engagement-score modules. Each would violate the constitution or
AntiGoals unless a future Product Decision changes the constitution.

## 7. Complexity firewall

Every technical component must answer, before it is added:

- What MVP behavior requires this?
- What problem does it solve?
- Can it be simpler?
- Can it remain local?
- Does it increase maintenance burden?
- Does it create future scope pressure?

Prefer simple, local, replaceable, testable, and boring over prematurely
scalable, distributed, over-engineered, or engagement-oriented.

## 8. Anti-goal firewall

Every new subsystem must answer: **Could this subsystem cause Wake itself
to become procrastination?** Also check compulsive checking, notification
dependence, scorekeeping, productivity-identity pressure, punishment,
shame, engagement substitution, and unnecessary session length. Longer
sessions are a warning, not a success (`../product/SuccessMetrics.md`).
Mitigation is required before approval (`../ux/AntiGoals.md`).

## 9. Local-first core

These do not depend on a backend: time awareness, widget rendering,
MicroStart, Fresh Start, local content, Speak Time where the platform
permits, notification scheduling where the platform permits, core state
transitions. A later backend must be additive. MVP is not designed around
authentication, cloud sync, social identity, server profiles, or mandatory
API availability.

## 10. Ritual vs infrastructure language

Ritual names belong at the domain/product layer. Low-level infrastructure
(queues, schedulers, storage) need not be renamed "ritual" where that adds
no technical value. Do not introduce a generic Feature domain.

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

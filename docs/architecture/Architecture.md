# Architecture Overview

**Phase:** 3 — Technical Planning
**Status:** Draft for review
**Mission:** Protect the behavioral philosophy from technical entropy
(Phase 3 authorization). Engineering convenience is subordinate to
behavioral consistency, simplicity, ethical persuasion, platform honesty,
and maintainability.

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
| Client shape | Native-per-platform shells + shared domain where practical; framework choice in AppStructure (spike-informed) | All rituals; P10/P11 |
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
| `FutureArchitecture.md` | Stoic pack, watch, etc. |

## 6. Non-goals of this architecture

Backend multiplayer · recommendation ML · cloud accounts · plugin
marketplaces · theming engines · "insights" data warehouses. Each would
violate the constitution or AntiGoals.

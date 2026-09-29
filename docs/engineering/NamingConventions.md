# Naming Conventions

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Vocabulary:** `../product/LanguageSystem.md`. Do not invent synonyms.

---

## Product tokens (canonical, case varies by language)

| Concept | Token |
|---|---|
| Two-minute intervention | `MicroStart` |
| Ephemeral run | `MicroStartSession` |
| Return flag | `FreshStart` / `FreshStartFlag` |
| Scheduled awareness | `AwarenessPulse` |
| Spoken clock | `SpeakTime` |
| Voice identifiers | `VoiceA`, `VoiceB` |
| Content platform | `ContentEngine` |
| V1 renderer | `DayDots` |
| Time-awareness state | `TimeAwarenessState` |

**Do not introduce** `Task`, `Streak`, `ProductivityScore`, `DailyGoal`,
`Achievement` unless a Product Decision approves them. `Session` alone is
ambiguous — qualify as `MicroStartSession`.

Display labels (`Coach`, `Friend`, future energy names) are **localization
keys**, never type names.

## Artifacts

| Artifact | Convention | Example |
|---|---|---|
| Folders | lowercase, one module | `microstart/`, `freshstart/` |
| Files | match the primary type | `MicroStartSession` |
| Classes / types | PascalCase product token | `MicroStartService` |
| Interfaces / ports | capability or noun | `SpeakTimeCapability`, `Clock`, `ContentPackSource` |
| Functions | verb + object | `startMicroStart`, `consumeFreshStartFlag` |
| Variables | camelCase, full words | `wakeWindow`, `freshStartFlag` |
| Constants | screaming snake or language idiom | `DEFAULT_MICROSTART_DURATION_MS = 120000` |
| Events | PascalCase product tokens | `MicroStartCompleted`, `PromptedStart`, `SelfInitiatedStart` |
| State enums | explicit lifecycle names | `Idle`, `Running`, `Completing` |
| Services | `…Service` for application orchestration | `MicroStartService` |
| Repositories | persistence ports only | `PreferencesRepository` |
| Adapters | platform suffix | `AndroidSpeakTimeAdapter` |
| Renderers | geometry name + `Renderer` | `DayDotsRenderer` |
| Platform bridges | `…Bridge` only at the UI/platform edge | `WidgetBridge` |

## User-facing copy vs code

Buttons may say "Start", "Start Now", "Begin", or "Just Start".
Code and events stay `MicroStart`. Do not rename domain types when copy changes.

## Events

Match `../architecture/Analytics.md`. New events require a schema version
note in `AnalyticsEngineering.md` and must not encode shame or scores.

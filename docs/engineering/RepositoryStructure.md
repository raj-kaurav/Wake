# Repository Structure

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Constraint:** Framework is **OPEN** (`../architecture/FrameworkDecision.md`).
This document defines **logical** boundaries, not a locked language tree.
Do not create these directories as a production app in Phase 4.

---

## Logical layout

```
docs/                  product, UX, architecture, engineering (this phase)
content/               versioned content packs (data, not UI strings)
domain/                platform-independent behavior
application/           use cases orchestrating domain + ports
infrastructure/        adapters: storage, clock, analytics queue, content IO
platforms/android/     Android UI, widgets, alarms, TTS — only if candidate needs it
platforms/ios/         iOS UI, WidgetKit, notifications — only if candidate needs it
```

Candidate C (cross-platform UI) may place UI outside `platforms/`, but
**widget, Speak Time, and exact scheduling adapters still live behind
ports** and may be native. Candidate A shares `domain/` and `application/`.
Candidate B may duplicate domain only if contract tests stay identical —
duplication is a cost, not a license to drift.

## Module boundaries

Match `../architecture/AppStructure.md`:

| Module | Layer | Notes |
|---|---|---|
| `microstart` | domain + application | Not a generic task engine |
| `awareness` | domain | Wake window, day progress math |
| `freshstart` | domain | Boolean flag only |
| `content` | domain selection + infrastructure load | Schema in ContentEngineering |
| `voice` | domain id + edge label resolver | `VoiceA` / `VoiceB` only in domain |
| `notifications` | application + platform adapter | No re-engagement type |
| `widget` | application state + platform renderer | Renderer ≠ source of truth |
| `speaktime` | port + platform capability | supported / partial / unavailable |
| `analytics` | infrastructure only | Never imported by domain |
| `settings` | application | ≤12 settings budget is a product rule |

## Public vs internal APIs

- **Public (inside the repo):** application use-case interfaces and domain
  types that UI and adapters may call.
- **Internal:** state-machine steps, content index layout, queue file format.
- UI and platforms depend on application interfaces, not on infrastructure
  concretes.
- No `internal` type from `domain` may mention a platform SDK.

## Shared vs native

| Shared | Native / platform |
|---|---|
| MicroStart transitions, FreshStart rules, content selection, day-progress math, event *names* | Widget timelines, notification scheduling, TTS, exact alarms, permission prompts |

Shared code must compile and test without Android or iOS SDKs.

## What must not appear

Folders or modules named `task`, `todo`, `streak`, `history`, `social`,
`account`, `leaderboard`, `achievement`, `score`. Fitness checks:
`ArchitectureFitness.md`.

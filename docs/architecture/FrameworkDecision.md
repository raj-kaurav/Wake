# Framework Decision

**Phase:** 3 — Technical Planning
**Status:** **OPEN** — not selected (D-014)
**Date of this record:** 2026-09-28
**Decision date:** *pending H13–H15 evidence*

**Principle:** Do not select a framework because it is familiar, popular, or
faster to prototype. Selection waits for spike evidence.

---

## Purpose

Choose the client implementation shape that can honestly deliver widgets,
notifications, Speak Time, and MicroStart without diluting behavioral UX.

## Scope

MVP client only. Not a backend framework decision (there is no MVP backend).

## Candidates (all remain open)

| ID | Shape |
|---|---|
| **A** | Kotlin Multiplatform shared domain + native UI (Android + iOS) |
| **B** | Fully dual-native Android + iOS (duplicated domain, shared content pack + contracts) |
| **C** | Cross-platform UI framework + native platform bridges (widgets, alarms, TTS) |

## Evaluation criteria (priority order)

1. Widget fidelity (H13)
2. Background execution reliability (H15)
3. Notification reliability
4. Speak Time capability (H14/H15)
5. Platform-native behavior
6. Accessibility
7. Local-first architecture
8. Long-term maintainability
9. Ability to preserve the behavioral UX
10. Engineering complexity

Familiarity and prototype speed are **not** criteria.

## Spike evidence

| Spike | Status | Evidence |
|---|---|---|
| H13 Widget fidelity | **Not run** | None yet — see `Spikes.md` |
| H14 Cross-platform capability | **Not run** | None yet |
| H15 Speak Time / background | **Not run** | None yet |

Until those rows contain observed behavior, **framework selection remains
OPEN.** No candidate is rejected on opinion.

## Trade-offs (hypotheses only — not decisions)

| Candidate | Likely strength | Likely risk |
|---|---|---|
| A KMP + native UI | Shared MicroStart/Content domain; native widgets | Two UI codebases; KMP interop cost |
| B Dual-native | Maximum platform honesty | Domain drift between apps |
| C Cross-platform UI | One UI | Widget/TTS/alarm bridges may force fidelity hacks (forbidden) |

## Unresolved questions

- Can candidate C meet H13 without fake-parity animation?
- Does H15 require a foreground service on any target OEM? (must not assume yes)
- Is domain sharing (A) worth the bridge cost vs contract tests (B)?

## Final decision

**None.** Status: OPEN.

## Rejected alternatives

None yet. Rejection requires a spike Decision section with confidence.

## Consequences of remaining open

- Phase 4 standards must not assume a language/framework.
- Architecture contracts (BehaviorArchitecture, event names, content schema)
  are framework-agnostic.
- Implementation does not start in this phase.

## Behavioral mapping

| Field | Answer |
|---|---|
| Behavior transition | All — delivery vehicle |
| Ritual | All MVP rituals |
| Emotional goal | Platform honesty (trust) |
| Success metric | Spike pass/fail vs budgets in Performance/Battery |
| Anti-goal | A1/A8 if framework encourages heavy in-app chrome |
| Principle | P8, P10, P13; Widget principle: honesty over fake parity |

## Quality record

- **Technical decision:** Defer.
- **Alternatives:** A, B, C.
- **Rationale:** Evidence before lock (Phase 3 review).
- **Constraints:** No hacks for visual parity.
- **Failure modes:** Choosing early and discovering widget/Speak Time cannot be honest.
- **Privacy:** Framework must not require accounts or analytics SDKs for core loop.
- **Platform:** Android + iOS both in scope.
- **Testing:** H13–H15 protocol in `Spikes.md`.
- **Open questions:** See above.
- **Dependencies:** Spikes, WidgetArchitecture, BackgroundServices.

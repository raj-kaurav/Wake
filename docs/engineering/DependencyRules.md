# Dependency Rules

**Phase:** 4 — Engineering Standards
**Status:** Draft for review

---

## Allowed direction

```
Domain
  ↑ used by
Application
  ↑ used by
Infrastructure / Platform adapters
  ↑ used by
UI
```

Dependencies point **inward** toward domain. Domain defines ports
(interfaces). Infrastructure implements them. UI calls application use cases.

## Allowed

| From | To |
|---|---|
| Application | Domain |
| Infrastructure | Domain ports (implements) |
| Infrastructure | Application only when delivering a use-case result |
| UI | Application interfaces |
| UI | Design tokens (Phase 5), not domain internals |

## Prohibited

| Edge | Why |
|---|---|
| UI → domain implementation details (state-machine internals, pack index) | UI depends on use cases |
| UI → infrastructure concretes (SQL, alarm APIs) | Bypasses ports |
| Analytics SDK → domain behavior | Analytics must not change transitions |
| Domain → analytics | Domain stays analytics-independent |
| Domain → platform SDK, notification SDK, network client, storage impl, UI framework | DomainStandards |
| Network → core behavior | Offline-first |
| Platform SDK → domain | Domain must not import Android/iOS |

## Detection

`ArchitectureFitness.md` lists checks. Until a framework exists, review
enforces this. After a framework choice, encode the same rules in that
toolchain (arch unit tests, lint, import graphs). Do not pick the framework
in order to make lint easier.

## Mapping

| Field | Answer |
|---|---|
| Behavior transition | All — structure only |
| Ritual | All |
| Emotional goal | Trust via isolation of pressure mechanics |
| Metric | Fitness checks green |
| Anti-goal | A1, A4 — analytics and UI cannot invent scores in domain |
| Principle | P11, P13 |

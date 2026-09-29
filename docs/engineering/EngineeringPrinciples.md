# Engineering Principles

**Phase:** 4 — Engineering Standards
**Status:** Draft for review — documentation only; no implementation
**Authority:** Subordinate to `../product/ProductPrinciples.md`,
`../product/LanguageSystem.md`, `../product/ProductDecisionLog.md`, and
`../architecture/BehaviorArchitecture.md`. If a standard here conflicts with
those, **flag the conflict**. Do not silently change the architecture.

---

## Mission

> Convert the approved product and technical architecture into a consistent,
> enforceable engineering operating system.

Phase 4 defines **how** we build. It does not decide **what** we build.

> Protect the behavioral philosophy from technical entropy.

> Engineering exists to preserve the behavioral philosophy, not to create
> opportunities for technical complexity.

> The product is not successful because Wake keeps the user inside the app.
> The product is successful when Wake helps the user leave the app and start
> living the moment.

## Operating rules

1. **Traceability.** Product Principle → Product Decision → Behavior
   Architecture → Technical Architecture → Implementation. Implementation
   must not redefine product behavior.
2. **Six-field mapping.** Every meaningful change maps to behavior
   transition, ritual, emotional goal, success metric, anti-goal, and
   product principle — or it is incomplete.
3. **Local-first.** Core rituals do not require network, accounts, or
   analytics (`../architecture/Architecture.md` §9,
   `../architecture/AnalyticsPrivacy.md`).
4. **Creep firewall.** No Task, Streak, History, Social, Account,
   Leaderboard, Achievement, or engagement-score modules unless a future
   Product Decision changes the constitution.
5. **Platform honesty.** Do not fake Android/iOS parity. Do not claim exact
   Speak Time or live widget motion the platform cannot guarantee.
6. **Least mechanism.** Use the least intrusive platform mechanism that
   reliably delivers the behavior. Do not add a foreground service, backend,
   or SDK because it might be useful later.
7. **Analytics is subordinate.** If analytics fails, the app continues.
   Never show independence scores, streaks, or productivity scores.
8. **FreshStartFlag is a boolean.** No missed-day counters.
9. **Open decisions stay open** until evidence or explicit authorization:
   framework (H13–H15), Android Speak Time mechanism (H15), voice display
   names (Phase 5 branding), long-term widget identity (beta).
10. **Graceful degradation over false certainty** (`ErrorHandling.md`).

## Language-agnostic coding rules

These apply whichever candidate in `../architecture/FrameworkDecision.md`
is later chosen:

- Single responsibility per module.
- No duplicated ritual rules (one MicroStart state machine).
- No hardcoded user-facing strings (catalogs / content pack).
- No hardcoded colors (design tokens, Phase 5).
- No feature flags that enable prohibited domains (streaks, re-engagement).
- Flags may select experiment arms already allowed (duration, framing,
  renderer) with safe binary defaults.
- Configuration that changes constitutional behavior is forbidden.

## What this phase does not do

No production app, screens, services, schemas, endpoints, widgets, Speak
Time implementation, notification implementation, or dependency installation.

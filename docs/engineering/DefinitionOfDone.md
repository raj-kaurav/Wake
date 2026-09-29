# Definition of Done

**Phase:** 4 — Engineering Standards
**Status:** Draft for review

A change is **not** done because it compiles, tests pass, or a screen looks
right.

## Done means all of the following

1. **Product intent.** The change serves an approved ritual or a documented
   standard, and does not invent a new product behavior.
2. **Architecture.** Dependency rules and the creep firewall hold.
   BehaviorArchitecture mapping is written in the PR when the change is
   behavioral.
3. **Behavioral mapping.** Transition, ritual, emotional goal, metric,
   anti-goal, and principle are identified or explicitly not applicable
   (tooling-only).
4. **Privacy.** New data is absent or documented under PrivacyEngineering.
   Logs are clean.
5. **Accessibility.** New UI (when implementation exists) meets
   `../ux/Accessibility.md`, including cognitive load. Docs-only changes
   note "no UI."
6. **Anti-goals.** The AntiGoals misuse questions are answered for new
   surfaces or subsystems.
7. **Documentation.** Specs updated in the same change if behavior or
   architecture moved. Decision log updated if a decision moved.
8. **Testing.** Required tests from `TestingStrategy.md` exist or a
   follow-up is impossible to forget (linked issue). Behavioral cases for
   lapse and analytics failure are included when those paths are touched.
9. **Honesty.** Platform limits are stated. No false guarantee of exact
   timing or widget smoothness.
10. **Scope.** Phase gate allows the change. Implementation of the app is
    not done during Phase 4.

## Explicitly insufficient

- Green CI alone
- "Works on my device" without the offline and permission-denied cases
- A spike opinion recorded as a permanent framework or FGS decision
- Analytics dashboards that show users a score

# Phase 4 — Engineering Standards

**Status:** Draft for review. No application implementation.

Phase 4 defines how Wake is built. It does not decide what is built.
Authoritative inputs remain the frozen Phase 0–3 documents. Conflicts are
flagged, not silently patched.

> Protect the behavioral philosophy from technical entropy.

## Reading order

1. [EngineeringPrinciples.md](EngineeringPrinciples.md)
2. [RepositoryStructure.md](RepositoryStructure.md)
3. [NamingConventions.md](NamingConventions.md)
4. [DependencyRules.md](DependencyRules.md)
5. [DomainStandards.md](DomainStandards.md) — includes the MicroStart model
6. [StateManagementStandards.md](StateManagementStandards.md)
7. [NotificationStandards.md](NotificationStandards.md)
8. [WidgetStandards.md](WidgetStandards.md)
9. [SpeakTimeStandards.md](SpeakTimeStandards.md)
10. [ContentEngineering.md](ContentEngineering.md)
11. [AnalyticsEngineering.md](AnalyticsEngineering.md)
12. [PrivacyEngineering.md](PrivacyEngineering.md)
13. [ErrorHandling.md](ErrorHandling.md)
14. [OfflineFirst.md](OfflineFirst.md)
15. [TestingStrategy.md](TestingStrategy.md)
16. [ArchitectureFitness.md](ArchitectureFitness.md)
17. [LoggingStandards.md](LoggingStandards.md)
18. [GitWorkflow.md](GitWorkflow.md)
19. [CodeReview.md](CodeReview.md)
20. [DefinitionOfDone.md](DefinitionOfDone.md)

Cursor enforcement: `.cursor/rules/`.

## Deliberately unresolved

Framework, Android Speak Time mechanism, voice display names, and long-term
widget identity stay open. See `../architecture/FrameworkDecision.md` and
`../architecture/Spikes.md`.

# Code Review

**Phase:** 4 — Engineering Standards
**Status:** Draft for review

Use this checklist on every meaningful pull request. Skip a section only
when the PR is docs-only and say so.

## Product

- [ ] Supports an already approved behavior or ritual
- [ ] Maps to `BehaviorArchitecture.md` (transition, ritual, emotion, metric, anti-goal, principle)
- [ ] Does not redefine product behavior in code comments or defaults

## Architecture

- [ ] Dependency direction holds (`DependencyRules.md`)
- [ ] Domain stays free of UI, network, analytics, and platform SDKs
- [ ] Local-first: core path works offline
- [ ] No new subsystem whose only justification is future scale

## Ethics and anti-goals

- [ ] Does not introduce shame, guilt copy, punishment state, or pressure escalation
- [ ] Does not add streaks, missed-day counts, or user-visible scores
- [ ] Does not lengthen time-in-app without a documented warning review
- [ ] Answers: could this make Wake itself a form of procrastination?

## Privacy

- [ ] No new data, or the field is justified, minimized, and documented
- [ ] Intention text not logged or sent
- [ ] Analytics remains optional

## Platform

- [ ] Does not assume Android and iOS parity
- [ ] Does not claim exact Speak Time or live widget precision without evidence
- [ ] Does not choose FGS or a framework while H13–H15 are open

## Testing

- [ ] Behavioral edge cases in `TestingStrategy.md` covered or explicitly deferred with a reason
- [ ] Failure of analytics or notifications does not fail MicroStart tests

## Scope

- [ ] Does not add Task, Streak, History, Social, Account, Leaderboard, Achievement, or a generic Feature domain
- [ ] Does not implement production UI or services during a docs-only phase
- [ ] Documentation updated if the architecture changed
- [ ] Product Decision Log updated if a decision changed

## AI-assisted changes

- [ ] Treated as a proposal; reviewer checks architecture, not just style
- [ ] Canonical names unchanged (`MicroStart`, `VoiceA`, `VoiceB`)

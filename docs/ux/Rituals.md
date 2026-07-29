# Rituals — Behavioral Ritual Framework

**Phase:** 2 — UX Documentation (added per Phase 2 review resolution)
**Status:** Draft for review
**Purpose:** Product-philosophy documentation exploring **Behavioral
Rituals** as the primary way we talk about what Wake offers — alongside,
and often instead of, "features." Not an implementation plan; not a rename
of the MVP scope contract. Features remain the engineering/shipping unit;
rituals are the *user-meaning* unit.

---

## 1. Why rituals, not only features

Features describe what the product *has*. Rituals describe what the user
*does* with time. Identity forms around repeated meaningful acts
(`BehaviorChangeModel.md` reinforcing loop: Reflection → Identity), not
around installed capabilities. A person does not become "someone who
starts" by owning a timer; they become that by repeating a small start
until it is *like them*.

Rituals also resist engagement creep: a feature invites expansion
("what else could it do?"); a ritual invites fidelity ("did we protect
the act?"). That matches P13 and AntiGoal A1.

## 2. How rituals differ from features

| | Feature | Ritual |
|---|---|---|
| Unit of meaning | Capability / surface | Recurring act in the user's day |
| Success | Ships, works, is used | Is repeated, felt, and eventually internalized |
| Failure mode | Bugs, missing options | Broken emotional contract (shame, noise, bait-and-switch) |
| Growth | Add more | Deepen fidelity; add rituals sparingly |
| Ownership | Product team | Shared — user performs it; product scaffolds it |

A single feature can serve multiple rituals (the widget serves Morning
Awareness and Midday Reset). A ritual may compose multiple features
(Tiny Start = affordance + timer + completion content).

## 3. The Wake ritual set (MVP-aligned)

| Ritual | When | What the user does | Features that scaffold it | Loop transition | Emotional goal |
|---|---|---|---|---|---|
| **Morning Awareness** | Wake +0–2h | Glance the day-shape; optionally hear/read a calm line | Widget, S1 content, optional morning pulse | Notice | Curiosity / Calm orientation |
| **Tiny Start** *(MicroStart)* | Any moment of resistance | One tap → two honest minutes → close | Start affordance, timer, T6 completion | Offer→Start→Momentum→Reflection | Action → Confidence |
| **Fresh Start** | After a gap (≥ threshold) | Open Wake; feel welcome; optionally start | Weightless Now, S6 Recovering content | Return→Relief→Fresh Start | **Relief** ("I'm still welcome") |
| **Midday Reset** | Midday band | Interrupt absorption; re-orient to remaining day | Midday pulse / Speak Time, S2 content | Notice→Offer | Grounded / Focused |
| **Evening Reflection** | Last hours of wake window | See remaining time without panic; choose one small act or rest | S3 content, rest face later | Notice / Rest | Reflective; rest permitted |

Optional later (Horizon 2+, not MVP): **Stoic Reflection** (philosophy
pack — consent-gated); **Landmark Morning** (Monday/month — already
partially present as S7 content override).

## 4. Why rituals strengthen identity

1. **Named acts are memorable.** "I did a Tiny Start" is a self-story
   unit; "I used the timer feature" is not.
2. **Repetition with emotional closure** (Reflection) is how Identity
   forms in the reinforcing loop.
3. **Rituals survive the app.** When prompts quiet (graduation), the
   ritual can remain as a personal practice — which is Autonomy.
4. **Relief is a ritual, not a feature.** Fresh Start has almost no UI
   delta; its power is the emotional contract. Framing it as a ritual
   keeps that contract from being "optimized away."

## 5. Design rules when thinking in rituals

1. Every ritual must map to ≥1 Wake Loop transition and ≥1 Anti-Goal it
   must not corrupt (`../architecture/BehaviorArchitecture.md`).
2. Rituals are **invited or ambient**, never assigned as homework (no
   "complete all 5 rituals today" — that recreates streaks/A4).
3. A ritual's empty/return states follow `EmptyStates.md` and Relief
   rules — especially Fresh Start.
4. New "features" proposals must declare which ritual they serve; if
   none, they are decoration (P13) or a new ritual requiring philosophy
   review.
5. Marketing and onboarding may speak in ritual language ("feel the
   morning; start tiny") while Settings may still use plain feature
   names — dual vocabulary is fine if the glossary stays clear
   (`Terminology.md`).

## 6. Relationship to existing docs

- Does **not** replace `MVPDefinition.md` feature list.
- **Does** inform copy, onboarding framing, and Phase 5 motion naming.
- **Does** give Horizon planning a vocabulary that resists feature-farm
  growth (`FeatureRoadmap.md` should prefer "deepen Tiny Start" over
  "add seven widgets").

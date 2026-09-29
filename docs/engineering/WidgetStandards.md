# Widget Engineering Standards

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Architecture:** `../architecture/WidgetArchitecture.md`,
`../architecture/WidgetEvolutionProgram.md`

---

## Ownership

| Owns | Does not own |
|---|---|
| **Domain:** `TimeAwarenessState`, wake window, FreshStartFlag, content line id, MicroStart remaining if running | Geometry, animation, colors, per-pixel refresh |
| **Renderer:** layout, motion, platform refresh strategy, size families | Source of truth, scheduling policy, MicroStart transitions |

A renderer must not store its own copy of "how much day is left" that can
diverge from domain state. It receives a snapshot and draws it.

## Honesty

If a platform cannot refresh every minute, the renderer uses coarse steps
that look intentional. Do not animate fake real-time precision
(`../architecture/Spikes.md` H13). Day Dots is the Default V1 renderer, not
the permanent identity.

## Introducing a renderer

1. Implement `DayShapeRenderer` (name may follow the language idiom) for one
   of: `DayDots`, `OpportunityTiles`, `TimelineBlocks`, `LivingHorizon`,
   `RemainingRibbon`, `DayArc`.
2. Do **not** add a new domain model per renderer.
3. Default remains Day Dots until a Product Decision promotes another.
4. New renderers ship behind a flag defaulting off.
5. Each renderer provides an accessibility summary string from the same
   snapshot fields.
6. Map the change to BehaviorArchitecture (Notice + MicroStart affordance).

## Refresh

Refresh policy lives in the platform adapter, bounded by
`../architecture/BatteryOptimization.md`. The domain does not call widget
APIs.

## Actions

Start and open-Now intents call application use cases. Renderers do not
embed business rules about when a start counts.

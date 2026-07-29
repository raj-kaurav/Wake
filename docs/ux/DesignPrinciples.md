# UX Design Principles

**Phase:** 2 — UX Documentation
**Status:** Draft for review
**Authority:** Implements the constitution (`../product/ProductPrinciples.md`)
at the experience level. Where these principles and a screen design conflict,
the screen changes. Phase 5 (design system) implements these visually.

---

## D1 — Glance-first, app-second

The primary experience happens *outside* the app: home-screen glances,
spoken moments, notification pulses. The in-app surface exists mainly to
run the timer and adjust settings. Design effort allocates accordingly:
the widget is our real home screen.

**Do:** design every feature widget-outward. **Don't:** hide value behind
an app open.

## D2 — One glance, one meaning

Each surface communicates exactly one thing at a time: the day's shape OR
a start invitation OR a completion moment. No surface stacks messages,
badges, or secondary calls to action.

**Test:** can a user extract the meaning in under one second, unfocused,
while walking?

## D3 — One tap to action, everywhere

From any Wake surface, a real start is exactly one tap away (P2). Two taps
is a defect. Zero-decision path: the tap itself never opens a decision
(intention entry is available, never demanded).

## D4 — Shape over digits

Time is rendered as form (filling dots, moving arcs, shrinking fields)
before it is rendered as numbers. Digits are the caption, not the message —
they are read and skipped; shapes are felt (`../research/ExecutiveFunctionADHD.md` §3).
Every shape carries a text equivalent for accessibility (P10).

## D5 — Silence during work

From timer start to timer end, the product produces nothing: no ticking
copy, no motivational interjections, no progress celebrations. The user's
work is the content. The UI shows remaining time as quietly as possible.

## D6 — Weightless states

No screen may carry weight from the past: no badges, counts, histories, or
"last seen" (P1, P3). Every arrival at any surface looks like a present
moment, whether the user was gone an hour or a month. States differ by
*time of day*, never by *user record*.

## D7 — Calm is the default; intensity is invited

Default configuration = the calmest coherent product: nurturing voice
pre-highlighted, pulses off until invited, Speak Time off, opportunity
framing (P9). Every intensity increase is a chosen, previewed, reversible
step with an obvious exit.

## D8 — The voice is everywhere or nowhere

The chosen voice colors every word the product says — onboarding,
notifications, settings descriptions, error states. Breaking character in
edge cases (errors, permissions) is where tone systems die; ours must not
(`../research/MicrocopyStrategy.md` §5). Both voices receive equal design
investment — no "default voice plus a reskin."

## D9 — Honest interface

The UI never dramatizes: no fake progress, no artificial waits, no
countdown theater beyond the real timer, no celebratory inflation
(completion moments are warm and *proportionate*). Promises in copy match
behavior exactly (P8): "two minutes" is 120 seconds.

## D10 — Five-second settings

Every setting is decidable in five seconds: plain-language label, current
value visible, at most one alternative or a simple stepper. No nested
option trees. Settings count is budgeted (see `InformationArchitecture.md`)
and grows only by constitutional argument.

## D11 — Interruption-proof by design

The core loop must survive real life: calls, locks, backgrounding, Do Not
Disturb, dead batteries at minute one. Every flow in `UserFlows.md`
defines its interruption behavior explicitly; a timer that loses a
completed start is a broken promise (P8).

## D12 — Design for the worst hour

Every screen is reviewed in the "Maya at 23:00" scenario: exhausted,
guilty, phone in bed. Surfaces must be dim-friendly, judgment-free, and
offer either a tiny start or explicit permission to rest — both are
designed outcomes (`AntiGoals.md` A6).

---

## Priority order under conflict

D12 (worst hour) and D9 (honesty) outrank all; then D3 (one tap); then D7
(calm default); then the rest. Mirrors the constitutional conflict rule.

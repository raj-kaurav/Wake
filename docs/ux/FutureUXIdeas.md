# Future UX Ideas

**Phase:** 2 — UX Documentation
**Status:** Draft for review — parking lot, not commitments
**Purpose:** UX-level explorations for post-MVP horizons, kept warm here so
they don't leak into MVP scope. Every idea below remains subordinate to
`../product/FeatureRoadmap.md` gates and the constitution; several exist
precisely because this document is where they wait.

---

## 1. Lock Screen & Always-On Surfaces (Horizon 2, nearest)

The widget's grammar on the surfaces users see most: iOS lock-screen
widgets (circular: a micro dot-arc; rectangular: dots + caption), Android
AOD complication. Design questions parked: does the dot grammar compress
to 8–12 dots without losing meaning? Does lock-screen presence at night
violate the rest-endorsement stance (proposal: rest face after wake
window, always)? W-B "Day Arc" is the natural circular-slot rendering
(`Widgets.md` §2).

## 2. Watch Presence (Horizon 2)

Complication (day-dots micro) + a one-tap Start on the wrist — the
lowest-friction OFFER surface conceivable (loop 2→3 in one wrist tap).
Speak Time on watch speakers/haptics (Taptic Time precedent). Parked
questions: does a wrist timer need any UI beyond haptic start/end?
(Proposal: no — the watch is affordance-only, the phone remains home.)

## 3. "The Stoic" Pack — Consent Ceremony Sketch (Horizon 2, ethics-gated)

The pack's UX challenge is its *entrance*: mortality framing must be
chosen with full understanding, never stumbled into (P9,
`../research/EthicalConsiderations.md` §4.2). Sketch: a dedicated,
unhurried opt-in sequence (deliberately slower than all other flows —
friction as consent quality): what the pack is (reflective Stoic practice)
→ what it shows (life-scale rendering on a user-set horizon or symbolic
scale — never predicted death dates) → sample lines → explicit enable.
Exit is one tap; re-entry repeats the ceremony. Voice: The Stoic joins as
a third voice with its own contract (calm, classical, zero morbidity-as-
edge). All of this awaits the dedicated ethics review; nothing ships
before it.

## 4. Countdown-to-Start Micro-Variant (research candidate, H-series)

From `../research/FeatureIdeaAssessment.md` §5 alternatives: after the
Start tap, an optional 3-2-1 breath before the two minutes begin —
removing "the decision to begin the beginning." Test as a Wave 2
prototype fork; ship only if it measurably helps (it adds ~3 s against
the friction budget, so it must earn them).

## 5. Physical-Action Starts (content variant)

T3 lines that name a bodily first move ("Stand up. Walk to the desk.
That's the start.") for users whose wall is physical inertia. Zero new
UI — a content-type enrichment; noted for corpus v2 authoring.

## 6. Own-Voice Prompts (Horizon 2 gate)

Recording a 5-second message from present-you to future-you, played as a
pulse ("message from past-you" implementation intention). UX questions
parked: recording flow simplicity; the emotional charge of one's own
voice (potentially strong — and potentially cringe-inducing; research
first); storage stays local (P11).

## 7. Live Wallpaper (Android, Horizon 2)

The day-dots as ambient wallpaper — the ultimate D1 surface. Battery and
OEM variance questions to Phase 3; design question parked: wallpaper
cannot carry a Start affordance (no interactivity), so it is pure NOTICE —
acceptable as a *supplement* only (P2 requires the widget/pulse layer to
remain).

## 8. The Rhythm Hint (Horizon 3, constitutionally contentious)

The single statistics-adjacent idea with a hearing
(`../product/FeatureRoadmap.md` H3): a private, occasional, sentence-form
observation ("Mornings seem to be your easiest starts") — surfaced *in
Settings only, on demand*, never pushed. Must pass a dedicated P1 review
("felt, not tracked") and A4 check (no scorekeeping drift). Parked until
the base product's telemetry can even support it honestly.

## 9. Calendar-Adjacent Granularity (Horizon 2 gate)

"40 minutes until your next meeting — enough to start" as a T2 content
capability with read-only calendar access. UX parked questions: permission
ask framing (F8 pattern); does calendar presence drag scheduling-app
gravity into the product's feel? (The five-second settings rule and P7
are the guards.)

## 10. Deliberate Non-Ideas

Recorded so future enthusiasm meets past reasoning: themes/customization
galleries (A8 bait) · celebration upgrades (confetti economies — A1) ·
widget stat variants ("starts this week" — A4/P1) · social widgets
("your friend started!") · AI-composed lines (unreviewable — ethics §5).

---

*Additions to this file are welcome at any phase; graduation out of it
requires the roadmap gate + constitutional review. Nothing here may be
built "while we're at it."*

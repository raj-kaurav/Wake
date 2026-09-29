# Behavioral Design

**Phase:** 2 — UX Documentation
**Status:** Draft for review
**Purpose:** The applied mechanics: how each surface implements the
behavior-change model (`BehaviorChangeModel.md`) — friction budgets,
defaults, commitment mechanics, anti-habituation, and the graduation
design. Where `EmotionalDesign.md` specifies how moments *feel*, this
document specifies how they *work on behavior*.

---

## 1. Friction Audit (the asymmetry we engineer)

Behavior follows the cheapest path; we price the paths deliberately:

| Path | Cost target | Enforced by |
|---|---|---|
| Awareness → start | **1 tap, <1 s, 0 decisions** | D3; deep-link contracts (Navigation §7); intention prefill |
| Start → stop | 1 tap, 0 confirmations (honest exit) | Navigation §4 — stopping is legitimate; hiding it would be coercion |
| Any signal → silence | 1 tap (quiet-today), ≤2 taps (disable) | P9 retreat flows (F9) |
| Configuring more intensity | deliberate, previewed, multi-step | P9 — intensity is *invited*, so its path is intentionally less slick than retreat |
| Reaching a second obligation | **impossible** | P7 — no path exists |

The doctrine: **make the good act cheaper than the escape act, and make
retreat cheaper than both.** We compete with an infinitely cheap scroll;
we win only at zero decisions.

## 2. Defaults Table (choice architecture, all in one place)

| Parameter | Default | Rationale |
|---|---|---|
| Voice pre-highlight | The Friend | safety-first (`../research/BehavioralEconomics.md` §4); explicit tap still required |
| Timer length | 2 min | anchor-small; remote-config arm for H3 (2/3/5) |
| Pulses | off until invited; suggested 3/day | P9; batching evidence (Fitz et al.) |
| Speak Time | off; suggested 60 min | annoyance floor; H5 |
| Framing | opportunity ("left") | H2 pending; anxiety-safe default |
| Wake window | 07:00–23:00 | broad, editable |
| Intention field | shown, optional | H12 pending |
| Quiet hours | = outside wake window | sleep endorsed |
| Milestone announcements (screen reader) | off | chattiness ≠ access |

Every default is a hypothesis with a telemetry hook; defaults change via
evidence, not taste (P12).

## 3. Commitment Mechanics (kept micro, kept honest)

- The Start tap is the product's only commitment device: a 120-second
  self-contract, honored exactly (`../research/BehavioralEconomics.md`
  §5). No deposits, no social stakes, no escalating ladders.
- The intention string sharpens commitment via specificity
  (implementation-intention scaffolding: pulses can reference it — "The
  deck. Two minutes." — T3 lines with intention interpolation are a
  content-system capability to confirm in Phase 3).
- **No pre-commitment scheduling of future starts in MVP** ("commit now
  for 9am tomorrow") — it recreates a breakable plan (P7). The anchor
  moment from onboarding research (`../research/HabitFormation.md` §4.3)
  is served by the user's pulse schedule instead: the pulse *is* the
  externalized implementation intention.

## 4. Cue Design (the NOTICE transition, engineered)

- **Layered cues at different attentional depths:** widget (ambient,
  passive), pulse (push, moment-bound), spoken time (absorption-piercing).
  A user picks their depth; the layers never stack simultaneously
  (pulse and Speak Time at the same minute collapse into one signal —
  scheduling rule for Phase 3).
- **Context stability serves habit formation:** pulses fire at the *same
  user-chosen times* daily (stable cue → faster automaticity, Lally);
  variation lives in content, never in timing
  (variation-within-predictability, `../research/NotificationPsychology.md` §3).
- **Cue → action co-location:** every cue carries the Start affordance
  in itself (P2) — the distance from cue to act is zero *by layout*.

## 5. Reinforcement Design (the CLOSE transition)

- The true reinforcer is endogenous: relief + self-credit ("You started.").
  The product's job is to *frame* it (T6 lines, IKEA-rule attribution),
  not replace it with app-goods (no points/pets — HabitFormation §2 risk).
- Reinforcement is **immediate** (≤3 s from timer end), **proportionate**
  (warm, brief), and **unconditional on continuation** (stopping at 120 s
  earns the full close — protecting the trust that makes the small ask
  believable next time).
- Variable *content* (rotating T6 lines) provides freshness; **fixed
  contingency** (every real start closes warmly) provides safety. We
  deliberately invert the industry pattern (variable rewards on fixed
  content) because variable-reward mechanics are banned (P8/ethics §2).

## 6. Anti-Habituation Program (R1, operationalized)

1. Content rotation with recency suppression (ContentSystem §3–4 depth
   minimums).
2. Landmark punctuation: Mondays/month-starts/gap-returns re-key the
   morning moment (S7) — calendar-driven novelty, zero added volume.
3. Respectful-silence: ignored channels quiet themselves
   (NotificationStrategy §4) — protecting signal value by rationing it.
4. Stable glance-grammar: the widget's *form* stays learnable while its
   *words* rotate (Widgets §8) — novelty budget spent on language, not
   layout.
5. Telemetry: pulse→start decay slopes per cohort are a first-class
   design KPI reviewed monthly (not a post-hoc dashboard — a design
   input).

## 7. Graduation Design (the countercultural requirement)

The model predicts (and we want) prompt-dependence to fall with tenure
(`BehaviorChangeModel.md` §4). Design consequences now, not later:

- Self-initiated starts (app-open → start, widget-start without a recent
  pulse) must be *at least as smooth* as prompted ones — the product never
  privileges its own prompts.
- Respectful-silence doubles as a graduation ramp: a user who starts
  without pulses stops "needing" them, ignores them, and the system
  quiets itself — dependence decays by design.
- No feature may ever *interrupt* a self-initiated pattern to reassert
  the app (no "let Wake schedule this for you!" upsells on organic
  starts).
- Marketing honesty (D9 at the brand level): we may tell users the goal
  is to need us less; per `../product/SuccessMetrics.md` §5 we measure
  exactly that.

## 8. Dark-Pattern Firewall (behavioral design's negative space)

This document's tools — defaults, framing, friction — are the same tools
dark patterns use. The firewall is procedural: every behavioral-design
change names its mechanism and passes the endorsement test
(`../research/EthicalConsiderations.md` §2) in review; the prohibited
list (fake urgency, guilt hooks, streak threats, variable rewards,
pre-checked intensity) is enumerated in the Phase 4 review checklist; and
`AntiGoals.md` defines the outcomes that would mean we failed even while
"succeeding."

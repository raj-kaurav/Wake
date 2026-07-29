# Anti-Goals

**Phase:** 2 — UX Documentation (added per Phase 1 review feedback)
**Status:** Draft for review
**Purpose:** Document the behaviors and outcomes the product must avoid
encouraging — including ways Wake could "work" and still harm. Each
anti-goal names the mechanism by which we could accidentally cause it, the
design guards in place, and the detection signal. These are outcome-level
complements to `../product/OutOfScope.md` (which bans features); anti-goals
ban *effects*.

Frame: every anti-goal is a corruption of a Wake Loop transition
(`BehaviorChangeModel.md`) — the loop working on the wrong object.

---

## A1 — App engagement replacing life engagement

- **The corruption:** the OFFER→START transition redirects into the app
  itself: Wake becomes a place to *be* rather than a doorway to leave
  through. (Loop serves the product, not the user.)
- **How we could cause it:** adding browsable content, richer completion
  ceremonies, streaks of any kind, "one more" prompts — each individually
  defensible as "engagement."
- **Guards:** no feeds or browsable surfaces exist (P5, IA §2); session
  auto-yields after close; the in-app surface is deliberately too sparse
  to binge (D1).
- **Detection:** median non-timer session length rising; opens without
  starts rising (guardrails, `../product/SuccessMetrics.md` §5).

## A2 — Compulsive time-checking

- **The corruption:** NOTICE over-fires: the widget/spoken time trains
  anxious clock-watching instead of calm orientation — time-salience
  becomes time-vigilance.
- **How we could cause it:** minute-precision displays, alarming visual
  urgency near day-end, intensity-3 content at fragile hours.
- **Guards:** coarse 15-minute granularity *by design* (Widgets §2 — the
  dot is deliberately unwatchable second-to-second); calm evening framing
  with rest permission (S3, T4); intensity caps by context (ContentSystem
  §1.3).
- **Detection:** aversive-use signals (rapid widget removal, Speak Time
  disabled <24h); H8 "pressuring" responses; interviews probing checking
  behavior in Wave 4.

## A3 — Prompt dependence deepening over time

- **The corruption:** the loop never internalizes: users can only start
  when Wake fires, and the scaffolding becomes a crutch that deepens
  (6→1 transition owned by us forever).
- **How we could cause it:** privileging prompted starts over organic
  ones; re-engagement mechanics; fighting respectful-silence because it
  "hurts DAU."
- **Guards:** graduation design (BehavioralDesign §7); respectful-silence
  as a ramp down; self-initiated paths first-class by contract.
- **Detection:** the prompt-dependence guardrail (self-initiated share
  must rise with tenure — SuccessMetrics §5).

## A4 — Starts as a new scorekeeping anxiety

- **The corruption:** CLOSE banks not a win but a *ledger entry*: users
  begin performing starts for the count, feeling deficient on low-count
  days — we will have rebuilt the streak app inside their head.
- **How we could cause it:** displaying any start count, "personal bests,"
  even well-meant weekly reflections; over-warm praise that implies a
  standard being met.
- **Guards:** no start history is displayed anywhere, constitutionally
  (P1/P3; IA §5 illegal inputs); completion warmth is proportionate and
  identical on a first start and a fiftieth (fixed contingency,
  BehavioralDesign §5).
- **Detection:** support/review language about "keeping my numbers up";
  interview probes; any user asking "where do I see my stats" is noted —
  and answered with the philosophy, not a roadmap promise.

## A5 — Productivity-identity totalization

- **The corruption:** the loop annexes the whole person: every hour must
  be "used," rest becomes guilt, the day-shape reads as a factory gauge.
- **How we could cause it:** depletion framing everywhere, day-end
  "summary" moments, copy that valorizes output ("crush your day").
- **Guards:** rest is a designed outcome with its own content type (T4)
  and its own state (the rest face endorses the day's end — Widgets §4);
  grind vocabulary is banned (Microcopy §2); outside-wake-window hours
  belong to the user unconditionally.
- **Detection:** H8 segment analysis; content-review drift audits (are T4
  lines shrinking as a corpus share?).

## A6 — Punishing rest / pathologizing normal delay

- **The corruption:** NOTICE fires at moments when *not acting is
  correct* (illness, grief, a needed evening off), and the product's
  presence reads as accusation. Not all delay is procrastination; some is
  wisdom or rest.
- **How we could cause it:** relentless action-only content; treating
  every quiet day as a lapse to re-engage.
- **Guards:** T4 rest permissions in every voice at every eligible slot;
  quiet-today one tap from every pulse (F9); absence produces zero
  reaction (D6); "the button keeps" framing (rest without forfeiting the
  door).
- **Detection:** qualitative only — interviews and reviews; this
  anti-goal is why aversive-use signals never trigger messaging (research
  input only, P11).

## A7 — Shame relocation (subtler than shame injection)

- **The corruption:** we never shame explicitly, but the product's
  *contrasts* do it implicitly — e.g., a beautiful fresh-start line whose
  very warmth reminds the user how long they were gone; a Coach line
  whose wit lands as a barb on the wrong day.
- **How we could cause it:** tonal misfires at fragile moments; landmark
  framing that implicitly references the gap.
- **Guards:** S6/post-lapse serves intensity-1 only; banned-word list
  ("again," "still," "back") in S6 (F6); the 2 a.m. test in the ethics
  checklist applied per line; Coach lines drill-tested for barb-reading
  (Microcopy §2 failure drills).
- **Detection:** line-cohort telemetry (disable/switch following specific
  lines — R4 signal); beta diary studies.

## A8 — Displacement procrastination via Wake itself

- **The corruption:** configuring, adjusting, and reading Wake becomes
  the user's newest form of productive procrastination (the Notion-setup
  failure mode, miniaturized).
- **How we could cause it:** settings depth, themes galleries, tinkerable
  everything.
- **Guards:** 12-setting budget (IA §4); no themes/customization surface
  in MVP; five-second settings rule (D10) makes tinkering unrewarding.
- **Detection:** settings-visit frequency telemetry (aggregate); a user
  visiting settings daily is a design smell, not a fan.

---

## Standing Review Questions

Every phase gate and every feature review asks:

1. **"Which anti-goal does this change move us toward, even slightly —
   and is the guard already in place?"** An unanswered A-question blocks
   the change (same standing as the constitution's principle test, which
   these anti-goals extend to outcomes).

2. **"Could this feature accidentally become another form of
   procrastination?"** — **mandatory** for every future feature proposal.
   Unanswered = blocked. Required answers (written into the proposal,
   not oral):

   | Required answer | What good looks like |
   |---|---|
   | **How could users misuse this?** | Name at least one plausible misuse path (configuration rabbit hole, browsing instead of starting, checking as avoidance, performing starts for scorekeeping…) |
   | **Could users spend time inside Wake instead of starting?** | Yes/no with mechanism; if yes, state the time-sink surface |
   | **How is that prevented?** | Point to a concrete guard: friction budget, missing surface, constitutional exclusion, respectful-silence, content-not-browsable, etc. "We'll be careful" is not an answer |

### Review criteria (pass/fail)

A proposal **fails** this review if any of the following hold:

- It introduces a destination surface (feed, gallery, history, insights
  dashboard) without a one-tap exit into a MicroStart and a session-length
  guardrail (A1).
- It creates a record the user can perform against (counts, bests,
  comparisons) (A4).
- It lengthens the path from Notice to MicroStart (A8 / D3).
- Its "prevention" relies solely on user self-control rather than
  structure (defaults, absence of the tempting surface, budgets).
- It fights graduation by re-escalating prompts after organic quieting
  (A3).

A proposal **passes** when misuse paths are named, in-app time-sinks are
structurally impossible or capped, and prevention maps to an existing
guard in this document or the constitution — not to a future promise.

Cross-check: every row in `../architecture/BehaviorArchitecture.md`
already lists its Anti-Goal; new features must add a row that clears this
review before entering the roadmap.

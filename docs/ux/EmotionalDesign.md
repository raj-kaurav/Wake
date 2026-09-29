# Emotional Design

**Phase:** 2 — UX Documentation
**Status:** Draft for review
**Purpose:** Specify the emotional register of every moment. Wake operates
on feelings about time and self-worth — emotional design here is the core
mechanism, not brand garnish. Companion docs: `EmotionalJourney.md` (over
time), `BehavioralDesign.md` (mechanics), Phase 5 (visual execution).

---

## 1. The Baseline Register: Calm Alertness

Wake's default emotional temperature sits deliberately between the
category's two failure poles — wellness-app sedation ("everything is
fine, rest forever") and hustle-app agitation ("time is running out!").
Target state: **the feeling of a clear morning** — awake, unhurried,
capable. Every surface is tuned to it:

- Visual: still layouts, generous space, one breathing element maximum
  (Phase 5 executes).
- Verbal: present tense, concrete nouns, no urgency punctuation (D9,
  Microcopy §1).
- Temporal: nothing on screen counts down at the user except the running
  timer they started themselves.

## 2. Emotional Specification by Moment

| Moment | Target feeling | Must never feel like | Design carriers |
|---|---|---|---|
| Widget glance | orientation; "the day is here, and so am I" | deadline dread; being watched | dot-field calm; opportunity caption; D2 one-meaning |
| Pulse arrival | a hand on the shoulder | an alarm; a demand | soft tone; ≤40-char line; Start as offer, not order |
| Spoken time | a lighthouse sweep — neutral, reliable | a nagging parent | the utterance's radical restraint (Microcopy §7) |
| Pre-start (S4) | permission; smallness of the ask | a test of character | anchor-small copy; intention prefilled; one tap |
| During timer | absorbed quiet; the app has left the room | being timed/judged | silence (D5); soft remaining-shape |
| Completion | proportionate warmth; *self*-credit | jackpot celebration; app taking credit | T6 lines credit the user (IKEA rule); brief, resolved sound |
| Stop early | neutrality; a fact, not a verdict | guilt; "are you sure?" shaming | no confirmation dialog; standard quiet close |
| Evening (S3) | invitation; "one real thing fits" | last-chance panic | remaining-framing; T4 rest permission present |
| Outside wake window | endorsement of rest | 24/7 productivity pressure | rest face; "Day complete."; no Start push |
| Lapse return (S6) | a clean page; zero owed | walking into a review meeting | D6 weightlessness; T7 fresh-start line; identical layout |
| Permission/edge states | competence; honesty | blame; drama | S8 copy rules (Microcopy §6) |

## 3. Voice as Emotional Instrument

The two voices are two *renderings of the same care* — they modulate
energy, not values (`../research/MicrocopyStrategy.md` §3.1). Emotional
parity requirements:

- Equal warmth budgets: The Coach is not "the cold one" — its warmth is
  respect and brevity; The Friend is not "the soft one" — its warmth
  includes quiet confidence in the user.
- Equal moments: both voices get full-quality completion moments, fresh
  starts, and rest permissions; no emotional feature is voice-exclusive.
- Palette accents (Phase 5) may differ in temperature, but both must
  remain inside the calm-alert baseline — the Coach palette is not
  "alarm red."

## 4. The Two Designed Peaks (peak–end economics)

Per `../research/BehavioralEconomics.md` §9, memory forms at peaks and
ends; we invest asymmetrically in exactly two moments:

1. **Completion** — the peak. The warmest audio, the best line in the
   corpus rotation, the one place the product looks the user in the eye.
   Budget: it must land in ≤ 3 seconds (warmth ≠ length) and auto-yield
   (the user's evening does not belong to us).
2. **The day's end** — the end. The final S3 pulse and the rest face close
   the day *kindly regardless of what happened in it*: the last thing Wake
   says on a bad day is never an accounting. ("The day's done. Tomorrow
   has its own dots." — Friend; "Day closed. It doesn't carry over." —
   Coach.)

## 5. Anxiety Engineering (the R9 discipline)

Time-salience has a threat edge; we manage it structurally, not just
verbally:

- Opportunity framing default; depletion only via tested variant (H2).
- Intensity caps by context: post-lapse and late-night moments serve
  intensity-1 content only (ContentSystem §1.3).
- Every awareness channel has an instant, guilt-free exit (quiet-today,
  mute, disable — P9); the *existence* of easy exits is itself
  anxiolytic (perceived control).
- The product never expresses disappointment — not in copy, not in
  iconography, not in palette shifts. There is no sad state anywhere in
  the design (no wilted plants, no gray "inactive" moods).

## 6. Trust as the Meta-Emotion

Every emotional effect above depends on trust, built mechanically:
promises kept literally (P8), predictable schedules (user-set, honored),
no surprises (no new notification types, no moved buttons), honest edge
states. Trust is why restraint wins long-term: each kept promise
compounds; a single bait-and-switch (an upsell on the completion screen)
would spend it all.

## 7. Delight Policy (yes, but…)

Wake earns delight through *fit* — the right line at the right moment, a
landmark morning's subtle accent, the completion sound's resolution — and
never through interruption, animation spectacle, or reward mechanics. The
test for any proposed delight: it must deepen the current moment rather
than add a new one (D2), and it must survive the 500th repetition without
becoming noise (R1).

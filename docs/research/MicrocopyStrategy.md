# Microcopy Strategy Research

**Phase:** 0 — Discovery & Research (added in revision 1)
**Status:** Draft for review
**Purpose:** Establish the research basis for how Wake speaks. In a product
with two authored voices, almost no chrome, and a philosophy delivered in
one-line doses, microcopy is not polish — it is the primary material.
Phase 2's `Microcopy.md` will turn this into a full style guide; this
document supplies the evidence and the strategic decisions.

---

## 1. Why Words Carry This Product

Wake's UI at any moment shows perhaps a dozen words. Those words must do the
work that other apps do with features: reframe the task, shrink the start,
carry the chosen voice, and never shame. Every line is therefore a behavioral
intervention and gets reviewed like one (checklist in
`EthicalConsiderations.md` §5).

## 2. Research Foundations

### 2.1 Autonomy-supportive vs. controlling language

Self-determination theory (Deci & Ryan) and message-framing studies (e.g.,
Legault et al. on autonomy-supportive interventions; reactance research,
Brehm) converge: controlling language ("you must," "you should," "don't
forget!") triggers reactance and undermines intrinsic motivation, while
autonomy-supportive language (choice, invitation, rationale) sustains it.

- **Rule:** No "should," "must," "need to" directed at the user, in either
  voice. The Coach-style voice is *challenging*, not *commanding*: "Two
  minutes. Yours if you want them." challenges; "You need to start now"
  controls.

### 2.2 Self-talk and person forms

Kross et al.'s distanced self-talk research: second-person and name-based
self-talk regulates emotion better than first-person immersion during
stressful tasks. App copy in second person ("You started.") doubles as a
self-talk script — one more reason tone discipline matters
(`EthicalConsiderations.md` §3: we are scripting users' inner voice).

- **Rule:** Second person, present tense, active voice by default. The app
  itself has no first-person ego ("I think you…" is banned; Wake is a
  doorway, not a character — see also the IKEA-effect rule: credit the
  user, `BehavioralEconomics.md` §8).

### 2.3 Concreteness and construal

Construal-level theory (already cited) implies concrete language collapses
psychological distance. "Write one sentence of the intro" beats "make
progress on your thesis."

- **Rule:** Copy names the smallest concrete action available. Numbers in
  digits ("2 minutes," "120 seconds"), granular time units
  (`ProcrastinationScience.md` §3.1).

### 2.4 Fluency and brevity

Processing-fluency research: easy-to-read = felt-as-true and felt-as-easy.
Long words make actions feel harder.

- **Rules:** Reading level ≤ grade 6 for functional copy. Notification
  primary text ≤ ~40 chars. No idioms that break localization. One idea per
  line.

### 2.5 Positive action framing

Negation ("don't procrastinate") activates the concept it negates
(ironic-process research, Wegner). 

- **Rule:** Name the desired action, never the avoided one. The word
  "procrastination" itself should be nearly absent from the product — it
  labels the user with the problem identity. (This also serves the Time
  Awareness positioning: Wake speaks about time and starting, not about a
  disorder.)

## 3. The Two-Voice System (strategy)

Both voices share invariants; they differ in energy, not in values.

### 3.1 Shared invariants (both voices, always)

- Second person, present tense, concrete, ≤ 1 idea per line.
- Behavior/moment focus; never identity, never the past ledger.
- No shame, sarcasm-at-user, catastrophe, comparison. No "should/must."
- Always paired with an available action (or an explicit grant of rest).
- Honest: no fake stakes, no inflated praise.

### 3.2 Voice A — the challenging register (naming: see `ToneNamingExploration.md`)

- **Energy:** kinetic, clipped, dry. Sentence fragments allowed.
- **Signature moves:** stating the time + the move ("14:00. The file's
  waiting."); wry understatement ("The report hasn't started itself.");
  countdown cadence ("120 seconds. Go.").
- **Failure modes to police:** drill-sergeant drift, guilt by implication
  ("*still* not started?" — the word "still" is a ledger word; banned),
  edginess for its own sake.

### 3.3 Voice B — the nurturing register

- **Signature moves:** permission-giving ("Starting badly is allowed.");
  self-compassion framing ("Everyone stalls. Two minutes restarts you.");
  softened time ("It's 14:00 — plenty of day left.").
- **Failure modes to police:** toothlessness (gentle ≠ never start),
  saccharine repetition, therapy-speak ("hold space," "journey"), infantile
  tone (our users are ambitious adults; Finch's register would grate here).

### 3.4 The tone matrix

Every content line is authored per voice × context slot. Slots identified so
far (Phase 2 will finalize):

| Slot | Moment | Example (Voice A) | Example (Voice B) |
|---|---|---|---|
| Morning first-glance | first widget view / first pulse | "New day. 16 hours in the tank." | "Morning. The whole day's still yours." |
| Pre-start | Start screen, before tap | "Two minutes. That's the whole ask." | "Just open it. That counts." |
| During timer | running state | (silence — the work is the content) | (silence) |
| Completion | timer end | "Started. That was the hard part." | "You began. That's the win today." |
| Post-lapse return | first open after gap | "Good. You're here. 120 seconds?" | "Welcome back. Nothing is lost." |
| Evening | last pulses of wake window | "3 hours left. Enough for one real thing." | "The day isn't over yet — one small thing?" |
| Fresh-start landmark | Monday / month start / post-gap | "Clean week. Pick one thing." | "A fresh week — begin anywhere." |

Note the **during-timer slot is deliberately silent**: the moment the user is
acting, the product shuts up. Restraint is part of the voice.

### 3.5 Corpus economics

Two voices × ~7 slots × enough variants to resist habituation (est. 8–15 per
cell) ≈ **400–800 authored, reviewed lines for launch** (English only,
per Open Question assumption E5). This is the real cost of the tone system
and belongs in Phase 1 planning as a content-production workstream with the
ethics checklist as its review gate. Localization multiplies it — deferred.

## 4. Anti-Patterns Catalog (from competitor review)

| Anti-pattern | Seen in | Why banned |
|---|---|---|
| Guilt hooks ("We miss you!") | most retention flows | Prohibited practices list |
| Streak threats ("Don't lose your 47 days!") | habit apps | Visible-debt principle |
| Empty superlatives ("Amazing job!!!") | quote/habit apps | Dishonest praise erodes trust; violates honesty invariant |
| Identity labels ("You're a procrastinator") | tough-love apps | Identity attack; shame research |
| Therapy cosplay ("Hold space for your feelings") | wellness apps | Not-a-therapist boundary; grates on target users |
| Feature-speak ("Configure your awareness intervals") | utility apps | Fluency rule; humans don't speak settings |

## 5. Handed to Phase 2 (`Microcopy.md`)

1. Full style guide per voice (vocabulary, rhythm, punctuation, emoji policy
   — proposal: none).
2. Finalized slot taxonomy + selection rules (incl. landmark and
   respectful-silence interactions).
3. The 400–800-line launch corpus plan with review workflow.
4. Error/edge-state copy (permission denied, TTS unavailable) in both
   voices — edge states are where tone systems usually break character.
5. Accessibility pass: screen-reader phrasing, no meaning carried by
   typography alone.

## 6. Key Sources

- Deci, E., & Ryan, R. — self-determination theory.
- Legault, L., et al. (2011). Ironic effects of antiprejudice messages
  (autonomy-supportive vs. controlling framing).
- Brehm, J. — psychological reactance theory.
- Kross, E., et al. (2014). Self-talk as a regulatory mechanism. *JPSP.*
- Wegner, D. — ironic process theory.
- Alter, A., & Oppenheimer, D. (2009). Uniting the tribes of fluency.
  *Personality and Social Psychology Review.*

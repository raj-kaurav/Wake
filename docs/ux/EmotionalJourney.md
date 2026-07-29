# Emotional Journey

**Phase:** 2 — UX Documentation (added per Phase 1 review feedback)
**Status:** Draft for review
**Purpose:** Document the user's emotional progression from installation to
autonomy: what they feel at each stage, what they need, how the design
responds, and where the journey typically breaks. Stages align with the
tenure model in `BehaviorChangeModel.md` §4; per-moment specification lives
in `EmotionalDesign.md`.

The journey is written for the honest case: a chronically procrastinating
adult who has tried other tools, carries accumulated self-blame, and
installs Wake in a moment of motivated hope they have learned to distrust.

---

## Stage 0 — Discovery & Install (minutes)

- **Arriving emotions:** skeptical hope. "This looks different… but so did
  the last five." A thin layer of shame underneath (installing an app *for
  this* is itself an admission).
- **Needs:** to not be promised the moon; to not be asked for anything.
- **Design response:** honest store listing (sell the moment, not
  miracles — R3); onboarding asks for one meaningful choice and zero data
  (F1); the first screen's promise is modest and concrete.
- **Break risk:** overpromise here creates the week-3 disillusionment
  cliff; the emotional contract must start under-promised.

## Stage 1 — First Hour (the audition)

- **Emotions:** testing posture; mild relief at the absence of setup; a
  small, real lift at the first completed start ("that was… fine?").
- **The pivotal beat:** the first completion moment is the user's first
  experience of Wake keeping a promise (120 s meant 120 s) *and* of
  starting feeling smaller than expected — the core loop's thesis,
  delivered once, in miniature.
- **Needs:** a win with zero chance of failure attached.
- **Design response:** the landing state makes a first start one tap away;
  the ask is disarmingly small; the close credits *them* (peak–end
  investment, EmotionalDesign §4).
- **Break risk:** any friction (permission wall, decision, jargon) during
  the audition confirms the skepticism and ends it.

## Stage 2 — Week One (novelty carries; trust forms)

- **Emotions:** novelty-powered engagement; alertness to the widget's
  presence; watchfulness — *when will this app disappoint me like the
  others?* Each pulse that respects its schedule, each start that closes
  honestly, each evening that ends without an audit deposits trust.
- **Needs:** consistency; felt usefulness at least once a day; no demands.
- **Design response:** reliability as emotional design (D11 — a missed
  pulse is a broken promise); S3 evening moments that close days kindly;
  the H8 sentiment pulse lands late this week (one question, in-voice).
- **Break risks:** notification annoyance (defaults too loud → R9);
  novelty masking non-fit (feels nice, does nothing — caught later by H1).

## Stage 3 — Weeks 2–4 (the crux: habituation and the first lapse)

- **Emotions:** the widget starts becoming wallpaper; a day is missed,
  then three. Here arrives the emotion that killed every previous tool:
  **pre-emptive guilt about the app itself** ("I'm failing this one too").
  The user braces for the accusation they have learned to expect.
- **The make-or-break beat:** they open Wake after five silent days and
  find… today. No red. No count. No "welcome back." One clean line and
  the same button. **The absence of punishment is the single most
  important emotional event in the entire journey** — it is the moment
  Wake proves it is not the previous apps, and (per the self-forgiveness
  evidence) the moment the spiral's compounding term breaks.
- **Needs:** amnesty they didn't have to request; a re-entry smaller than
  their embarrassment.
- **Design response:** F6's weightless return, engineered to be
  indistinguishable from any other day; respectful-silence meanwhile
  prevented their absence from being nagged at; T7 fresh-start framing
  gives the return a forward door.
- **Break risks:** any ledger leakage (a changed layout, a "resume"
  banner) re-triggers the learned shame → uninstall; alternatively,
  silent churn if week-one never produced a felt win (R2).

## Stage 4 — Months 2–3 (integration; the quiet identity shift)

- **Emotions:** Wake stops being an *app they use* and becomes a *texture
  of their day* — the glance is automatic, the 2-minute move is a known
  personal tool ("I'll just dot it" — users will coin their own verbs).
  The deeper shift is narrative: from "I'm someone who procrastinates" to
  **"I'm someone who starts."** Small, but identity-level.
- **Needs:** the product to keep up without demanding attention; no
  novelty theater; continued freshness at low volume.
- **Design response:** anti-habituation program at full depth
  (BehavioralDesign §6); landmark moments provide gentle seasonality;
  nothing new is asked of them.
- **Break risk:** the plateau misread as staleness → *our* temptation to
  add engagement features. The design answer is to let the product recede
  gracefully (this stage is supposed to feel quiet — AntiGoals A1 guards
  the temptation).

## Stage 5 — Autonomy (the designed ending)

- **Emotions:** confidence with a shorter memory of the struggle; starts
  self-initiate; pulses feel optional and get quieted (by them or by
  respectful-silence); the widget may stay forever as a companion object
  or go — both are fine.
- **What success feels like from inside:** not "this app changed my life"
  but **"somewhere along the way, starting stopped being a thing."**
  (Full definition: `UserSuccessDefinition.md`.)
- **Design response:** graduation design (BehavioralDesign §7): no
  win-back, no guilt, frictionless quieting; the door stays open — a
  returner in a hard season re-enters at Stage 3's amnesty, not at zero.
- **The business tension, resolved in advance:** this stage reduces
  engagement on purpose. The constitution (P5) and metrics contract
  (prompt-dependence *declining* = success) were written so this stage
  survives commercial pressure.

---

## Journey-Level Design Laws (extracted)

1. **Under-promise at entry; over-deliver at the first close.**
2. **Reliability is an emotion.** Every kept schedule is a trust deposit;
   spend nothing.
3. **The first lapse is the product's true first impression.** Design
   backwards from Stage 3.
4. **Let the product recede.** From Stage 4 on, Wake's emotional job is
   to get quieter without getting colder.
5. **The journey may restart at any stage** (life happens); every restart
   lands on amnesty, not on a record.

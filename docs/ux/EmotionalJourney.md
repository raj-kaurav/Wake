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

## The Emotional Arc (canonical)

Tenure stages below describe *when* things happen; this arc describes
*what it feels like*, in order. Design must honor every step — especially
the Lapse → Relief sequence, which is the journey's load-bearing hinge.

```
Curiosity → Hope → Action → Momentum → Lapse → Relief → Confidence → Identity → Autonomy
```

| Emotion | Lived as | Tenure home | Design must deliver |
|---|---|---|---|
| **Curiosity** | "This looks different…" | Stage 0 | Honest, under-promised discovery |
| **Hope** | Thin, distrustful hope | Stage 0–1 | A first win with zero failure attached |
| **Action** | The first real start | Stage 1 | One tap; ask small enough to believe |
| **Momentum** | "That was… fine. Maybe again." | Stage 2 | Reliable pulses; honest closes; no escalation |
| **Lapse** | Pre-emptive guilt; bracing for accusation | Stage 3 | Zero reaction during absence (respectful silence) |
| **Relief** | **"I'm still welcome."** — not "I failed." | Stage 3 return | Weightless home; identical layout; T7/T4 only |
| **Confidence** | Trust that starting is possible again | Stage 3→4 | A start after Relief, banked warmly |
| **Identity** | "I'm someone who starts." | Stage 4 | Product recedes; glance becomes texture |
| **Autonomy** | Starting stopped being a *thing* | Stage 5 | Graduation; door stays open |

**Hard rule:** Confidence must not be asked of a user who has not yet felt
Relief. Any return UX that skips Relief (resume banners, "welcome back,"
gap acknowledgments, recovered counts) collapses the arc into the shame
spiral Wake exists to break. Full treatment: § "Why Relief Is the
Foundation" below.

---

## Stage 0 — Discovery & Install (minutes) — *Curiosity → Hope*

- **Arriving emotions:** skeptical hope. "This looks different… but so did
  the last five." A thin layer of shame underneath (installing an app *for
  this* is itself an admission).
- **Needs:** to not be promised the moon; to not be asked for anything.
- **Design response:** honest store listing (sell the moment, not
  miracles — R3); onboarding asks for one meaningful choice and zero data
  (F1); the first screen's promise is modest and concrete.
- **Break risk:** overpromise here creates the week-3 disillusionment
  cliff; the emotional contract must start under-promised.

## Stage 1 — First Hour (the audition) — *Hope → Action*

- **Emotions:** testing posture; mild relief at the absence of setup; a
  small, real lift at the first completed start ("that was… fine?").
- **The pivotal beat:** the first completion moment is the user's first
  experience of Wake keeping a promise (120 s meant 120 s) *and* of
  starting feeling smaller than expected — the core loop's thesis,
  delivered once, in miniature. This is where Hope becomes Action.
- **Needs:** a win with zero chance of failure attached.
- **Design response:** the landing state makes a first MicroStart one tap
  away; the ask is disarmingly small; the close credits *them* (peak–end
  investment, EmotionalDesign §4).
- **Break risk:** any friction (permission wall, decision, jargon) during
  the audition confirms the skepticism and ends it.

## Stage 2 — Week One (novelty carries; trust forms) — *Action → Momentum*

- **Emotions:** novelty-powered engagement; alertness to the widget's
  presence; watchfulness — *when will this app disappoint me like the
  others?* Each pulse that respects its schedule, each MicroStart that
  closes honestly, each evening that ends without an audit deposits trust.
  Momentum is the felt accumulation of kept promises, not of volume.
- **Needs:** consistency; felt usefulness at least once a day; no demands.
- **Design response:** reliability as emotional design (D11 — a missed
  pulse is a broken promise); S3 evening moments that close days kindly;
  the H8 sentiment pulse lands late this week (one question, in-voice).
- **Break risks:** notification annoyance (defaults too loud → R9);
  novelty masking non-fit (feels nice, does nothing — caught later by H1).

## Stage 3 — Weeks 2–4 (the crux: Lapse → Relief → Confidence)

- **Emotions at Lapse:** the widget starts becoming wallpaper; a day is
  missed, then three. Here arrives the emotion that killed every previous
  tool: **pre-emptive guilt about the app itself** ("I'm failing this one
  too"). The user braces for the accusation they have learned to expect.
- **The make-or-break beat — Relief:** they open Wake after five silent
  days and find… today. No red. No count. No "welcome back." One clean
  line and the same button. The felt sentence must be **"I'm still
  welcome"** — never "I failed." **The absence of punishment is the
  single most important emotional event in the entire journey** — it is
  the moment Wake proves it is not the previous apps, and (per the
  self-forgiveness evidence) the moment the spiral's compounding term
  breaks. Full rationale: § "Why Relief Is the Foundation" below.
- **Then Confidence:** only *after* Relief lands can a MicroStart on the
  return day bank a quiet win. Confidence is Relief proven by one more
  action — never demanded as a posture at the door.
- **Needs:** amnesty they didn't have to request; a re-entry smaller than
  their embarrassment.
- **Design response:** F6's weightless return, engineered to be
  indistinguishable from any other day; respectful-silence meanwhile
  prevented their absence from being nagged at; T7/T4 Recovering-
  temperature lines give the return a forward door (`ContentSystem.md`
  Emotional Temperature).
- **Break risks:** any ledger leakage (a changed layout, a "resume"
  banner) re-triggers the learned shame → uninstall; alternatively,
  silent churn if week-one never produced a felt win (R2).

## Stage 4 — Months 2–3 (integration; the quiet identity shift) — *Confidence → Identity*

- **Emotions:** Wake stops being an *app they use* and becomes a *texture
  of their day* — the glance is automatic, the 2-minute move is a known
  personal tool ("I'll just MicroStart it" / users will coin their own
  verbs). The deeper shift is narrative: from "I'm someone who
  procrastinates" to **"I'm someone who starts."** Small, but
  identity-level. Identity then feeds future Notice
  (`BehaviorChangeModel.md` § reinforcing loop).
- **Needs:** the product to keep up without demanding attention; no
  novelty theater; continued freshness at low volume.
- **Design response:** anti-habituation program at full depth
  (BehavioralDesign §6); landmark moments provide gentle seasonality;
  nothing new is asked of them.
- **Break risk:** the plateau misread as staleness → *our* temptation to
  add engagement features. The design answer is to let the product recede
  gracefully (this stage is supposed to feel quiet — AntiGoals A1 guards
  the temptation).

## Stage 5 — Autonomy (the designed ending) — *Identity → Autonomy*

- **Emotions:** confidence with a shorter memory of the struggle;
  MicroStarts self-initiate; pulses feel optional and get quieted (by
  them or by respectful-silence); the widget may stay forever as a
  companion object or go — both are fine.
- **What success feels like from inside:** not "this app changed my life"
  but **"somewhere along the way, starting stopped being a thing."**
  (Full definition: `UserSuccessDefinition.md`.)
- **Design response:** graduation design (BehavioralDesign §7): no
  win-back, no guilt, frictionless quieting; the door stays open — a
  returner in a hard season re-enters at Stage 3's **Relief**, not at
  zero and not at Confidence.
- **The business tension, resolved in advance:** this stage reduces
  engagement on purpose. The constitution (P5) and metrics contract
  (prompt-dependence *declining* = success) were written so this stage
  survives commercial pressure.

---

## Why Relief Is the Foundation of Renewed Engagement

The evidence base already says self-forgiveness reduces subsequent
procrastination and guilt increases it (`../research/ProcrastinationScience.md`
§2.2; Wohl et al., 2010). Translated into journey design:

1. **Shame is the spiral's compounding term.** If return feels like
   walking into a review meeting, the user avoids the app *and* the work —
   the same mood-repair mechanism that caused the original delay.
2. **Relief deletes that term.** "I'm still welcome" restores approach
   motivation without requiring the user to perform confidence they do not
   yet feel. Confidence is a *consequence* of one safe start after Relief,
   not a prerequisite for opening the door.
3. **Industry tools invert this.** Streaks, "we missed you," recovered
   chains, and resume banners all demand Confidence (or extract guilt)
   before Relief — which is why Stage 3 is where those products die.

### UX implications

- Return layout **identical** to any other day (D6); the only delta is the
  content line (S6 → T7/T4, Emotional Temperature = Recovering).
- No gap duration, no "welcome back," no layout shift that implies the
  product *noticed* the absence as failure.
- Start affordance unchanged in size and position — re-entry must be
  cheaper than embarrassment (friction audit, `BehavioralDesign.md` §1).
- Rest permission (T4) remains available on return; Relief includes the
  right to rest without forfeiting welcome.

### Copy implications

- Banned on return surfaces: "again," "still," "back," "missed," "resume,"
  any reference to the gap (F6; `Microcopy.md` §1).
- Allowed: present-tense, forward doors — "A fresh page — begin anywhere."
  / "The afternoon is a clean page."
- Temperature = **Recovering** (never Urgent, never Celebratory) until a
  post-return MicroStart has closed (`ContentSystem.md`).

### Notification implications

- Respectful-silence continues through the gap; absence never generates
  a re-engagement pulse (`NotificationStrategy.md` §4–5).
- Pulses that auto-downgraded restore **only** on explicit user action in
  Settings — never auto-escalate on return (would read as "we noticed").
- First post-return pulse, if any are still scheduled, uses Recovering /
  Grounded temperature — never kinetic challenge.

### Future measurement opportunities

- **Relief signal (research):** H8-adjacent pulse on return day —
  single question ("Opening Wake today felt: welcoming / neutral /
  accusing") — aggregate only, never a trigger (P11).
- **Relief → Confidence conversion:** share of gap-returns that produce a
  MicroStart within 24 hours of first post-gap open (extends H9).
- **Ledger-leakage alarms:** any future surface that changes on return
  must fail a D6 review before ship; qualitative probes in lapsed-user
  interviews ("did anything feel like it was counting your absence?").

---

## Journey-Level Design Laws (extracted)

1. **Under-promise at entry; over-deliver at the first close.**
2. **Reliability is an emotion.** Every kept schedule is a trust deposit;
   spend nothing.
3. **The first lapse is the product's true first impression.** Design
   backwards from Stage 3.
4. **Relief before Confidence.** Never ask for Confidence at the door.
5. **Let the product recede.** From Stage 4 on, Wake's emotional job is
   to get quieter without getting colder.
6. **The journey may restart at any stage** (life happens); every restart
   lands on Relief, not on a record.

# Tone Naming Exploration

**Phase:** 0 — Discovery & Research (added in revision 1)
**Status:** Draft for review — final name is a Phase 1/2 decision with the
product owner; a provisional recommendation is made below so Phase 1 documents
can use consistent language.
**Context:** Phase 0 established the behavioral contract for the challenging
voice (challenge the behavior and the moment, never the person or the past —
`EthicalConsiderations.md` §3). The review asked for alternatives to the
working label "Direct," with UX rationale.

---

## 1. What the Names Must Do

Naming the two modes is not cosmetic; the names are shown at the single most
consequential choice in onboarding and they set the user's expectations for
every line of copy afterward. Evaluation criteria:

| # | Criterion | Why it matters |
|---|---|---|
| C1 | **Expectation accuracy** | The name must predict the voice. A user who expects drill-sergeant and gets dry wit feels cheated; one who expects respect and gets barked at feels attacked. |
| C2 | **No moral hierarchy in the pair** | Neither name may read as the "strong" or "weak" choice. "Brutal vs. Gentle" frames gentle-choosers as fragile — a shame tax on the safer option. |
| C3 | **Safe self-selection** | The name must not specifically attract self-punishment. "Brutal" is a magnet for users in shame spirals (the adverse-selection risk). |
| C4 | **Extensibility** | The tone system will grow (the philosophy packs, e.g. the Stoic pack, are effectively additional voices). Names should belong to an open set. |
| C5 | **Localization robustness** | Idiomatic names ("Real Talk," "Straight Up") translate poorly. |
| C6 | **Marketability** | The mode choice is a screenshot moment; the pair should be instantly graspable in a store listing. |

## 2. Candidate Sets

### Set A — Adjective pairs (voice described as a property)

| Pair | Assessment |
|---|---|
| **Direct / Gentle** (working labels) | Accurate (C1 ✓), translatable (C5 ✓). Weakness: mild hierarchy — "Direct" flatters, "Gentle" can read as the concession option (C2 ✗). Serviceable fallback. |
| **Firm / Kind** | Warmer than Direct/Gentle; "Firm" avoids aggression connotations. Still slight hierarchy; "Kind" implies the other is unkind (C2 ✗). |
| **Bold / Calm** | Nicely non-hierarchical (both aspirational). But "Calm" mispredicts the nurturing voice (it's warm, not just quiet) — C1 partial. |
| **Blunt / Soft** | "Blunt" is honest about the register but carries mild negativity; "Soft" is a loaded word for the target audience (C2 ✗, C3 risk inverted — may shame gentle-choosers). Rejected. |

### Set B — Verb/energy pairs (voice described as what it does)

| Pair | Assessment |
|---|---|
| **Push / Ease** | Behaviorally accurate and refreshingly concrete. Risks: "Push" can promise pressure beyond the contract (C1 partial); "Ease" could read as low-effort mode. |
| **Spark / Steady** | Evocative, non-hierarchical (C2 ✓), marketable (C6 ✓). Abstract enough to need a one-line explainer (C1 partial). Strong second choice. |

### Set C — Persona names (voice described as who is speaking)

| Pair | Assessment |
|---|---|
| **The Coach / The Friend** | **Recommended.** See §3. |
| The Coach / The Companion | Same virtues; "Companion" is colder and longer than "Friend." |
| The Trainer / The Mentor | Both read as authority figures; the pair loses its contrast (C1 ✗). |

## 3. Recommendation: Voices, Named as Personas — "The Coach" and "The Friend"

Reframe the feature itself from *modes* to **Voices**: at onboarding the user
chooses **who talks to them about time**.

Rationale against the criteria:

- **C1 Expectation accuracy:** Everyone has a precise prior for how a good
  coach talks — demanding, on your side, zero interest in your excuses,
  zero contempt. That prior *is* the behavioral contract. Likewise "a good
  friend" predicts the nurturing register exactly (warm, honest, wants you
  to get up). The names carry the content-style contract culturally, for
  free.
- **C2 No hierarchy:** A coach and a friend are both fully adult
  relationships to choose. Neither is the weak option; picking The Friend
  is not an admission, it's a preference. This is the clearest advantage
  over every adjective pair.
- **C3 Safe self-selection:** A user seeking self-punishment gets no
  promise of it from "The Coach" — coaches famously don't accept
  self-flagellation as effort. The name steers the vulnerable segment
  *toward* the contract, not past it.
- **C4 Extensibility:** Personas form an open set. The optional philosophy
  pack (`FeatureIdeaAssessment.md` §6) becomes **The Stoic** — a third
  voice, off by default, with its own contract. Future candidates (The
  Poet, a recorded past-self voice) slot in without renaming anything.
  Adjective pairs cannot grow this way.
- **C5 Localization:** "Coach" and "friend" are near-universal concepts;
  persona naming survives translation better than register adjectives.
- **C6 Marketability:** "Choose who talks to you about time" is a
  first-class store screenshot and a one-line pitch of the whole tone
  system.

**Risks and mitigations:**

- *Persona ≠ character.* The voices must remain register, not chatbot
  personality; no first-person ego, no avatars talking back
  (`MicrocopyStrategy.md` §2.2 rule stands: the app has no "I").
- *"Coach" gym connotation.* Onboarding preview (three sample lines per
  voice, already planned) calibrates expectations before commitment.
- *Gendering risk in some locales* — style guides must keep both voices
  ungendered.

## 4. Decision Requested

- **Adopt "Voices" as the system frame**, with **The Coach** and **The
  Friend** at launch, pending product-owner ratification in the Phase 1
  review. Phase 1 documents use these names provisionally (marked as
  provisional in `MVPDefinition.md`).
- Fallback if rejected: **Direct / Gentle** (Set A working labels) — safe,
  accurate, less extensible.
- Naming of the philosophy pack voice (**The Stoic**) travels with this
  decision.

---

## 5. Round 2 — Parallel Exploration (during Phase 2; does not block UX work)

Per the Phase 1 review direction, naming continues as a parallel design
exploration. All Phase 2 UX documents use **The Coach / The Friend** as
provisional labels; every artifact treats the label as a swappable string
(the voice *contract* is the stable object — `Microcopy.md` §2–3 defines
voices by contract, not by name).

### 5.1 What Round 1 settled vs. left open

Settled: the **"Voices" system frame** (personas over adjectives) survives
all Phase 2 design work well — "choose who talks to you about time" turned
out to be the natural onboarding framing (`../ux/Onboarding.md` screen 2).
Open: whether *Coach/Friend* are the best two personas, and how names
should be *presented* at choice time.

### 5.2 Additional persona candidates surfaced by Phase 2 work

| Pair | Notes |
|---|---|
| The Coach / The Friend (incumbent) | Strong priors; "Coach" carries slight gym/fitness scent; "Friend" is warm and plain |
| **The Trainer / The Companion** | "Trainer" sharpens the challenge promise but narrows to fitness harder than Coach; "Companion" is Finch-adjacent vocabulary — risk of wellness-app association |
| **The Straight Talker / The Encourager** | Maximally descriptive; clunky as product nouns; poor localization |
| **The Spark / The Steady** (persona-ized Set B) | Evocative, ungendered, ownable; abstract enough to *require* the preview — which we mandate anyway. Promoted to a serious alternate |
| Named human personas ("Sam / Ren") | Rejected: names imply characters/chatbots (violates the no-ego rule, `MicrocopyStrategy.md` §2.2) and gender/culture assumptions |

### 5.3 Presentation insight (matters more than the label)

Wave 2 prototype testing (H6) should test **sample-lines-first
presentation**: the choice screen can lead with each voice's three sample
lines and reveal the *name* second (or even after selection). If
comprehension holds, the label's weight drops further — users choose the
*voice they heard*, not the noun. This would also let labels be refined
post-launch without re-onboarding anyone (the contract, corpus, and
choice persist; only the display string changes).

### 5.4 Decision timeline

- **Now → Phase 2 review:** provisional labels stand; no UX work blocked.
- **Wave 1/2 research:** name-comprehension + connotation probes ride
  along (zero added sessions); Spark/Steady tested as alternate against
  Coach/Friend.
- **Final ratification deadline: end of Phase 5** (design system), before
  store-listing assets and the launch corpus's choice-screen copy are
  frozen. Labels are display strings until then by architecture
  (`../ux/ContentSystem.md` voice dimension uses stable ids `coach` /
  `friend` regardless of display name).

---

## 6. Round 3 — Continued Exploration (Phase 2 review resolution)

**Constraint (binding):** Do **not** rename anything across the repository.
Coach / Friend remain temporary display labels. Stable internal ids remain
`coach` / `friend`. This section evaluates alternatives only.

### 6.1 Candidates under evaluation

| Pair | Family |
|---|---|
| Coach / Friend *(current provisional)* | Personality |
| Coach / Guide | Personality |
| Coach / Companion | Personality |
| Challenger / Supporter | Energy-of-role |
| Mentor / Ally | Personality |
| Spark / Steady | Energy |

### 6.2 Evaluation grid

Scores: ● strong · ◐ mixed · ○ weak

| Pair | Emotional clarity | Localization | Onboarding comprehension | Extensibility | Inclusiveness | Marketability |
|---|---|---|---|---|---|---|
| Coach / Friend | ● / ● | ● | ● | ● (Stoic slots in) | ● | ● |
| Coach / Guide | ● / ◐ | ● | ◐ (Guide vague) | ● | ● | ◐ |
| Coach / Companion | ● / ● | ● | ● | ● | ◐ (wellness/Finch scent) | ◐ |
| Challenger / Supporter | ● / ● | ◐ | ● | ◐ | ◐ (Challenger can read combative) | ◐ |
| Mentor / Ally | ◐ / ● | ◐ | ◐ | ◐ | ● | ◐ |
| Spark / Steady | ● / ● | ● | ◐ (needs samples) | ● | ● | ● |

### 6.3 Personality names vs energy names

- **Personality names** (Coach, Friend, Mentor, Ally, Companion, Guide)
  borrow cultural priors for *how someone talks* — strong for onboarding
  comprehension when samples are short; risk: implying a character/chatbot
  (banned by no-ego rule) or importing baggage (gym Coach, wellness
  Companion).
- **Energy names** (Spark / Steady, Challenger / Supporter) describe
  *how the moment feels*, aligning cleanly with Emotional Temperature
  (`ContentSystem.md` §1.4) and avoiding character implication. Risk:
  lower unaided comprehension — sample-lines-first presentation (§5.3)
  becomes mandatory, not optional.

**Recommendation (direction, not a rename):** Prefer **energy-describing
names** for long-term brand (Spark / Steady currently leads that family),
*or* keep one personality pair if Wave 1/2 shows Spark/Steady needs too
much explanation. Do not decide until research; do not propagate any
rename before Phase 5.

### 6.4 Standing rules while exploration continues

1. User-facing copy may say "voice" without naming until choice screen.
2. Docs and code keep ids `coach` / `friend`.
3. Display strings are a single localization key each — swap cost is one
   string change, not a refactor.
4. Future pack voices (Stoic) are energy-or-tradition names, never
   invented human names.

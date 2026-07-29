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

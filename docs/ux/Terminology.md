# Terminology — Internal Canonical Terms

**Phase:** 2 — UX Documentation (added per Phase 2 review resolution)
**Status:** Draft for review
**Purpose:** Terminology audit outcome. Separates **user-facing UX copy**
from **internal architectural names**. Does not rename user-facing
strings in the product; establishes one internal canonical term for the
two-minute start mechanic.

---

## 1. Audit finding: "Start Now"

| Context | Current use | Problem |
|---|---|---|
| User-facing button / affordance | "Start" / "Start · 2 min" | Fine — verb-first, concrete (`Microcopy.md` terminology law) |
| Feature name in Phase 0–1 docs | "Start Now" | Reads as marketing copy; ambiguous in architecture (now vs later) |
| Loop / engineering discussion | mixed "start", "Start Now", "session" | Session collides with engagement metrics; Start Now is not a type name |

**Decision:** Treat **"Start Now" as UX/marketing heritage only** — not as
the internal architecture term. User-facing copy remains **"Start"** (with
optional "· 2 min"). Docs and engineering adopt **MicroStart** as the
canonical internal name for the mechanic.

## 2. Candidates evaluated

| Candidate | Pros | Cons |
|---|---|---|
| **MicroStart** | Matches behavioral science (sub-threshold / tiny start); unique; ritual-friendly ("Tiny Start" as ritual display); no "now" ambiguity | Slightly coined |
| TinyStart | Plain; aligns with Tiny Habits language | Generic; trademark/noise in industry |
| Activation | Clinical EF term (accurate) | Cold; medical scent; poor ritual language |
| FirstStep | Descriptive | Vague (first of what?); implies sequence |
| Start Ritual | Ritual-framework aligned | "Ritual" in code/identifiers is heavy; user-facing "ritual" optional |

## 3. Recommendation

> **Internal canonical term: `MicroStart`**
>
> - **Ritual display name (philosophy / marketing optional):** Tiny Start
>   (`Rituals.md`)
> - **User-facing button copy:** Start · 2 min (unchanged)
> - **Legacy phrase "Start Now":** allowed in historical Phase 0–1 docs;
>   new docs and Phase 3+ architecture use MicroStart

### Rationale

1. Names the *size* of the ask (the behavioral mechanism), not the
   urgency of the moment ("Now" implied pressure — conflicts with calm
   register).
2. Distinguishes the ignition device from Pomodoro "sessions" and from
   generic "starts" in analytics prose ("MicroStarts per day").
3. Maps cleanly to ritual language (Tiny Start) without forcing "ritual"
   into code identifiers.
4. Stable id form: `microstart` (events, types, module names).

## 4. Glossary (authoritative going forward)

| Term | Layer | Meaning |
|---|---|---|
| **Start** | UX copy | Button / verb the user sees |
| **MicroStart** | Internal / architecture / metrics | The two-minute honest start mechanic |
| **Tiny Start** | Ritual framework | The ritual name for a MicroStart |
| **Start Now** | Legacy | Historical feature label; do not use in new architecture docs |
| **Pulse** | UX + internal | Scheduled awareness notification |
| **Speak Time** | UX + internal | Spoken clock feature |
| **Intention** | UX + internal | Optional single string |
| **Voice** | UX + internal | Challenging/nurturing register (`coach`/`friend` ids) |
| **Content Engine** | Internal | Behavioral content system |
| **Notice / Offer / …** | Behavior model | Wake Loop transitions |

## 5. Scope of rename in this revision

- New and revised Phase 2 docs use **MicroStart** where the mechanic is
  meant (EmotionalJourney, BehaviorChangeModel, EmptyStates, Rituals,
  BehaviorArchitecture, AntiGoals review criteria).
- Phase 0–1 historical documents are **not** mass-rewritten (avoid churn);
  they remain understandable; Phase 3 must use MicroStart.
- User-facing copy catalogs (`Microcopy.md`) keep **Start** as the button
  term — no change.

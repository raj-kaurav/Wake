# Feature Roadmap

**Phase:** 1 — Product Documentation
**Status:** Draft for review
**Roadmap philosophy:** Horizons with entry criteria, not dates. A feature
advances when its evidence gate opens, never because a quarter ended.
Every listed item has already passed concept triage
(`../research/FeatureIdeaAssessment.md`); items rejected there do not
appear. The constitution applies at every horizon.

---

## Horizon 1 — MVP: The Loop

*Scope contract in `MVPDefinition.md`. Everything here exists to prove the
core loop: feel time → start small → in a chosen voice.*

| Feature | One-line scope |
|---|---|
| **Time Awareness Widget** | Home-screen day-shape with granular remaining-time framing; Android + iOS (fidelity tiered per platform budgets) |
| **Start Now** | One button → two-minute honest timer → genuine completion moment; optional single intention string |
| **Voice system** | Choice of two voices (challenging/nurturing; names pending ratification — `../research/ToneNamingExploration.md`) with preview at onboarding, one-tap switch forever |
| **Content Engine** | Voice- and slot-aware functional content (reframes, time facts, prompts, permissions, sparse quotes) powering widget, notifications, start & completion screens, and lapse re-entry |
| **Speak Time (tiered)** | Android: scheduled on-device TTS with quiet hours & instant mute. iOS: pre-rendered notification-sound approximation — ships only if spike H14 passes; else v1.x |
| **Awareness pulses** | User-scheduled notification cadence within wake window; every pulse carries the Start action |
| **Lapse re-entry** | Weightless return experience: today + button + fresh-start line; no record of absence |

## Horizon 2 — Deepening the Same Loop (post-MVP, evidence-gated)

*Nothing new conceptually; the same loop on better surfaces and with earned
configurability.*

| Feature | Entry criteria (gate) |
|---|---|
| **Lock-screen widgets / AOD presence** | MVP widget retention validated (H1 signal positive); platform effort sized in Phase 3 |
| **Watch complications & watch Speak Time** | Same; watch reach justifies the surface for S2/S3 |
| **"The Stoic" philosophy pack** | Optional voice + reflective life-scale widget faces; **disabled by default, explicit consent, dedicated ethics review passed** (`../research/EthicalConsiderations.md` §4.2). Gate: voice system stable, ethics review scheduled, no G4 warning signs in the base product |
| **Live wallpaper (Android)** | Widget visual language proven; battery budget verified |
| **Calendar-aware granularity** | "40 min until your next meeting — enough to start." Gate: users request it in research (not assumed); read-only calendar permission UX passes the five-decision ceiling |
| **Speak Time iOS parity improvements** | Platform API changes, or spike results improving on H14's tier |
| **Voice-recorded self-prompts** | "Message from past-you" implementation intentions. Gate: H-series research shows demand; audio infra exists from Speak Time |
| **Framing & duration personalization** | Remote-config experiments (H2, H3) graduate into user-facing settings only where data shows meaningful heterogeneity |

## Horizon 3 — Exploratory (research alongside, never promised)

| Idea | Standing note |
|---|---|
| Additional voices (e.g., "The Poet"; localized voice character sets) | Voices are Wake's only content growth axis; each new voice = full contract + corpus + review cost (`MicrocopyStrategy.md` §3.5) |
| Single private rhythm hint ("you start easiest 9–11am") | The only statistics-adjacent idea allowed a hearing; must pass P1 ("felt, not tracked") in a dedicated design review |
| Desktop/menubar presence | S2 users live at desks; awareness layer may belong there; large surface-area cost |
| On-device-AI content selection | Selection, not generation; only if it stays local (P11) and reviewable (no unreviewed lines — ethics checklist) |

## Permanently Out (constitutional)

Task lists & projects · schedules/time-blocking · streaks & badges ·
statistics dashboards · social feeds/accountability graphs · cloud AI coach ·
screen-time reports · regret simulation (failed ethics at concept) ·
engagement-driven anything. Rationale: `OutOfScope.md`.

## Sequencing Logic (why this order)

1. MVP proves the loop with the fewest moving parts (P13); Speak Time's
   platform risk is contained by tiering so it cannot delay the loop.
2. Horizon 2 spends only on surfaces where the *proven* loop gains reach
   (lock screen, watch) or earned depth (philosophy pack after trust is
   established) — no new mechanics until the first one demonstrably works
   (P12).
3. Horizon 3 stays exploratory because each item risks a constitutional
   principle (P1, P5, P11, P13) and must argue its way in through the
   amendment process, not drift in through enthusiasm.

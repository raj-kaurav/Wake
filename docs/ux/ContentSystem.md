# Content System — Structured Behavioral Content Architecture

**Phase:** 2 — UX Documentation (expanded per Phase 1 review feedback)
**Status:** Draft for review
**Purpose:** Expand the Content Engine from a concept into a structured,
scalable behavioral content system: taxonomy, schema, selection logic,
authoring pipeline, and growth model (voices, packs, locales). This is the
UX-side specification; Phase 3 defines the data/storage implementation.

**What the Content Engine is:** the single system that supplies every word
Wake says in its behavioral moments. It is infrastructure (per the Phase 0
decision) — there is no browsable content surface (P5).

---

## 1. Taxonomy

### 1.1 Content types (the behavioral job)

| Type | Job (loop transition served — `BehaviorChangeModel.md`) | Example (Coach) | Example (Friend) |
|---|---|---|---|
| **T1 Reframe** | Shrink the imagined task (competing-loop intercept 1) | "You don't need ready. Ready comes after." | "It's allowed to start badly." |
| **T2 Time fact** | Raise time salience, granular & finite (→1 NOTICE) | "This week is 40% done." | "6 hours of today are still yours." |
| **T3 Action prompt** | Implementation-intention scaffold (1→2, 2→3) | "When this sounds, open the file. That's all." | "Just open it — that counts." |
| **T4 Permission** | Lower emotional cost; includes rest permission (2→3; A6 guard) | "Two bad minutes beat zero perfect ones." | "If today needs rest, rest. The button keeps." |
| **T5 Quote** | Sparse seasoning; borrowed authority (any) | Seneca on time (attributed, verified) | same pool, gentler selections |
| **T6 Completion** | Bank the win honestly (4→5 CLOSE) | "Started. That was the hard part." | "You began. That's today's win." |
| **T7 Fresh start** | Close the past, open now (L2) | "Clean week. Pick one thing." | "A fresh page — begin anywhere." |

Caps: T5 ≤ 10% of any rotation. T6/T7 are dedicated-slot-only types.
(T6/T7 formalize what Phase 1 treated as slot-bound content — making them
types keeps the schema uniform.)

### 1.2 Context slots (the delivery moment)

| Slot | Surface(s) | Window | Eligible types |
|---|---|---|---|
| S1 morning | widget footer, first pulse | wake +0–2h | T2, T3, T4 |
| S2 midday | widget, pulses | midday band | T1, T2, T3 |
| S3 evening | widget, late pulses | last 3h of wake window | T2 (remaining-framed), T4 |
| S4 pre-start | start screen | on view | T1, T3, T4 |
| S5 completion | timer end screen/notification | on event | T6 only |
| S6 post-lapse | home & widget after gap ≥ threshold | first view | T7, T4 |
| S7 landmark | overrides S1/S2 on Mon/month-start | per calendar | T7, T2 |
| S8 edge/error | permission denied, TTS unavailable, etc. | on event | dedicated edge lines (see §5) |

### 1.3 Dimensions (metadata every line carries)

- **voice:** coach | friend | (future: stoic, …) — every line belongs to
  exactly one voice; no "shared neutral" lines except Speak Time's clock
  utterance.
- **framing:** opportunity | depletion | neutral (H2 experiment axis;
  depletion lines gated to Coach by default pending H2).
- **intensity:** 1-calm | 2-standard | 3-kinetic — selection respects the
  user's context (S6 post-lapse never serves intensity 3; late-night
  serving caps at 1 — the "Maya at 23:00" rule, D12).
- **emotional_temperature:** see §1.4 — the felt register of the line,
  orthogonal to voice/type/slot.
- **landmark-eligible:** bool (fits fresh-start framing).
- **locale:** BCP-47; launch = en only, schema ready for more.
- **a11y note:** pronunciation/screen-reader hints where phrasing is
  ambiguous aloud.

### 1.4 Emotional Temperature (new dimension)

**Emotional Temperature** is the felt register of a line — how the moment
should *land* emotionally — independent of who is speaking (voice), what
job the line does (type), or when it is delivered (slot/context).

| Value | Felt as | Typical homes |
|---|---|---|
| **Calm** | Unhurried orientation | S1 mornings; widget default |
| **Focused** | Clear, kinetic-but-kind forward lean | S4 pre-start; T3 prompts |
| **Grounded** | Steady, non-dramatic presence | Midday; Speak Time adjacent copy |
| **Reflective** | Quiet looking-back-without-ledger | S3 evenings; landmark soft |
| **Urgent** | Time-near without threat theater | Rare; Coach + depletion arm only; never S6/late-night |
| **Recovering** | "I'm still welcome" | S6 post-lapse; first post-gap pulse (**required**) |
| **Celebratory** | Proportionate warmth | S5 completion (T6) only; never inflated |

**How it differs from adjacent dimensions:**

| Dimension | Answers | Emotional Temperature does not |
|---|---|---|
| **Voice** | *Who* is speaking (Coach / Friend contract) | Change mid-voice; both voices own all temperatures |
| **Content type** | *What job* the line does (reframe, prompt…) | Replace type — a T4 Permission can be Calm or Recovering |
| **Context / slot** | *When / where* it is served | Equal slot — S2 can serve Focused or Grounded |
| **Intensity** | *How much energy* (1–3) | Equal intensity — intensity-1 Calm ≠ intensity-1 Recovering |

**Selection constraints (documentation; no implementation yet):**

- S6 / gap-return / respectful-silence downgrade moments: **Recovering**
  only (or Calm as fallback) — never Urgent, never Celebratory
  (`EmotionalJourney.md` Relief-before-Confidence).
- S5 completion: **Celebratory** or Calm; never Urgent.
- Late-night / D12: Calm, Grounded, or Recovering; Urgent banned.
- Urgent requires intensity ≤ 2 and Coach voice pending H2; Friend never
  serves Urgent.

**Future use cases (schema ready; not MVP behavior):**

1. **Adaptive delivery** — after aversive-use signals or Coach→Friend
   switches, prefer Recovering/Calm for a cooldown window.
2. **Personalization** — user pacing preference ("softer mornings") maps
   to temperature filters without inventing a third voice.
3. **Pacing across the day** — Morning Calm → Midday Focused → Evening
   Reflective as a default arc; landmarks may insert Reflective/Recovering.
4. **Recovery after lapse** — temperature lock to Recovering until one
   post-return MicroStart closes, then unlock (implements the emotional
   arc in content selection).

## 2. Line Schema (canonical record)

```yaml
id: t1-coach-0042            # type-voice-serial, immutable
type: T1                     # taxonomy §1.1
voice: coach
slots: [S2, S4]              # where it may serve
framing: neutral
intensity: 2
emotional_temperature: focused  # §1.4
landmark_eligible: false
locale: en
text: "You don't need ready. Ready comes after."
char_count: 38               # enforced against surface budgets
review:
  ethics_checklist: passed   # EthicalConsiderations §5, per line
  reviewer: <editorial owner>
  date: 2026-XX-XX
status: active               # draft | active | retired
version_introduced: content-v1
notes: "CBT-derived reframe; see EvidenceBasedInterventions §3.2"
```

Rules: `text` is final display copy (no runtime templating except time
values in T2 — the only interpolation allowed, e.g. `{remaining_hours}`);
retired lines keep their ids forever (telemetry integrity); every line
traces to a mechanism note.

## 3. Selection Algorithm (deterministic, local, explainable)

On each serving request `(surface, slot, voice, now, user-state)`:

1. **Filter:** status=active ∧ voice ∧ slot ∧ locale ∧ intensity ≤ context
   cap ∧ framing matches current config/experiment arm ∧
   emotional_temperature ∈ allowed set for (slot, user-state).
2. **Landmark override:** if today is a landmark (Monday, month-start,
   post-gap return) and slot ∈ {S1, S2}, re-filter to landmark_eligible/T7
   first; fall through if empty.
3. **Recency suppression:** exclude lines served in the last N days
   (default N=10 per line, N=2 per type within a slot) from a local
   serving log (on-device only, capped size).
4. **Type weighting:** slot-specific weights (e.g., S4: T3 50%, T1 30%,
   T4 20%); T5 global cap enforced here.
5. **Weighted random** among survivors; if survivors < 3, relax recency
   before relaxing anything else (predictability of *kind*, variety of
   *instance*).

Properties this guarantees: no repeats in short windows (anti-habituation,
R1), no intense lines at fragile moments (R9), explainable output (any
served line can be traced to filters — required for content debugging and
ethics audits).

## 4. Anti-Habituation Depth Requirements

Minimum active variants per (voice × slot) cell, derived from recency
windows: **≥12** for daily-fire slots (S1–S3), **≥15** for S4/S5 (highest
frequency), **≥6** for S6/S7. Launch corpus estimate reconfirmed:
2 voices × (3×12 + 2×15 + 2×6) ≈ **156 minimum, 400–800 with healthy
depth** — matching `../product/MVPDefinition.md` F4. Cells below minimum
block release (content CI check, Phase 4).

## 5. Edge & Error Register (S8)

Tone systems break character in edge states; ours must not (D8). Every
edge state is authored in both voices, same review pipeline:

notification permission denied · exact-alarm permission denied (Android) ·
TTS voice unavailable · OEM battery restriction detected · timer killed by
OS · widget stale-data state · storage failure. (Full copy in
`Microcopy.md` §6.)

## 6. Authoring Pipeline & Governance

1. **Draft** against a mechanism (must cite type + research note).
2. **Ethics checklist** per line (`../research/EthicalConsiderations.md`
   §5) — recorded, not rubber-stamped; rejection rate monitored (R4 signal
   in both directions).
3. **Voice review** by editorial owner against the voice contract
   (`Microcopy.md` §2–3): Coach lines tested for bully-drift, Friend lines
   for toothlessness/saccharine-drift.
4. **Read-aloud pass** (lines are heard via screen readers and possibly
   TTS; rhythm matters).
5. **Release** as a versioned content package (`content-vN`); line-level
   kill-switch = status flip in a point release.

No runtime-generative content, v1 and foreseeable: every shipped line has
passed human review (constitutional consequence of P4/P8; also the AI
Coach exclusion rationale).

## 7. Telemetry Hooks (within the P11 contract)

Aggregate only: serve counts per line, slot conversion (pulse→start) per
line-cohort, disable-following-serve signals (R4/R9 detection). No
individual content-history profiles; the serving log stays on-device.

## 8. Scalability Model

- **New voice = a pack:** voice definition (contract, style guide section)
  + full cell coverage (§4 minimums) + optional palette/widget-face set +
  ethics review. "The Stoic" (Horizon 2) is exactly this shape, plus its
  consent gate; the schema needs nothing new.
- **New locale:** full corpus × voices re-authored (not translated
  literally — voice contracts re-expressed culturally); T2 templates
  localize units/formats. The cost model in `MicrocopyStrategy.md` §3.5
  stands.
- **New slot/type:** requires this document's revision + constitution
  check (new slot = new interruption surface = P9 review).
- **Experiments:** framing/intensity arms select via config, never via
  unreviewed lines.

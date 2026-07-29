# Behavior Architecture — Authoritative Behavioral Contract

**Status:** **FROZEN / ARCHITECTURALLY AUTHORITATIVE** (D-007)
**Phase:** Bridge (Phase 2) — binding on all Phase 3+ technical design
**Purpose:** Behavioral equivalent of an API contract. No technical design
may exist without explicit mapping to this matrix.

**Canonical language:** `../product/LanguageSystem.md` (MicroStart,
VoiceA/VoiceB, Ritual names).

Every Phase 3 technical proposal **must** answer:

1. Which **behavior transition** does this support?
2. Which **ritual** does it belong to?
3. Which **emotional state** does it reinforce?
4. Which **metric** validates it?
5. Which **anti-goal** does it protect against?
6. Which **product principle** does it satisfy?

Proposals that cannot answer all six are rejected until they can.

---

## 1. MVP Behavior Matrix

| Ritual / surface | Behavior transition(s) | Emotional goal | Success signal | Anti-goal / ethical guardrails | Principles |
|---|---|---|---|---|---|
| **Morning Awareness Ritual** (Day Dots widget + S1) | → Notice; Identity→Notice over tenure | Calm orientation | Widget retained; H1 conversion; H8 calm | A2 checking; A5 totalization; rest face | P1, P2, P10 |
| **MicroStart Ritual** (affordance + timer + close) | Offer→Start→Momentum→Reflection | Action → proportionate Confidence | MicroStarts/user/day; ≤10s to start; honest close | A1 engagement; A4 scorekeeping; P8 120s | P2, P5, P8, P13 |
| **Voice system** (`VoiceA` / `VoiceB`) | Unblocks Motivation; protects Offer→Start | Chosen care; parity | Preview choice; ≤2-tap switch; H6/H7 | P4 never shame; P9 never paywall switch | P4, P9 |
| **Content Engine** | Notice, Offer, Reflection, Fresh Start | Per Emotional Temperature | Line-cohort conversion; Recovering post-gap | A7 relocation; no runtime generative | P4, P12 |
| **Midday Reset Ritual** (pulses / Speak Time) | Rest→Notice→Offer | Grounded / Focused hand-on-shoulder | User-scheduled; action rate; respectful-silence | A3 dependence; A6 rest; zero unsolicited | P5, P9 |
| **Speak Time** (tiered) | → Notice (absorption interrupt) | Neutral lighthouse | H5 retention; a11y coexistence | A2 vigilance; battery honesty; OS Focus | P8, P10 |
| **Fresh Start Ritual** (lapse re-entry) | Return → **Relief** → Fresh Start → Offer | "I'm still welcome." | Return-after-gap; MicroStart ≤24h | A7; P3; D6; Recovering lock; no auto-re-escalate | P3, P4, D12 |
| **Evening Reflection Ritual** | Notice / Rest | Reflective; rest permitted | Kind day-close; no audit | A5/A6 | P1, P3 |
| **Onboarding** (container) | Curiosity→Hope→ first Offer | Under-promised hope | ≤5 decisions; ≤60s; session-1 MicroStart | P6; no permission wall | P6, P9 |
| **Retreat / Settings** | Enables P9 across rituals | Competence; control | Quiet-today; opt-out without loss | A8 tinkering (≤12 settings) | P9, P11 |

## 2. Domain vocabulary (engineering must match)

| Domain concept | Canonical name |
|---|---|
| Two-minute start mechanic | `MicroStart` |
| Running instance | `MicroStartSession` |
| Completion event | `MicroStartCompleted` |
| Challenging voice | `VoiceA` |
| Nurturing voice | `VoiceB` |
| Content catalog | `ContentEngine` |
| Day-shape widget (V1) | `DayDotsWidget` |
| Gap-return one-shot | `FreshStartFlag` (boolean, not a counter) |

## 3. Invariants (non-negotiable in implementation)

1. No persisted "days missed" or start-history UI model — even if "only
   internal" (leak risk to P1/P3).
2. MicroStart duration promise is literal (default 120s); no auto-extend.
3. Notifications: user-scheduled or user-caused only.
4. Content lines always carry the five mandatory metadata fields
   (LanguageSystem §5).
5. Voice stored as `VoiceA`|`VoiceB`; display label resolved at the edge.
6. Fresh Start: layout identical; temperature Recovering until one
   post-return MicroStart completes.

## 4. Change control

Matrix amendments = Product Decision Log entry + product-owner approval.
Shipping a surface not on this matrix is a defect.

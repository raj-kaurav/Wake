# Notification Strategy

**Phase:** 2 — UX Documentation
**Status:** Draft for review
**Purpose:** The complete specification of everything Wake may send,
implementing the research constraints (`../research/NotificationPsychology.md`
§7) as product behavior. The prime directive: **every notification is
user-scheduled or user-caused; zero unsolicited notifications, permanently
(P5).**

---

## 1. The Complete Notification Inventory

This list is exhaustive. A new notification type requires revision of this
document plus a P9 review.

| Type | Trigger | Content | Actions |
|---|---|---|---|
| **N1 Awareness pulse** | User's schedule (F3) | One content line (slot-appropriate) | **Start** · quiet-today |
| **N2 Timer completion** | User's own running timer ends while app backgrounded/locked | T6 completion line + genuine credit | Open (→ Completion) · Again |
| **N3 Timer running** (ongoing/persistent) | Active session | Remaining time, quiet | Stop (honest, no confirm) |
| **N4 Speak Time carrier (iOS tier)** | User's Speak Time schedule | Pre-rendered "It's 12:30" sound + minimal visible text ("12:30") | Start (as N1) |
| **N5 Foreground service notice (Android, only if H15 forces it)** | Speak Time reliability requires a service | Static, honest ("Wake is keeping time.") | Settings shortcut |

**Types that will never exist** (enumerated as tripwires): re-engagement
("we miss you"), streak/status alerts, content marketing ("new quotes!"),
rating requests, seasonal campaigns, "finish setting up" reminders,
social anything.

## 2. Anatomy & Copy Rules

- Primary text ≤ ~40 characters; one idea; user's voice; autonomy-
  supportive (no "should/must/don't forget") — budgets and style in
  `Microcopy.md`.
- Every N1/N4 carries exactly one **Start** action (the exit ramp, P2) and
  one low-key quiet-today action. Nothing else.
- No emoji, no ALL CAPS, no urgency punctuation (D9).
- App icon badge count: **never used.** A badge is a debt marker (P3).

## 3. Scheduling Rules

1. All N1/N4 fire only inside the user's wake window, minus quiet hours.
2. Default state: **off**. Onboarding invites (F1); Settings owns
   thereafter. Suggested cadence 3/day (morning S1, midday S2, evening
   S3) — cadence chosen by the user, capped at hourly.
3. Pulses are suppressed while a timer runs (the prompt's job is done, D5)
   and for a cooldown after a completed start (proposal: 90 min —
   a completed start has earned silence; tune in beta).
4. Quiet-today (from any pulse) silences N1/N4 until the next wake window.
   One tap, silent confirmation, no re-ask.
5. OS Focus/DND is honored absolutely — no critical-alert entitlements, no
   bypass attempts, ever.
6. Landmark mornings (S7) may *re-style* the scheduled morning pulse
   (fresh-start line) — never add an extra one.

## 4. The Respectful-Silence Rule (specification)

Purpose: notifications that are being ignored must quiet themselves —
habituated noise damages both the user and the channel
(`../research/NotificationPsychology.md` §3).

- **Signal:** zero interactions (no Start, no body tap, no quiet-today)
  with the last 14 consecutive delivered pulses (≈ ~5 days at default
  cadence).
- **Action:** cadence halves (e.g., 3/day → morning + evening; then → 1/day
  minimum). One honest, quiet system line accompanies the first downgrade
  (S8 register): "Wake is quieting down — resume anytime in Settings."
  (This is user-caused — their silence — and states a reduction, not a
  plea; it is the only self-initiated notification adjustment in the
  product, and it only ever *reduces*.)
- **Floor:** at continued non-interaction, pulses pause entirely.
- **Restoration:** only by explicit user action in Settings (F6 rule —
  never auto-re-escalate).
- **Interaction with gaps:** absence with no deliveries doesn't count
  toward the signal (undelivered ≠ ignored).

## 5. Permission Strategy (F8 pattern)

- Never at first launch; requested at the moment a user turns on the first
  notification-bearing feature, after a one-line voice-consistent priming
  ("Wake will only send what you schedule.").
- Denial: honest S8 state in Settings with deep link to system settings;
  no repeat prompting; app remains whole (widget + in-app loop unaffected).
- iOS provisional (quiet) delivery: **not used** — quiet delivery would
  gut N1's job and N4's sound; we ask plainly instead
  (`../research/NotificationPsychology.md` §5 reasoning).
- Android 13+ runtime permission and exact-alarm permission are requested
  in the same in-context moment, with the accessibility/time-awareness
  rationale stated honestly (R11).

## 6. Sound & Haptics Grammar

- N1: near-silent by default — a single soft tone distinct from system
  defaults (recognition without alarm); haptic-only option.
- N2: the completion sound is the product's warmest audio moment
  (peak–end, `../research/BehavioralEconomics.md` §9) — brief, resolved,
  never fanfare.
- N4: the spoken time *is* the sound; no additional tone.
- All sounds respect silent mode without exception; Speak Time offers
  headphone-only routing (Android).

## 7. Budget & Telemetry

- Hard ceiling: user's own schedule; at maximal legal settings (hourly
  pulses in a 16-h window + Speak Time) a user could self-configure ~16–32
  daily signals — the UI surfaces a gentle density note at configuration
  time ("That's a lot of Wake. Your call.") but obeys (autonomy, P9, D9).
- Telemetry (aggregate, P11): delivery counts, action rates per slot/line
  cohort, quiet-today usage, downgrade activations, disable-after-pulse
  events (R1/R9 early warning). No individual notification histories
  leave the device.

## 8. Open Items for Beta Tuning

Post-start cooldown duration (90 min proposal) · respectful-silence
thresholds (14 pulses proposal) · default suggested cadence (3/day
proposal) · N1 tone design (with Phase 5). Each ships behind remote config
within pre-committed humane bounds (never exceeding this document's
ceilings).

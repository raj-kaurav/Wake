# Onboarding

**Phase:** 2 — UX Documentation
**Status:** Draft for review
**Purpose:** Detailed specification of the one-time first-run experience.
Constraints inherited: ≤5 decisions, ≤60 seconds to a possible start, zero
permission dialogs, no account (P6). Flow skeleton in `UserFlows.md` F1;
this document specifies each screen's intent, copy direction, and failure
analysis.

**Design stance:** Onboarding is not a tour, a pitch, or a data harvest.
It is *one meaningful choice (the voice) plus three invitations*, and it
ends inside the product's real value. Every screen must survive the
question: "would a skeptical, tired person tolerate this?"

---

## Screen 1 — Welcome (no decision)

- **Job:** Set the register and the honest promise in one breath. No
  feature list, no carousel, no illustration parade.
- **Content:** App name + one line: the philosophy in user language
  (direction: "Days pass quietly. This makes them felt — and makes
  starting small."), one continue button.
- **Tone note:** voice-neutral (no voice chosen yet) — calm, concrete.
- **Anti-patterns excluded:** multi-page value carousels (skipped, then
  resented); "sign in with…" (no accounts exist).

## Screen 2 — Voice choice (decision 1, the meaningful one)

- **Job:** The user decides *who talks to them about time.* This choice
  carries the whole tone system, so it gets the most careful design in
  onboarding.
- **Mechanics:** Two cards (order randomized to avoid position default),
  each with the voice's name, a one-line self-description, and **three
  sample lines** (mandatory preview — H6/H7 safety design; samples drawn
  from real corpus: one T2, one T3, one T6, so users hear the voice in
  action, not a slogan).
- **Default:** The nurturing voice is visually pre-highlighted
  (safety-first default) but an explicit tap is required — no silent
  default path.
- **Safety detail:** The screen's framing question is tone-neutral
  ("Choose how Wake talks to you") — never self-diagnostic ("Do you need
  tough love?"), which would invite shame-driven selection
  (`../research/EthicalConsiderations.md` §3).
- **Copy note:** A quiet "you can switch anytime" line reduces
  choice-stakes anxiety and is true (F7).

## Screen 3 — Your day (decision 2)

- **Job:** One fact Wake genuinely needs: the wake window (it scales the
  day-shape and bounds every pulse).
- **Mechanics:** Two time fields prefilled 07:00–23:00; accept or adjust.
  One screen, no follow-ups (no chronotype quizzes, no weekday/weekend
  splits in MVP).
- **Copy direction (voice-aware from here on):** Coach: "When does your
  day run?" / Friend: "When is your day — roughly is fine."

## Screen 4 — Invitation: time pulses (decision 3, skippable)

- **Job:** Offer scheduled awareness, honestly described, default-off
  posture (P9): the screen invites, never pre-checks.
- **Mechanics:** on/off + suggested cadence (3/day: morning, midday,
  evening) with the wake window shown. Choosing "on" → in-context
  permission flow at confirmation (F8). Skipping is a first-class path
  visually equal to accepting.
- **Honesty requirement:** the example notification shown is a real
  corpus line, and the screen states the zero-spam rule in plain words
  ("Only what you schedule. Nothing else, ever.") — a promise the product
  architecture actually keeps (P5).

## Screen 5 — Invitation: Speak Time (decision 4, skippable)

- **Job:** Introduce the signature feature with platform honesty.
- **Mechanics:** off by default; interval choice if enabled (60 min
  suggested; 15 min available with a gentle note about it being a lot);
  quiet hours default to outside the wake window.
- **Platform copy:** Android: full description. iOS: honest tier ("On
  iPhone, Wake speaks through notifications — it works, with iOS limits.")
  — never promise parity (R5, D9). If H14 failed and the tier isn't
  shipping, this screen is pulses-only on iOS.
- **Battery honesty:** one line at 15-min interval selection (P8).

## Screen 6 — The widget (decision 5, skippable)

- **Job:** Get Wake's primary surface onto the home screen while
  motivation is present.
- **Mechanics:** live preview of the widget as it would look *right now*
  (real time, their wake window — demonstrating, not describing); then
  platform add-flow (Android: `requestPinAppWidget`; iOS: brief visual
  how-to, since programmatic add doesn't exist) — platform asymmetry
  accepted.
- **Skip path:** "later" — Now carries a one-time, dismissible widget
  suggestion that never returns after dismissal (no persistent setup
  nagging).

## Landing — Now (first-run state)

The Start button front and center with an S4 pre-start line; if the user
does nothing else, the first start is one tap away — onboarding ends
*inside* the loop, not at a "you're all set!" dead end. A first-session
start is the activation metric (SuccessMetrics §2); this landing is its
design.

---

## Budget Audit

| Metric | Budget | This design |
|---|---|---|
| Decisions | ≤5 | 5 (voice, window, pulses, speak time, widget) — at cap, nothing may be added without removal |
| Time to possible start | ≤60 s | ~35–50 s at reading pace; screens 4–6 skippable in one tap each |
| Permission dialogs during onboarding | 0 | 0 (deferred to in-context confirmations) |
| Text per screen | ≤2 short lines + samples | enforced in `Microcopy.md` budgets |

## Failure Analysis

- **Skeptic path (skips 4–6):** lands with voice + window only; app fully
  functional; widget suggestion once; pulses/Speak Time discoverable in
  Settings. No degraded-mode messaging anywhere.
- **Abandon mid-flow:** resume at same step on next open (state saved
  locally). No restart, no "continue setup!" notifications (none are
  permitted to exist).
- **Wrong voice chosen under shame** (H7 risk): mitigations are the
  preview realism, the tone-neutral framing, and the 2-tap switch; beta
  watches Coach→Friend early-switch rates.
- **Accessibility:** every screen screen-reader complete; previews
  readable (voice samples are text, not audio-only); time fields use
  platform-native accessible pickers; full flow completable with switch
  access (`Accessibility.md`).

## What Onboarding Never Does (standing exclusions)

No goal-setting wizard · no "what do you want to achieve?" survey · no
notification-permission wall · no email capture · no personalization quiz
· no progress bar theatrics for a 5-screen flow · no dark-pattern
pre-checks (every invitation starts off).

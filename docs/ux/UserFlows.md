# User Flows

**Phase:** 2 — UX Documentation
**Status:** Draft for review
**Purpose:** The canonical flows, each with steps, budgets, interruption
behavior, and edge cases. Every flow names the Wake Loop transitions it
serves (`BehaviorChangeModel.md` §2). Tap/decision budgets are contractual
(D3, P6).

---

## F1 — First Run: install → first start (loop: full pass)

**Budget: ≤5 decisions, ≤60 s to a possible start; zero permissions.**

1. Open → Welcome (one screen, one line of promise, no decision).
2. Voice choice — previews mandatory (3 sample lines each), nurturing
   voice pre-highlighted, explicit tap required. *(decision 1)*
3. Wake window — one screen, default 07:00–23:00 offered, adjust or
   accept. *(decision 2)*
4. Invitation: time pulses (on/off + suggested cadence). Skippable.
   *(decision 3)* — choosing "on" defers the OS permission ask to the
   moment of scheduling confirmation (in-context, F8).
5. Invitation: Speak Time (Android full / iOS tiered description — honest
   platform copy). Skippable. *(decision 4)*
6. Widget suggestion — one screen showing the widget with "add it now or
   later"; platform add-flow if supported, else brief visual instruction.
   *(decision 5)*
7. Land on Now. First-run Now shows S4-flavored pre-start line; the Start
   button is the visual center.

**Edge cases:** kill mid-onboarding → resume same step. Decline everything
→ fully functional app (widget-less, pulse-less: Now + Start still work).
Reinstall → onboarding repeats (local-first).

## F2 — Glance → start (the canonical daily flow; loop 1→5)

1. User glances at home screen; widget shows day shape + granular time +
   content line. *(NOTICE)*
2. Taps widget Start affordance. *(OFFER→START; tap 1 of 1)*
3. Timer opens already running (<1 s cold start). Silence (D5).
4. At 120 s: quiet completion signal (gentle sound + haptic if permitted),
   Completion moment (T6 line). *(CLOSE)*
5. Auto-return to Now after ~8 s or on tap; user leaves. *(REST — session
   ends ≤15 s after close, guardrail)*

**Variants:** continue working past timer end → timer screen quietly ends,
no interjection; phone locked at completion → completion notification
carries the moment. Stop early → §Navigation.md §4 contract.

## F3 — Pulse → start (loop 6→1→3)

1. Scheduled notification: one content line + **Start** action +
   quiet-today action.
2a. Start action (even from lock screen) → Timer running.
2b. Body tap → Now.
2c. Quiet-today → pulses pause until tomorrow's wake window; silent
   confirmation only ("Quiet until tomorrow."), no guilt, no re-ask.
2d. Ignore → nothing. Ever. (No follow-up, no escalation.)

## F4 — Spoken time → start (Android; loop 6→1)

1. At interval boundary within wake window: "It's 12:30." (respects DND,
   quiet hours, headphone-only setting, instant-mute).
2. No further audio. If the user picks up the phone, the widget/pulse is
   the visual affordance (deliberate: the spoken moment stays pure
   awareness — the affordance is one glance away, D2).

**Edge:** media playing → duck-and-speak or skip per user setting (default:
skip during calls, duck during music). Screen reader active → Speak Time
defers to it (never overlaps — P10).

## F5 — Start Now lifecycle (all branches; loop 3→5)

**Start:** from widget / notification / Now. Intention field visible if
enabled: prefilled with last value, editable, skippable — never blocks.
**Running:** remaining time as quiet shape+numeral; stop control visible;
pulses suppressed; leaving the app doesn't stop it (D11 contracts in
`Navigation.md` §5).
**End (three honored outcomes, H4):**

- *Continue working:* screen quietly offers nothing; timer face fades to
  "done" state; user keeps working with Wake silent. (Continuation is the
  user's silent act — never our pitch.)
- *Stop at end:* Completion moment — T6 line, proportionate warmth, done.
- *Never really started / stopped <20 s:* quiet end, no failure state, no
  copy about it; the next pulse arrives as scheduled.

**Repeat:** Completion offers a small "again" affordance (silent repeat,
same intention) — user-initiated only.

## F6 — Lapse re-entry (loop L1→L2; the designed moment)

1. User returns after ≥ gap threshold (proposal: 7 days — Phase 2 review
   decision) via any entry point.
2. Now renders exactly as always (D6) with S6 content: one T7/T4 line
   ("A fresh page — begin anywhere."), no gap acknowledgment, no changed
   layout, no "welcome back."
3. Gap-return flag consumed on first view; second view is a normal day.

**Absolute rules:** absence duration never appears; the words "again,"
"still," "back" are banned in S6 lines; pulses that auto-downgraded during
absence (respectful silence) restore only on explicit user action in
Settings — never automatically re-escalate.

## F7 — Voice switch (safety flow; ≤2 taps from Now, P9)

Now → Settings → Voice → tap other voice (1-line preview shown) → done.
Takes effect everywhere immediately. No confirmation, no "are you sure,"
no exit survey. Switch frequency is aggregate telemetry (H6/H7) only.

## F8 — Permission asks (in-context pattern, used by pulses & Speak Time)

1. User enables the feature in its own context (onboarding invitation or
   Settings).
2. One priming line in the user's voice explains exactly what will happen
   ("Wake will say the time out loud at the times you chose.").
3. OS dialog.
4a. Granted → feature live, confirmation is the feature itself working.
4b. Denied → honest edge copy (S8): feature marked "needs permission" in
   Settings with a direct link to system settings; **no nagging, no
   re-prompt loops**; the rest of Wake is unaffected.

## F9 — Quiet today / retreat flows (P9)

From any pulse: quiet-today (F3c). From Speak Time utterance moment:
volume/mute hardware works instantly; Settings offers one-tap disable.
From widget: removing it is an OS act — Wake never reacts to it (no
"you removed the widget!" anything; aversive-use signals are aggregate
research input only).

## F10 — Settings changes

All settings apply immediately, no save step, no restart. Wake window
changes recompute pulse/Speak Time schedules silently. Analytics opt-out
takes effect immediately with no feature loss (P11).

---

## Flow Coverage Matrix (review aid)

| Loop transition | Covered by |
|---|---|
| →1 NOTICE | F2, F3, F4 |
| 1→2→3 OFFER/START | F2, F3, F5 |
| 3→4→5 SHIFT/CLOSE | F5 |
| 5→6 REST | F2 step 5, F5 end states |
| 6→L1→L2 lapse | F6 |
| Safety/retreat | F7, F8, F9 |

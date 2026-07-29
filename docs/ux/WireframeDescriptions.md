# Wireframe Descriptions

**Phase:** 2 — UX Documentation
**Status:** Draft for review
**Purpose:** Textual wireframes for every screen and surface — layout
regions, element hierarchy, focus order, and state variants — precise
enough for Phase 5 to execute visually and for prototype building (Wave 2
research). Conventions: portrait phone reference; regions listed top to
bottom; `[element]` = interactive; focus order = screen-reader/keyboard
sequence.

---

## 1. Now (root screen)

```
┌──────────────────────────────┐
│  (status area / breathing     │   Region A — Day field:
│   room, no app chrome)        │   the dot-field rendering of today,
│        · · · · · · · ·        │   larger sibling of the widget;
│        ● ● ● ● ◐ · · ·        │   caption beneath:
│   "6h 40m of today left"      │   granular remaining-time text
│                               │
│   "You don't need ready.      │   Region B — Content line (S1–S3
│    Ready comes after."        │   slot; S6 variant post-lapse)
│                               │
│   [ intention: "the deck" ]   │   Region C — Intention chip
│                               │   (present only if set; tap = edit)
│      ┌──────────────────┐     │
│      │  Start · 2 min    │     │   Region D — the Start button:
│      └──────────────────┘     │   visually dominant, min 56pt tall
│                               │
│                        [⚙]    │   Region E — settings entry, small
└──────────────────────────────┘
```

- **Hierarchy:** D > A > B > C > E. The button is the largest tap target
  on screen; the day field is the largest visual area.
- **Focus order:** day-field summary (one utterance) → content line →
  intention → Start → settings.
- **States:** wake window (S1/S2/S3 content + advancing dots) · rest face
  (outside window: dots complete + dimmed, caption "Day complete.", Start
  visually de-emphasized but present) · gap return (identical layout, S6
  line — the only delta) · timer running (this screen is skipped;
  app-open routes to Timer).
- **Absent by design:** navigation bars, date headers, greetings
  ("Good morning, User!"), counts of any kind.

## 2. Timer (running)

```
┌──────────────────────────────┐
│                               │
│           1:24                │   Region A — remaining time,
│        (quiet ring or         │   large numeral + minimal shape;
│         shrinking form)       │   no color alarm as time falls
│                               │
│      "the deck"               │   Region B — intention (if set),
│                               │   small, static
│                               │
│                               │   (deliberate emptiness — D5)
│         [ Stop ]              │   Region C — stop, visible,
│                               │   quiet-styled, single tap
└──────────────────────────────┘
```

- **Behavior:** screen stays awake (optional setting, default on); no
  copy changes during countdown; pulses suppressed; leaving keeps the
  timer running (N3 persistent notification carries it).
- **Focus order:** remaining time (pollable) → intention → Stop.
- **End transition:** at 0:00, soft sound + haptic → Completion. No
  strobe, no fanfare.

## 3. Completion

```
┌──────────────────────────────┐
│                               │
│      "Started. That was       │   Region A — T6 line (the moment)
│       the hard part."         │
│                               │
│      [ Done ]   [ Again ]     │   Region B — two quiet options,
│                               │   Done is default-focused
└──────────────────────────────┘
```

- **Behavior:** auto-yields to Now after ~8 s if untouched
  (interruptible; nothing lost if missed — reopening shows Now). "Again"
  restarts silently with same intention.
- **Variant:** reached via N2 notification when completion happened
  backgrounded — identical content.
- **Anti-patterns excluded:** share buttons, streak displays, "go 10 more
  minutes?" upsells (P8).

## 4. Settings (one screen)

```
┌──────────────────────────────┐
│  ← back        Settings       │
│                               │
│  VOICE                        │
│  [ The Coach   ✓ The Friend ] │  current highlighted; 1-line
│  "sample line preview here"   │  preview of the *other* voice
│                               │
│  YOUR DAY                     │
│  [ 07:00 ] — [ 23:00 ]        │  two native time fields
│                               │
│  TIME PULSES                  │
│  [ on/off ]  [ cadence ]      │  state-first labels
│  [ Quiet today ]              │  always visible shortcut
│                               │
│  SPEAK TIME                   │
│  [ on/off ] [ 15/30/60 min ]  │
│  [ quiet hours ] [ headphones │
│   only (Android) ]            │
│  "Uses a little battery at    │  honesty line (P8)
│   15 min."                    │
│                               │
│  INTENTION                    │
│  [ show on start: on/off ]    │
│                               │
│  PRIVACY                      │
│  [ analytics: on/off ]        │
│  [ About & privacy → ]        │
└──────────────────────────────┘
```

- **Rules:** flat; groups scannable; every control shows current state in
  its label; changes apply instantly (F10); ≤12 tappable settings
  (IA §4). Safety controls (voice, quiet) sit highest.

## 5. Onboarding (6 lightweight screens — full spec in `Onboarding.md`)

Per-screen skeleton: single message region (≤2 lines) + decision region +
[continue/skip]. Screen 2 (voice choice) is the only dense one:

```
┌──────────────────────────────┐
│  "Choose how Wake talks       │
│   to you." (+ switch-anytime  │
│   note)                       │
│ ┌───────────┐ ┌────────────┐  │   two cards, randomized order,
│ │ THE COACH │ │ THE FRIEND │  │   Friend pre-highlighted;
│ │ 3 sample  │ │ 3 sample   │  │   samples are real corpus lines
│ │ lines     │ │ lines      │  │   (one T2, T3, T6 each)
│ └───────────┘ └────────────┘  │
│         [ Continue ]          │   disabled until a card is tapped
└──────────────────────────────┘
```

## 6. About / Privacy

Static, plain-language: what Wake stores (five items, listed), what
leaves the device (analytics description + opt-out state), the
not-a-medical-product note, licenses. No marketing.

## 7. Widget (medium — reference; full spec in `Widgets.md`)

```
┌──────────────────────────────┐
│ ● ● ● ● ● ◐ · · · · · · ·    │  dot field (wake window)
│ "6h 40m of today left"        │  caption (framing per config)
│ "The file hasn't opened       │  content line (S-slot)
│  itself."                     │
│              [ Start · 2min ] │  Start affordance, right-aligned
└──────────────────────────────┘
```

Small widget: dots + caption + Start (no content line). States per
Widgets §4 (rest face, timer mirror, stale face).

## 8. Notifications (reference layouts)

- **N1 pulse:** app icon · line ("14:00. Two minutes, yours if you want
  them.") · actions: [Start] [Quiet today].
- **N2 completion:** line ("You began. That's today's win.") · actions:
  [Open] [Again].
- **N3 running:** "1:24 remaining" · action: [Stop]. Silent, ongoing.
- **N4 (iOS Speak Time):** visible text "12:30" · sound: pre-rendered
  utterance · action: [Start].

## 9. Prototype Notes (Wave 2)

Build screens 1–3 + widget mock + N1 as the clickable core; the H4
end-state variants (three Completion behaviors) and H6 voice-choice
with/without previews are the two test forks; measure time-to-first-start
against the 60 s budget and decision count against the cap.

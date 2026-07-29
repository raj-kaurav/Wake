# Navigation

**Phase:** 2 — UX Documentation
**Status:** Draft for review
**Purpose:** The navigation model. It is deliberately trivial: Wake has six
screens, no tabs, no drawer, no nested stacks. Complexity here would be a
symptom (P13).

---

## 1. Navigation Map

```
                    ┌──────────────┐
   (one-time) ────► │  Onboarding   │ ───► Now (replaces; no back)
                    └──────────────┘
                                            ┌───────────────┐
  widget/notification Start ──────────────► │     Timer     │
                    ┌──────┐   Start        └──────┬────────┘
  widget/notif tap ►│ Now  │ ─────────────►        │ ends/stops
                    └──┬───┘                        ▼
                       │ gear icon           ┌───────────────┐
                       ▼                     │  Completion   │ ─► auto → Now
                    ┌──────────┐             └───────────────┘
                    │ Settings  │ ─► About/Privacy (push, back returns)
                    └──────────┘
```

Rules:

- **Now is the root.** Every path terminates back at Now. There is no
  navigation state to lose.
- **Maximum depth: 2** (Now → Settings → About). Nothing else pushes.
- **Timer and Completion are modal moments,** not navigation destinations:
  no gear, no links out, no way to wander from inside a running start.
- **No tab bar, no drawer, no long-press menus** required for any core
  action (discoverability by visibility only — hidden gestures fail the
  five-second rule and accessibility).

## 2. Entry Points (ranked by expected frequency — D1)

1. Widget Start → Timer (the canonical path; must be < 1 s to running
   timer).
2. Notification Start action → Timer (same contract, from lock screen too).
3. Widget/notification body → Now.
4. App icon → Now (or Timer, if a session is running — never lose a
   running timer to a fresh Now).
5. Completion notification → Completion.

## 3. Back & Exit Behavior

| Context | System back / swipe-home behavior |
|---|---|
| Now | Exits app (nothing to protect) |
| Settings / About | Returns up one level |
| Timer | **Leaves the app, timer keeps running** (notification continues it — D11). Back never cancels a start; stopping is an explicit on-screen act |
| Completion | Returns to Now (moment already banked) |
| Onboarding | Back moves between steps; system back on step 1 exits app; re-open resumes at the same step (no restart punishment) |

## 4. The Stop Control (the only destructive-ish navigation)

Stopping early is a legitimate act, not a failure (P3): the stop control is
visible (no shame-hiding), single-tap, with **no confirmation dialog** —
confirmations imply wrongdoing and add friction to an honest choice. A
stopped session before 20 s simply ends (below the start-count floor);
after 20 s it ends with the standard quiet close, no scolding variant.

## 5. Interruption & Resumption Contracts (D11)

- **Lock/background during Timer:** timer persists; notification shows
  remaining time; unlocking returns to Timer.
- **Call during Timer:** timer continues; no penalty concept exists.
- **Process death:** completion still fires via scheduled notification;
  on next open, if the session's end time passed, show Completion once
  (banked, honest), else resume Timer.
- **Notification arriving during Timer:** pulses are suppressed while a
  session runs (the user is already started — the prompt's job is done;
  D5).

## 6. First-Run vs. Every-Run

Onboarding runs once, ever. Reinstall runs it again (local-first means no
memory — acceptable; the flow is < 60 s). There are no "what's new" tours,
no feature-announcement interstitials, no rating prompts on any navigation
path (P5, D9). Release notes live in the store listing only.

## 7. Platform Notes (behavioral contract; implementation in Phase 3)

- Deep links must not construct artificial back stacks (no "up to a home
  you never visited" chains); Start deep links land in Timer with back →
  exit.
- iOS Live Activity (if adopted post-spike) mirrors Timer state; tapping
  returns to Timer. It is a mirror, never an alternate UI.
- Android widget Start uses a trampoline-free direct intent (cold-start
  budget) — constraint recorded for Phase 3.

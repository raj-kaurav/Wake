# Accessibility

**Phase:** 2 — UX Documentation
**Status:** Draft for review
**Purpose:** Accessibility is Wake's premise, not its checklist (P10): the
founding feature is an accessibility-inspired idea, and the product thesis —
externalized, multi-sensory time — is assistive technology for everyone.
This document sets the launch requirements; Phase 3
(`AccessibilitySupport.md`) covers platform implementation.

**Standard:** WCAG 2.2 AA as the floor for everything; specific commitments
below go further where the product's nature demands it.

---

## 1. The Multi-Sensory Time Contract

Time must be feelable through **sight, sound, and touch** — no single
channel is required:

| Channel | Surfaces | For whom it is primary |
|---|---|---|
| Sight | Widget dot-field, timer face, captions | sighted users |
| Sound | Speak Time, pulse tone, completion sound | blind/low-vision users; anyone mid-absorption |
| Touch | Pulse haptic option, completion haptic | deaf/hard-of-hearing users; silent contexts |
| Text (assistive) | Full text equivalents of every state | screen-reader users |

**Launch test:** a blind user, a deaf user, and a screen-reader user can
each complete the entire core loop (notice time → start → work → close)
without assistance. This is an MVP quality bar
(`../product/MVPDefinition.md` §4), verified per release.

## 2. Screen Reader Specification (VoiceOver / TalkBack)

- **Widget:** one coherent utterance, state-complete: "Today: nine of
  sixteen hours remaining. Six hours forty minutes left. [content line].
  Start two minutes, button." Never dot-by-dot enumeration.
- **Now:** reading order = day state → content line → intention (if set) →
  Start button. The Start button is the first actionable element.
- **Timer:** announces on entry ("Two minutes started"); remaining time is
  *pollable, not chatty* — no automatic per-second or per-15s announcements
  (respect the silence principle D5 for ears too); optional milestone
  announcement at half and near-end (user setting, off by default);
  completion announced warmly (T6 line).
- **Completion:** the T6 line is the announcement; "Again" and "Done"
  clearly labeled.
- **Speak Time coexistence:** Speak Time defers to an active screen reader
  (never overlaps/interrupts VoiceOver or TalkBack speech; if the screen
  reader is speaking at the interval boundary, the utterance is skipped —
  the screen reader user already has spoken time on demand). Documented
  honestly in the feature's settings copy.
- All controls: role, label, and state set; no unlabeled icon buttons
  anywhere (the gear, the stop control, quiet-today — all named).

## 3. Vision

- Contrast: AA minimum everywhere, in both voice palettes, in dark and
  light modes, including widget-over-wallpaper (solution: widgets carry
  their own background, never transparent-over-unknown — a Phase 5
  requirement recorded here).
- Meaning never by color alone: dot fill state (not hue) carries the day;
  timer state is shape + numeral.
- Dynamic type / font scaling to platform maximums: captions scale, the
  dot field yields space before any text truncates; no fixed-height text
  containers.
- Dark mode is not an afterthought: the 23:00 scenario (D12) is a
  dark-mode scenario by default (Phase 5 `DarkMode.md`).

## 4. Hearing

- Every audio signal has a visual+haptic equivalent (completion = sound
  AND haptic AND screen moment; pulses = tone AND banner).
- Speak Time is optional by design and its absence removes nothing from
  the loop (the widget carries the same information).
- No information exists in audio only.

## 5. Motor

- All tap targets ≥ 44×44 pt / 48×48 dp, including widget affordances and
  notification actions.
- The one-tap philosophy (D3) is itself a motor-accessibility feature; no
  gesture-only interactions (no swipe-to-X without a button equivalent),
  no long-press requirements, no drag interactions anywhere in MVP.
- Full switch-access / keyboard navigability: the six screens are shallow
  and linear by design; focus order specified per screen in
  `WireframeDescriptions.md`.
- Timers do not demand fast reactions: nothing in the loop is
  time-pressured *as an interaction* (the two minutes is work time, not UI
  time; the completion screen waits).

## 6. Cognitive

- Reading level ≤ grade 6; one idea per line (`Microcopy.md` §1).
- The five-decision onboarding cap and five-second settings rule (D10) are
  cognitive-accessibility budgets, enforced as tests.
- Predictable structure: no moving navigation, no surprise modals, no
  timed dismissals the user must race (Completion auto-dismiss is
  interruptible and repeatable — reopening shows Now, nothing lost).
- The ADHD-informed checklist (`../research/ExecutiveFunctionADHD.md` §3)
  is treated as cognitive-accessibility requirements: externalized
  intention, zero-step availability, shape-over-digits, weightless failure
  states.

## 7. Vestibular & Motion

- `prefers-reduced-motion` (and platform equivalents) honored everywhere:
  the breathing current-dot becomes a static contrast marker; screen
  transitions become fades; the timer face never pulses.
- No parallax, no large sweeping animations anywhere (also a calm-register
  choice — the accessibility and emotional-design requirements coincide).

## 8. Speak Time as an Accessibility Feature (owning it honestly)

For blind and low-vision users, Speak Time is a primary feature, not a
novelty; its settings (voice, rate via system TTS; interval; quiet hours)
must be fully screen-reader operable, and the iOS tier's limitations must
be stated plainly in its settings copy (degraded honesty is still honesty,
D9). The accessibility statement (About screen) may factually note the
product's design is informed by executive-function and accessibility
research — without clinical claims
(`../research/ExecutiveFunctionADHD.md` §4).

## 9. Cognitive Accessibility

Wake's audience disproportionately includes people navigating ADHD,
executive dysfunction, anxiety, perfectionism, burnout, overwhelm, and
decision fatigue (`../research/ExecutiveFunctionADHD.md`;
`../product/Personas.md`). Cognitive accessibility is therefore a primary
design surface — not an add-on. The curb-cut rule applies: reducing
cognitive load helps everyone.

### 9.1 Populations & failure modes we design against

| Condition / state | Typical failure mode with tools | Wake response |
|---|---|---|
| ADHD / time blindness | Time vanishes; intentions evaporate | Externalized time (widget, Speak Time); one visible intention |
| Executive dysfunction | Cannot initiate despite knowing | MicroStart: ask < resistance; zero decisions on the path |
| Perfectionism | Start blocked by imagined quality bar | "Starting badly is allowed" (T4); 120 s is complete success |
| Anxiety | Awareness → dread | Opportunity framing default; Recovering temperature; easy exits |
| Burnout / overwhelm | Any ask feels like one more demand | Calm defaults; rest permission; pulses off until invited |
| Decision fatigue | Every choice depletes | ≤5 onboarding decisions; ≤12 settings; one Start affordance |

### 9.2 Interaction principles (cognitive)

- **One act, one meaning** (D2/D3): never stack decisions onto a MicroStart.
- **Recognition over recall:** intention prefilled; voice remembered; no
  re-entry of setup.
- **Forgiving paths:** stop needs no confirmation; wrong voice is 2 taps
  to fix; absence leaves no debt (P3).
- **No time pressure in the UI:** the two minutes are work time, not a
  race against a dialog.
- **Predictable structure:** same Now layout every open (D6) — cognitive
  energy is not spent re-learning the screen after a lapse.

### 9.3 Navigation principles (cognitive)

- Depth ≤ 2; six screens total; no hidden gestures required
  (`Navigation.md`).
- Timer and Completion are modal moments — no way to wander mid-start.
- Settings are flat and state-first (D10); no nested option trees.

### 9.4 Notification principles (cognitive)

- User-scheduled only; zero unsolicited (P5) — unexpected interrupts are
  cognitive tax.
- One idea per pulse; one primary action (Start); quiet-today always
  present.
- Respectful-silence reduces volume when ignored — noise is load.
- Pulses suppressed during a running MicroStart (D5) — do not interrupt
  the hard-won initiation.

### 9.5 Copy principles (cognitive)

- Grade ≤ 6; one idea per line; concrete verbs (`Microcopy.md`).
- No controlling language; no identity labels ("procrastinator").
- Edge copy: next-step-first, no blame (S8).
- Emotional Temperature Recovering on return — cognitive safety after
  lapse (`EmotionalJourney.md`).

### 9.6 Visual principles (cognitive)

- Shape over dense numerals (D4); caption is secondary.
- Calm baseline; no alarm geometry; no badge counts (badges = open loops
  in working memory).
- Reduced motion honored; one breathing element max.
- Rest face endorses stopping — visual permission to not produce (A5/A6).

### 9.7 How Wake minimizes cognitive load (summary)

Externalize time · shrink the ask · delete decisions on the critical path ·
delete history that would demand processing · delete engagement that would
compete with the task · speak in one idea · let intensity be invited ·
treat return as a clean page. Every principle above is already a
constitutional or UX rule; this section names them as cognitive-
accessibility requirements so they remain release-blocking under P10.

## 10. Testing Protocol

- Per release: screen-reader pass on all six screens + widget + all
  notification types, both platforms; contrast audit on both palettes ×
  both modes; font-scale max audit; reduced-motion audit; switch-access
  core-loop run.
- Cognitive pass: decision-count audit on onboarding/settings; empty-state
  review against `EmptyStates.md`; return-from-gap walkthrough (Relief
  test).
- Beta cohort explicitly recruits assistive-technology users and
  ADHD-adjacent testers (S3 overlap;
  `../product/UserResearchHypothesis.md` Wave 4).
- Accessibility defects are release-blocking at the same severity as data
  loss (constitutional standing, P10).

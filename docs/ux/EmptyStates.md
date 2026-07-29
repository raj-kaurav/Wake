# Empty States

**Phase:** 2 — UX Documentation (added per Phase 2 review resolution)
**Status:** Draft for review
**Purpose:** UX strategy for every empty, incomplete, denied, or return
state. Empty states are emotional design moments (often the user's worst
hour) — they follow D12, P3, P4, and the Relief-before-Confidence rule
(`EmotionalJourney.md`). Cross-refs: `Microcopy.md` S8, `UserFlows.md` F6/F8/F9.

**Convention per state:** user emotion · design goal · copy tone · CTA ·
anti-patterns.

---

## First launch / pre-onboarding complete

- **Emotion:** curiosity, thin hope, skepticism.
- **Goal:** land inside the loop with zero failure possible.
- **Tone:** voice-neutral until voice chosen; then in-voice; Calm.
- **CTA:** continue onboarding → then Start · 2 min on Now.
- **Anti-patterns:** feature carousels; account walls; permission walls;
  empty dashboards asking for setup.

## No widget configured

- **Emotion:** mild incompleteness or indifference.
- **Goal:** invite once; never nag; core loop works without widget.
- **Tone:** Calm / Focused; one-line value ("Feel the day on your home
  screen.").
- **CTA:** Add widget (platform flow) · Dismiss forever.
- **Anti-patterns:** persistent banners; blocking Now; implying the app
  is broken without a widget.

## Permissions denied (notifications)

- **Emotion:** wariness or "I meant to."
- **Goal:** honesty + one path to fix; app remains whole.
- **Tone:** Grounded; next-step-first (S8).
- **CTA:** Open system settings · Not now.
- **Anti-patterns:** re-prompt loops; guilt ("Wake works better with…");
  disabling Start.

## Notifications disabled (user turned pulses off)

- **Emotion:** intentional quiet or forgotten setting.
- **Goal:** reflect state accurately; easy re-enable; no upsell.
- **Tone:** Calm; state-first ("Pulses: off").
- **CTA:** Turn on pulses (Settings).
- **Anti-patterns:** "You're missing out"; automatic re-enable.

## Speak Time unavailable / denied / unsupported

- **Emotion:** confusion or platform frustration.
- **Goal:** honest tiering; widget still carries time.
- **Tone:** Grounded; platform-honest (D9).
- **CTA:** Fix permission / See limits / Use widget instead.
- **Anti-patterns:** promising parity; hiding the limitation; blaming the
  user or the OEM in hostile language.

## Returned after one day

- **Emotion:** neutral continuity (not a lapse).
- **Goal:** identical to any normal day (D6).
- **Tone:** slot-normal (S1–S3); not Recovering unless other signals.
- **CTA:** Start · 2 min.
- **Anti-patterns:** "Welcome back"; any gap acknowledgment.

## Returned after one week (gap threshold — Relief)

- **Emotion:** bracing for accusation → needs **Relief**.
- **Goal:** "I'm still welcome." Identical layout; S6 content only.
- **Tone:** Recovering; T7/T4; banned words: again/still/back/missed
  (`EmotionalJourney.md`).
- **CTA:** Start · 2 min (unchanged) · rest permission available.
- **Anti-patterns:** resume banners; changed chrome; recovered counts;
  auto-re-escalated pulses; Celebratory or Urgent temperature.

## Returned after one month

- **Emotion:** stronger pre-emptive guilt; possible distrust.
- **Goal:** same as one-week Relief — amnesty does not expire (P3).
- **Tone:** Recovering; if pulses fully paused by respectful-silence,
  Settings shows paused state without drama.
- **CTA:** Start · 2 min · optionally resume pulses (user-initiated only).
- **Anti-patterns:** "It's been a while"; win-back campaigns; onboarding
  replay forced as punishment.

## Completed first MicroStart

- **Emotion:** tentative lift; testing whether the win is real.
- **Goal:** bank Reflection; credit the user; yield fast.
- **Tone:** Celebratory (proportionate) / Calm; T6.
- **CTA:** Done (default) · Again.
- **Anti-patterns:** share sheets; streak unlock; "go longer" upsell;
  tutorial interruption.

## Completed today's awareness (rest face / day complete)

- **Emotion:** closure; possibly fatigue.
- **Goal:** endorse rest; no last-chance panic (A5/A6).
- **Tone:** Reflective / Calm; "Day complete."
- **CTA:** none pushed; Now still openable; Start de-emphasized.
- **Anti-patterns:** "One more before bed"; depletion catastrophe;
  scoring the day.

## Offline / no internet

- **Emotion:** none required — core loop is local-first (P11).
- **Goal:** zero degradation of MicroStart, widget, content, Speak Time
  (on-device).
- **Tone:** only if a cloud-optional surface exists later; MVP: no empty
  state needed.
- **CTA:** n/a for core loop.
- **Anti-patterns:** full-screen "you're offline" blocking Start;
  implying connectivity is required.

## No content available (corpus miss / empty filter)

- **Emotion:** slight glitch unease.
- **Goal:** never show a blank motivational hole; fall back silently.
- **Tone:** omit the content line rather than show an error; or one
  Grounded generic ("Two minutes.") from a hard-coded fallback set.
- **CTA:** Start still primary.
- **Anti-patterns:** "Error loading quote"; empty quotation marks;
  blocking Start on content failure.

## Unsupported device capability (e.g., no TTS, no exact alarms)

- **Emotion:** frustration if they wanted Speak Time.
- **Goal:** degrade gracefully; explain once in Settings; never block
  the loop.
- **Tone:** Grounded; capability-honest.
- **CTA:** Continue with widget / pulses · Learn more.
- **Anti-patterns:** install-blocking capability checks; shaming old
  devices.

---

## Cross-cutting rules

1. Empty ≠ broken: every state above still offers a path to a MicroStart
   or an honest rest, except where Start is intentionally de-emphasized
   (rest face).
2. Return states after ≥ gap threshold share one emotional contract:
   Relief before Confidence.
3. No empty state may introduce a new notification type to "fix" itself
   (P5).
4. Copy for all states is authored in both voices where the user already
   has a voice; otherwise voice-neutral Calm.

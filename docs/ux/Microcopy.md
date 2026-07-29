# Microcopy

**Phase:** 2 — UX Documentation
**Status:** Draft for review
**Purpose:** The style guide for every word Wake displays or speaks:
shared invariants, the two voice contracts, surface budgets, terminology
law, edge-state copy, and the review workflow. Research basis:
`../research/MicrocopyStrategy.md`. Content data model:
`ContentSystem.md`. Behavioral content lives in the corpus; this document
also governs *interface* copy (buttons, settings, errors).

---

## 1. Shared Invariants (both voices, all surfaces — hard rules)

1. Second person, present tense, active voice. The app has no "I" and no
   name-dropping of itself in behavioral moments.
2. One idea per line. Reading level ≤ grade 6 for functional copy.
3. Concrete over abstract: name the smallest action, the exact number.
   Digits for numbers ("2 minutes", "120 seconds"), granular units.
4. No "should," "must," "need to," "don't forget" (controlling language);
   invitations and statements only.
5. Behavior and moment only — never identity, never the past ledger.
   Banned words in behavioral copy: "still," "again," "already," "just
   [time] left" as reproach, "procrastination," "lazy," "fail."
6. Positive action framing: name what to do, never what to avoid
   (ironic-process rule).
7. Honest: no inflated praise, no fake stakes, no pseudo-statistics.
8. Every awareness line pairs with an action or explicitly grants rest.
9. No emoji. No exclamation marks in Coach; max one per screen in Friend,
   rare.
10. Localizable: no idioms that die in translation (though launch is
    en-only).

## 2. Voice Contract — The Coach (challenging; provisional name)

- **Is:** kinetic, clipped, dry, concrete. Fragments allowed. Wry
  understatement is the signature spice ("The file hasn't opened
  itself.").
- **Sounds like:** a great trainer who respects you and wastes nothing.
- **Never:** commands ("Do it now"), contempt, sarcasm at the user,
  drill-sergeant theatrics, profanity, grind-culture vocabulary
  ("crush," "grind," "no excuses").
- **Failure drills (authoring examples):**
  - ✅ "14:00. Two minutes. Yours if you want them."
  - ❌ "It's 14:00 and you still haven't started." (ledger word, reproach)
  - ✅ "Didn't happen earlier. The next window is now."
  - ❌ "Stop wasting your day." (command + identity-adjacent)

## 3. Voice Contract — The Friend (nurturing; provisional name)

- **Is:** warm, plain, permission-giving, quietly confident. Softens time,
  never softens truth.
- **Sounds like:** a good friend who wants you to get up and knows you
  can.
- **Never:** saccharine repetition, therapy-speak ("hold space,"
  "journey"), infantilizing ("little wins, buddy!"), toothless comfort
  that excuses indefinitely (gentle ≠ never start).
- **Failure drills:**
  - ✅ "Starting badly is allowed. Two minutes is enough."
  - ❌ "Aww, no worries at all, whenever you feel ready! 💛" (toothless,
    emoji, saccharine)
  - ✅ "Rough day? One small thing, then rest."
  - ❌ "You deserve rest, forget it today." (decides for the user; T4 rest
    permission must leave the door open)

## 4. Terminology Law (glossary — one word per concept, everywhere)

| Concept | Term | Banned alternatives |
|---|---|---|
| The 2-minute act | **start** | session, sprint, focus block, pomodoro |
| Scheduled awareness notification | **pulse** | reminder, alert, nudge (in UI copy) |
| Spoken clock feature | **Speak Time** | voice assistant, announcements |
| The one stored string | **intention** | task, todo, goal |
| Voice choice | **voice** | mode, personality, theme |
| Wake window | **your day** (UI) / wake window (docs) | active hours, schedule |
| Stopping a timer early | **stop** | give up, quit, cancel (post-20 s) |
| The mortality pack (future) | **The Stoic** | death clock, memento mori (user-facing) |

The words "productivity," "procrastination," "habit," "streak," and
"performance" do not appear in user-facing copy at all (positioning +
identity-labeling rules).

## 5. Surface Budgets

| Surface | Budget |
|---|---|
| Widget content line | ≤ 40 chars |
| Widget caption | ≤ 24 chars |
| Notification primary | ≤ 40 chars |
| Notification secondary (if any) | ≤ 60 chars, usually none |
| Onboarding screen | ≤ 2 short lines + samples |
| Start screen line | ≤ 60 chars |
| Completion line | ≤ 50 chars |
| Settings item label + description | label ≤ 24, description ≤ 70 chars |
| Buttons | 1–3 words, verb-first ("Start", "Quiet today", "Switch voice") |

## 6. Edge & Error Copy (S8 register — where tone systems usually die, D8)

Edge copy stays in-voice but drops all playfulness at genuine failures:
calm, factual, next-step-first. Canonical set (authored both voices;
Coach examples shown):

- **Notification permission denied:** "Pulses need permission. Grant it in
  Settings when you want them." (no pleading; deep link)
- **Exact-alarm restricted (Android):** "Your phone limits exact timing.
  Speak Time may drift a few minutes." (honest, no blame)
- **TTS unavailable:** "This device can't speak the time right now. The
  widget still shows it."
- **OEM battery restriction detected:** "Your phone is pausing Wake in the
  background. To fix it: [device-specific step]."
- **Timer lost to system kill (rare):** "Your start counted. The timer
  couldn't follow — the work did." (bank the win; never make the user pay
  for our failure)
- **Widget stale:** "Tap to wake the widget."

Rules: never blame the user; never dramatize; always one concrete next
step; the failure of a *feature* never implies the failure of the
*person's day*.

## 7. Speak Time Utterance Spec

The spoken line is deliberately voice-neutral and minimal: "It's 12:30." —
no motivational suffix, no name, no variation beyond natural clock
phrasing (locale-appropriate). Rationale: the restraint *is* the feature
(brief's original insight, upheld); voice character belongs to text
surfaces. Configurable TTS voice/rate ride on system settings.

## 8. Settings & Interface Copy Principles

Settings speak human, current-state-first ("Pulses: 3 a day, 9:00–21:00"),
five-second decidable (D10). Toggles state what happens, not what the
feature is called ("Say the time out loud every hour"). The privacy screen
is written at the same reading level as everything else — plain-language
disclosure is a P11 requirement, not legal boilerplate.

## 9. Review Workflow

Every user-facing string (corpus *and* interface copy): drafted against
this guide → ethics checklist (`../research/EthicalConsiderations.md` §5)
→ voice review (drift drills §2–3) → read-aloud/screen-reader pass →
versioned release (`ContentSystem.md` §6). Interface copy changes ride the
same review as corpus lines — there is no "just a label" exemption (labels
are where "should" sneaks in).

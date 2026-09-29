# Information Architecture

**Phase:** 2 — UX Documentation
**Status:** Draft for review
**Purpose:** The complete inventory of surfaces, screens, objects, and
states. Wake's IA is defined as much by what is absent as by what exists:
there is no list, no history, no feed, no profile (P1, P3, P7).

---

## 1. Surface Inventory (outermost first — D1)

| Surface | Role | Contents |
|---|---|---|
| **Home-screen widget** | Primary awareness surface | Day shape + granular time text + content line (footer) + Start affordance |
| **Notifications** | Scheduled awareness pulses; timer completion; (iOS) Speak Time carrier | One content line + Start action + quiet-today action |
| **Spoken time (Android)** | Auditory awareness | "It's 12:30." — nothing else |
| **The app** | Timer runtime + configuration | 6 screens, listed below |

## 2. Screen Inventory (complete — the whole app)

1. **Now** (home) — the day's shape (mirrors widget, larger), granular
   time text, the Start button, current intention (if set). This is the
   only "landing" screen; it doubles as the lapse re-entry surface (its
   S6 content state).
2. **Timer** (running state) — remaining time rendered quietly, current
   intention (if set), stop control. Full-screen, minimal, silent (D5).
3. **Completion** — the honest close: T6 line, credit to user, quiet
   options (done / again). Auto-dismisses to Now.
4. **Settings** — one flat screen (see §4 budget).
5. **Onboarding** — one-time sequence, ≤5 decisions
   (`Onboarding.md`).
6. **About/Privacy** — plain-language data disclosure (P11), licenses,
   the not-a-medical-product note. Static.

No other screens exist in MVP. Screen number seven requires a
constitutional argument.

## 3. Object Model (everything the product knows)

| Object | Cardinality | Lifecycle | Notes |
|---|---|---|---|
| **Voice choice** | exactly 1 | set at onboarding; switchable anytime | coach \| friend |
| **Wake window** | exactly 1 | set at onboarding; editable | start/end time of the user's day |
| **Intention** | 0 or 1 | replaced, never archived (P7) | one short string; local only, never transmitted |
| **Pulse schedule** | 0 or 1 | user-scheduled; auto-downgrades per respectful-silence rule | cadence within wake window |
| **Speak Time config** | 0 or 1 | opt-in; interval + quiet hours + output routing | Android full / iOS tiered |
| **Timer session** | 0 or 1 active | ephemeral; not persisted as history | aggregate counters only, per analytics contract, never displayed |
| **Content package** | 1 installed | versioned, shipped with app | `ContentSystem.md` |
| **Serving log** | 1, on-device, capped | rolling | recency suppression only |

**Deliberately absent objects:** task, list, project, streak, score,
session history, account, profile, social edge. Their absence is
load-bearing architecture, guarded by `../product/OutOfScope.md`.

## 4. Settings IA (budgeted)

One flat screen, grouped; each item passes the five-second test (D10):

- **Voice** — current voice, tap to switch (with 1-line preview each).
- **Your day** — wake window (two time fields).
- **Time pulses** — on/off, cadence, quiet-today shortcut.
- **Speak Time** — on/off, interval (15/30/60), quiet hours,
  headphones-only (Android), honest battery note (P8).
- **Intention** — show/hide the intention field on start.
- **Privacy** — analytics opt-out (feature-loss-free), link to About.

Budget: ≤ 12 tappable settings total in MVP. Additions require removal or
constitutional argument. **Safety controls (voice switch, quiet, disable
any channel) are always ≤ 2 taps from Now and never paywalled (P9).**

## 5. State Model (what changes what a surface shows)

Surfaces vary by exactly three inputs — never by user record (D6):

1. **Clock state:** position in wake window → S1/S2/S3 content slots;
   outside wake window → the widget rests (dimmed "day complete" face, no
   copy urging action; sleep is endorsed).
2. **Event state:** timer running (widget/notification mirror it: remaining
   time + nothing else) · timer completed (S5 moment) · gap-return flag
   (S6, set when last interaction ≥ threshold; consumed by first view;
   leaves no trace).
3. **Config state:** voice, framing arm, intention presence.

Illegal state inputs (enumerated so they cannot creep in): start counts,
day-miss counts, absence duration displayed anywhere, comparative anything.

## 6. Deep-Link Map

| Entry | Target | Contract |
|---|---|---|
| Widget: Start affordance | Timer, starting immediately | Cold start < 1 s budget; no interstitial |
| Widget: shape area | Now | Never opens settings/upsells |
| Pulse notification: Start action | Timer, starting immediately | Same |
| Pulse notification: body tap | Now | Same |
| Completion notification | Completion | — |
| Speak Time | none (auditory only) | The moment is the message; the widget/pulse is the visual affordance nearby |

## 7. IA Anti-Patterns Watchlist

Drift that reviews must catch: a second landing screen ("insights",
"today's summary") · settings sub-pages · a badge anywhere · an archive of
intentions · onboarding steps added "just one more" (P6 cap) · any surface
whose content depends on user performance history (D6 violation).

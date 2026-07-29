# Feature Idea Assessment

**Phase:** 0 — Discovery & Research
**Status:** Draft for review
**Purpose:** Evaluate the six proposed feature ideas against the evidence base
(`ProcrastinationScience.md`, `EvidenceBasedInterventions.md`), the market
review (`CompetitiveLandscape.md`), and practical constraints. Each feature is
assessed on: behavioral impact, strengths, weaknesses, implementation
complexity, accessibility, ethics, battery, privacy — ending with a priority
recommendation. Final scope decisions belong to Phase 1 (`MVPDefinition.md`);
this document supplies the evidence and the recommendation.

**Summary of recommendations**

| # | Feature | Recommendation |
|---|---------|----------------|
| 1 | Motivation Mode | **MVP — with a mandatory reframe** ("Brutally Honest" → "Direct", plus content guardrails) |
| 2 | Time Awareness Widget | **MVP — the product's identity**, with platform-driven design constraints |
| 3 | Speak Time | **MVP-candidate on Android; constrained variant on iOS.** Feasibility spike required before commitment |
| 4 | Quote Engine | **Demote: not a feature, a content system** serving features 1–3. Generic quotes rejected |
| 5 | Start Now | **MVP — the behavioral core.** Highest evidence strength of all six |
| 6 | Future ideas | **Research-only confirmed.** Two flagged as promising, two flagged as dangerous |

---

## 1. Motivation Mode (Brutally Honest / Gentle & Nurturing)

### Behavioral analysis

Letting users choose the app's emotional register is genuinely novel at this
scale (Gap 3) and respects a real psychological difference: some users
experience directness as respect and gentleness as condescension; others the
reverse. Perceived-autonomy research (self-determination theory) also says a
*chosen* voice will be better tolerated than an imposed one.

However, the proposed "Brutally Honest" framing collides with the strongest
finding in the field: **shame and self-criticism increase procrastination**
(Wohl et al., 2010; Sirois & Pychyl, 2013; see `ProcrastinationScience.md`
§2.2). A literal brutal mode would harm the chronic procrastinators most
likely to choose it — people often select self-punishment precisely when
stuck in the guilt spiral.

### The reframe we recommend

Keep the two-mode architecture. Rename and redefine the poles:

- **Direct** (not "Brutal"): concise, concrete, zero praise-padding,
  challenge-oriented. Targets the *behavior and the moment*, never the
  person. "It's 14:00. The report hasn't started itself. 120 seconds — go."
- **Gentle**: warm, permission-giving, self-compassion-informed. "It's 14:00.
  Starting badly is allowed. Two minutes is enough."

**Hard content rules for Direct mode** (full rationale in
`EthicalConsiderations.md` §3): no identity attacks ("you're lazy"), no
catastrophizing, no comparisons to others, no accumulated-failure references,
no profanity-as-edge. Directness is a *style*; contempt is a *harm*.

### Assessment grid

- **Strengths:** True differentiator; doubles perceived personalization for
  the cost of a copy system; marketing hook ("the app that talks to you the
  way you want to be talked to").
- **Weaknesses:** Doubles all content authoring/review/localization cost;
  risk of caricature in Direct mode; mode choice at onboarding is made in a
  motivated state that may not match later low states.
- **Implementation complexity: Low–Medium.** A tone dimension on every string
  + themed palette. Must be architected from day one (string catalog keyed by
  tone) — retrofitting would be expensive. No backend needed.
- **Accessibility:** Tone must not be carried by color alone; Direct-mode
  palette must still meet contrast standards; screen-reader users receive
  tone via copy, which works naturally.
- **Ethics:** Highest ethical surface of the MVP set; see dedicated doc.
  Mitigations: mode preview before choice, one-tap switch at any time
  (never buried), possible soft check-in if signals suggest distress.
- **Battery/Privacy impact:** None / none (tone preference stored locally).
- **Priority: MVP**, conditional on the reframe. If the product owner insists
  on literal brutality, our recommendation is to ship Gentle-only first —
  the evidence risk is that serious.

---

## 2. Time Awareness Widget

### Behavioral analysis

The identity feature (Gap 2). Mechanism: make the day's passage perceptible
at every home-screen glance — attacking TMT's delay-discounting denominator
with ambient, zero-effort exposure. Evidence for the exact mechanic is
*emerging* rather than proven (`EvidenceBasedInterventions.md` §2.2) — we
should instrument it and generate our own evidence.

Users glance at their phone dozens of times daily; each glance is a free
delivery of "time is moving." No notification fatigue, no permission needed.

### UX directions to explore in Phase 2 (per brief, needs UX exploration)

1. **Day-depletion bar/disk** (Time Timer heritage): today as a shape that
   visibly empties. Strong "felt" quality.
2. **Waking-hours remaining, granular:** "6h 40m of today left" — leverages
   the Lewis & Oyserman granularity effect; needs a wake/sleep window
   setting (one onboarding question).
3. **Dot-grid day** (a dot per 15 min, filling as it passes): quiet, abstract,
   screenshot-friendly.
4. **Minimal "now" clock with progress ring** — a hybrid; the ring gives
   feeling, the clock gives coordinates.
5. **Framing variants:** depletion ("gone") vs. opportunity ("still left").
   Framing research suggests testing both against mode (Direct/Gentle may
   want different defaults). Anxiety risk of pure-depletion framing is real.

### Hard platform constraints (must shape design, discovered now, detailed in Phase 3)

- **iOS WidgetKit is budgeted:** roughly 40–70 timeline refreshes per day.
  A minute-accurate progress bar is impossible as a naive widget. Mitigations
  exist — `Text(.timer)`/date-relative text renders continuously without
  refreshes, and timeline entries can be pre-generated at coarser visual
  granularity (e.g., a step every 10–15 min) — but the visual design must be
  chosen *with* this constraint, not against it.
- **Android** offers `AppWidgetProvider`/Glance with more flexible updates
  (typically ≥15-min periodic updates without special measures, finer with
  `AlarmManager` at battery cost). A per-minute Android widget is feasible
  but should still favor coarse steps for battery citizenship.
- **Lock screen / always-on surfaces** (iOS lock widgets, Android AOD
  complications) are high-value placements for this exact content — note for
  Phase 2/3.

### Assessment grid

- **Strengths:** Identity-defining; zero-friction delivery; widget-first
  distribution is proven by the quote apps; no permissions.
- **Weaknesses:** Mechanic not yet directly evidence-validated; refresh
  limits constrain fidelity on iOS; risk of becoming wallpaper (habituation) —
  periodic visual variation may be needed.
- **Complexity: Medium.** Two platform widget stacks + shared rendering
  logic; the cross-platform framework decision (Phase 3) is materially
  affected since widgets are largely native code even under Flutter/RN.
- **Accessibility:** Widget content must have text alternatives (the visual
  bar duplicated by an accessible label like "68% of your day remaining");
  color-independent encoding; respects system font scaling.
- **Ethics:** Low risk; monitor anxiety-inducing framing (test in research).
- **Battery:** Low if designed to budgets above; this is the reason coarse
  granularity is a *feature*.
- **Privacy:** None beyond an optional local wake/sleep window.
- **Priority: MVP.**

---

## 3. Speak Time

### Behavioral analysis

Auditory externalization of time (Gap 5): at chosen intervals the phone says
"It's 12:30." No lecture — the restraint is the design. Mechanism: interrupts
absorption (the state where time vanishes, §3.1 of the science doc) through a
different sensory channel that doesn't require looking at the phone — thereby
*not* offering a scroll opportunity, a subtle but important advantage over
visual notifications.

Clinical ADHD practice endorses auditory time cues; direct trial evidence for
spoken time vs. procrastination is absent — another instrumentation
opportunity.

### Platform feasibility (the brief asked; preliminary findings, Phase 3 must verify with spikes)

**Android — feasible.**

- Reliable paths: `AlarmManager.setExactAndAllowWhileIdle` or a foreground
  service + on-device `TextToSpeech`. Exact alarms now require the
  `SCHEDULE_EXACT_ALARM`/`USE_EXACT_ALARM` permission (Android 12+/14
  policy tightening) with Play Store justification — an accessibility/time
  -awareness rationale is plausible but must be argued in the listing.
- Foreground service requires a persistent notification; Doze/OEM battery
  killers (Samsung, Xiaomi) are the classic reliability trap.
- Battery: on-device TTS every 30–60 min is cheap; every 15 min with exact
  wakeups is measurable but acceptable. Audio-focus etiquette (ducking music,
  honoring DND, silent-mode behavior, headphones-only option) is where the
  real design work lives.

**iOS — the hard case.**

- Arbitrary background TTS on a schedule is **not supported**: no exact-alarm
  API, `BGTaskScheduler` timing is discretionary, background audio mode for
  this purpose would violate App Review intent.
- Honest options: (a) **scheduled local notifications with pre-rendered
  spoken-time audio as the notification sound** — closest approximation;
  constraints: ≤30 s sounds, 64 pending notifications (fine: even 15-min
  intervals over a waking day ≈ 64), sound plays only per user's
  notification/focus settings, and pre-rendering "It's HH:MM" clips for each
  interval boundary is required (or 96+ bundled clips for 15-min granularity —
  entirely doable offline). (b) Reliable speech only while app is foreground
  or during an active Start Now session. (c) Point users to iOS's built-in
  hourly Taptic/spoken time features where applicable (watch).
- **Recommendation:** design Speak Time as *tiered*: full experience on
  Android, notification-sound approximation on iOS, and honest in-app copy
  about the difference. Do not promise identical behavior.

### Assessment grid

- **Strengths:** Unique, memorable, accessibility-rooted (benefits blind and
  low-vision users outright); screen-free awareness; strong PR/story value.
- **Weaknesses:** iOS ceiling; social awkwardness (phone talking in public —
  needs granular quiet hours, headphone-only mode, instant mute); annoyance/
  habituation risk; OEM reliability variance on Android.
- **Complexity: Medium–High** (highest of the MVP candidates), driven by
  background-execution edge cases, not by TTS itself.
- **Accessibility:** Net positive — it *is* an accessibility feature; ensure
  configurable voice/rate and coexistence with screen readers (never speak
  over VoiceOver/TalkBack output).
- **Ethics:** Consent is inherent (opt-in + interval choice); ensure it never
  becomes inescapable nagging — one-tap pause for today.
- **Battery:** The main technical cost; must ship with battery-impact honesty
  in settings copy.
- **Privacy:** On-device TTS only; zero data leaves the phone. (A cloud-voice
  option would break this and is rejected.)
- **Priority: MVP-candidate.** Commit only after a 1–2 day feasibility spike
  per platform in Phase 3. If iOS approximation feels too degraded, ship
  Android-first for this feature while keeping iOS at notification parity.

---

## 4. Quote Engine

### Behavioral analysis

As specified (motivational quotes in Brutal/Gentle variants, shown in
widgets/home/notifications), this is the weakest idea of the six: generic
motivational quotes have near-zero durable behavioral effect, habituate in
days, and position us in the quote-app junk drawer
(`WhyProductivityAppsFail.md` F7; `CompetitiveLandscape.md` §E).

### The reframe we recommend

**Demote from "feature" to "content system."** There is no Quote Engine
surface of its own; there is a **tone-aware content library** that supplies
*functional* lines to the surfaces we already have (widget footer,
notifications, Start Now screen, lapse-recovery moments). Content types, in
priority order:

1. **Reframes** (CBT-derived, one sentence): "You don't need to feel ready.
   Ready comes after."
2. **Granular time facts** (Lewis & Oyserman mechanism): "This week is 40%
   over."
3. **Implementation-intention prompts:** "When this notification sounds,
   open the file. That's the whole job."
4. **Starting permissions** (self-compassion-derived): "A bad first minute
   still counts."
5. Sparse classical quotes (Seneca on time, etc.) as seasoning — capped at a
   small share of rotation to avoid the quotes-app smell.

Every line is authored twice (Direct/Gentle), tagged by *context slot*
(morning, pre-start, post-lapse, evening) — content architecture to be
specified in Phase 2 (`Microcopy.md`) and Phase 3 (content data model).

### Assessment grid

- **Strengths (post-reframe):** Feeds every surface from one authored,
  reviewable, testable catalog; makes tone-mode real; cheap; fully offline.
- **Weaknesses:** Authoring quality bar is high (bad Direct copy = brand
  damage); localization multiplies cost (tones × languages); needs editorial
  review process with ethical guidelines.
- **Complexity: Low** technically (local structured content + selection rules);
  the cost is editorial.
- **Accessibility:** Plain-language guidelines; screen-reader friendly by
  nature.
- **Ethics:** Direct-mode content rules apply (see §1); review checklist in
  `EthicalConsiderations.md` §5.
- **Battery/Privacy:** None / none (fully local).
- **Priority: MVP as infrastructure**, not as a marketed feature.

---

## 5. Start Now

### Behavioral analysis

The strongest evidence alignment of all six ideas
(`EvidenceBasedInterventions.md` §1): sub-threshold first action + immediate
commitment device + the just-get-started attitude shift, delivered as one
button. It also owns Gap 1, the moment no competitor serves.

The brief asked for behavioral analysis, alternatives, and scientific
validation status:

- **Validation status:** the *components* (implementation intentions, tiny
  first steps, action-precedes-motivation) are Strong-to-Moderate evidence;
  the *specific two-minute packaging* is folk (Allen/Clear). Treat duration
  as a tunable default, and instrument what happens at timer end.
- **The critical design question is the end-of-timer moment.** Three
  outcomes must all be honored: (a) user continues working → timer quietly
  ends, maybe "keep going" with no interruption; (b) user stops → *genuine
  congratulation, no upsell to continue* — if two minutes always becomes a
  bait-and-switch to 25, users learn the button lies and stop pressing it
  (trust is the entire asset); (c) user never started → no failure state
  recorded, gentle re-offer later.
- **What Start Now must NOT become:** a session tracker, a Pomodoro cadence,
  a statistics generator. One press = one start. History, if kept at all, is
  private, minimal, and never displays absence (F2: no visible debt).

### Alternatives considered (per brief)

| Alternative | Verdict |
|---|---|
| "Choose your task first" flow before timer | Rejected for default path — reintroduces decision friction at the worst moment; optional single "current intention" field acceptable |
| Countdown-to-start ("starting in 5,4,3…") | Promising micro-variant (removes the decision to begin the beginning); test in Phase 2 prototypes |
| Body-doubling / live co-working | Out of scope (heavyweight, social); noted in future ideas |
| Escalating commitments (2 → 5 → 15 min ladders) | Contradicts trust principle above if automatic; acceptable only as silent user-initiated repeat |
| Physical-action starts ("stand up now") | Interesting for a subset; keep as content variant, not separate feature |

### Assessment grid

- **Strengths:** Best evidence; simplest possible UI; the pair (Widget →
  Start Now) *is* the product loop; works offline; measurable ("starts per
  user-day" is our north-star candidate metric, and time-to-exit-into-action
  our anti-engagement guardrail metric — see F5).
- **Weaknesses:** Easily undervalued in store screenshots ("it's just a
  button?"); depends on nailing microcopy and the end-of-timer moment;
  habituation risk if the moment never varies.
- **Complexity: Low–Medium.** Foreground timer is trivial; surviving
  backgrounding/lock (notification-based completion, Live Activity on iOS as
  a nice-to-have) is the real work. Widget/notification deep-link into a
  running timer must be instant (<1 s cold-start budget — performance
  budget for Phase 4).
- **Accessibility:** Large tap target; timer must not be color/vision-only —
  haptic and audio completion cues; full screen-reader labeling; no
  time-pressure-only affordances.
- **Ethics:** Low risk; keep congratulation honest (no manufactured streak
  pressure).
- **Battery:** Negligible.
- **Privacy:** Local only; if an intention text field exists, it stays
  on-device.
- **Priority: MVP core. Build the product outward from this button.**

---

## 6. Optional Future Ideas (research-only, per brief)

Rapid triage so Phase 1 can formally park them:

| Idea | Triage | Notes |
|---|---|---|
| Death Clock / Life Progress / Memento Mori | **Dangerous by default** | Terror-management backfire risk (`ProcrastinationScience.md` §3.3); life-expectancy math is pseudo-precision; real self-harm-adjacent risk for vulnerable users. If ever built: opt-in behind reflection-oriented framing (Stoic-style), never in Direct mode, never as default widget. Research-only stands. |
| Live Wallpaper (time-aware) | Promising, Android-first | Natural extension of the widget identity; iOS can't do live wallpapers — parity issue. Post-MVP. |
| Lock-screen widgets | **Promote to Phase 2/3 consideration** | Not really "future" — it is the same widget on a better surface; iOS lock widgets + Android AOD are high-value placements. |
| Screen-time awareness | Decline | F6 territory, OS-owned surface, permission-heavy (usage-access), duplicates Opal/OS features. |
| AI Coach | Decline for foreseeable roadmap | Forces subscription economics + privacy posture change (cloud inference); conversational coaching invites therapy-adjacent claims; contradicts minimalism. Revisit only with on-device models and a clear job description. |
| Calendar awareness | Park | "Your next meeting is in 40 min — enough to start" is a genuinely good granular-time mechanic, but calendar permission + parsing complexity doesn't belong in MVP. Strong v2 candidate. |
| Regret simulation | **Reject** | Deliberate negative-affect induction; the evidence says induced negative mood *increases* procrastination. Fails ethics review at concept stage. |
| Ambient sounds / focus music | Decline | Commodity (endless competitors); scope creep toward "media app"; better served by Spotify et al. |
| Voice reminders (user-recorded) | Park, interesting | Own-voice implementation intentions have plausible mechanism ("message from past-you") and pair with Speak Time infra. Research in v2. |
| Habit insights | Decline as dashboards | Anti-vision (F6, F2). A single private "you start most easily around 9–11 a.m." hint could pass; anything chart-like does not. |

---

## Cross-Feature Verdict

The MVP that Phase 1 should formalize, per this assessment:

> **Widget (feel time) → Start Now (act in 2 minutes) → tone-aware content
> system (chosen voice, incl. lapse recovery) → Speak Time (where the
> platform allows it) — and nothing else.**

Four surfaces, one loop, every element traceable to the intervention stack in
`EvidenceBasedInterventions.md` §5. Everything beyond this is listed for the
Phase 1 `OutOfScope.md`.

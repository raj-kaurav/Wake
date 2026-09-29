# Competitive Landscape Review

**Phase:** 0 — Discovery & Research
**Status:** Draft for review
**Purpose:** App-by-app review of the products named in the brief plus adjacent
categories; extract what each proves about the market, what each fails at, and
what we can learn. Store listings and feature sets change frequently — details
below reflect research-time knowledge and should be spot-checked before any
external claims.

Categories reviewed:

- **A. Focus / distraction blockers:** Forest, One Sec, Opal, Freedom
- **B. Emotional-design companions:** Finch
- **C. Task & schedule managers:** Todoist, TickTick, Structured
- **D. Timers:** Be Focused (Pomodoro)
- **E. Minimalist motivation/quotes:** Motivation, I Am, Stoic
- **F. Adjacent inspirations:** Time Timer, WeCroak, death-clock apps, One Big Thing / single-task apps

---

## A. Focus & Distraction Blockers

### Forest

- **Model:** Plant a virtual tree; it grows while you don't touch your phone;
  leaving the app kills it. Paid app + real-tree planting tie-in.
- **What it proves:** Loss aversion + a cute artifact can sustain focus
  sessions; people will pay up front for a single-mechanic behavioral app;
  emotional framing (a living tree) beats a bare timer.
- **Where it fails our user:** It protects a session the user has already
  managed to start. It does nothing for the wall *before* the session. The
  dead-tree mechanic adds a guilt artifact (failure mode F2). Its unit is
  25–120 minutes of purity — heavy for someone who can't begin at all.
- **Lesson for us:** One mechanic, executed with charm, is a complete
  product. Emotional skin over a timer multiplies perceived value.

### One Sec

- **Model:** Intercepts opening of chosen apps (via iOS Shortcuts automation /
  Android accessibility) and imposes a breathing pause + "do you really want
  to open X?" prompt.
- **What it proves:** A *micro-intervention measured in seconds* can be an
  entire product with published efficacy (PNAS 2023 field study: large drop
  in target-app opens; effect sustained over weeks). Also proves users accept
  quite invasive OS-integration hoops when the value is clear.
- **Where it fails our user:** Pure avoidance-side. Not opening TikTok ≠
  starting the essay. Setup (Shortcuts automations per app) is a real hurdle —
  a live example of the setup tax.
- **Lesson for us:** Our "Start Now" is structurally the mirror image of One
  Sec's pause: they insert friction before distraction; we remove friction
  before action. The published evidence for their mechanic lends indirect
  credibility to ours, and their setup pain warns us about anything that
  requires OS-integration gymnastics.

### Opal

- **Model:** Screen-time app blocker with scheduled sessions, "focus score,"
  gem/reward gamification, subscription.
- **What it proves:** Users pay recurring subscriptions ($60–100/yr) for
  screen-time control; a "score" framing appeals to a quantified-self niche.
- **Where it fails our user:** Stats-forward (failure mode F6), blocking-only
  (F3), and its dashboard is another place to feel bad about yesterday.
- **Lesson for us:** Subscription willingness exists in this space. Scores
  invite gaming and guilt; avoid.

### Freedom

- **Model:** Cross-device (desktop+mobile) website/app blocking sessions,
  subscription, long-established.
- **What it proves:** Durable willingness-to-pay for blunt, reliable blocking;
  cross-device sync matters to professionals.
- **Where it fails our user:** Same avoidance-side limits; utilitarian, no
  emotional design; nothing about starting.
- **Lesson for us:** Reliability is a feature. A behavioral app that misfires
  (missed notifications, dead widgets) loses trust instantly — relevant to
  our platform-constraint work in Phase 3.

## B. Emotional-Design Companions

### Finch

- **Model:** Self-care pet: completing self-set tasks feeds/grows a bird;
  extremely gentle, mental-health-adjacent tone; freemium.
- **What it proves:** *This is the most important comp for us.* Emotional
  design with a compassionate register drives top-tier retention in a
  category (self-care/habit) notorious for churn. A large audience —
  including many self-identified ADHD/anxious users — explicitly chose a tool
  because it is kind to them. Gentleness is a mass market, not a niche.
- **Where it fails our user:** Engagement loop competes with real life (F5):
  caring for the bird is the activity. Task layer is a lightweight todo list,
  so the starting wall remains. Heavy gamification surface (outfits,
  currencies) contradicts "no unnecessary complexity."
- **Lesson for us:** Validates the Gentle mode market and the emotional-design
  thesis. Warns against letting the emotional layer *become the product*.
  Our emotional layer must point outward (at the user's real task), not
  inward (at app content).

## C. Task & Schedule Managers

### Todoist / TickTick

- **Model:** Full task managers (projects, labels, filters, calendars;
  TickTick adds built-in Pomodoro + habit tracker). Freemium, mature,
  enormous user bases.
- **What they prove:** The organized minority is well served and locked in.
  Feature completeness is table stakes there — a war we must not enter.
- **Where they fail our user:** The entire Section 1 loop of
  `WhyProductivityAppsFail.md`: setup tax, overdue-red guilt ledger, zero
  help at the moment of emotional resistance. TickTick's bolted-on Pomodoro
  confirms that timers-inside-task-managers still presume you can start.
- **Lesson for us:** Do not build task storage. The moment we hold a list of
  the user's obligations, we inherit the guilt-ledger problem and compete
  with these incumbents on their turf. **Recommendation to enshrine in Phase
  1 scope: the app stores at most one "current intention," never a list.**

### Structured

- **Model:** Visual timeline day planner ("time boxing for humans"),
  aesthetic-forward, popular with students/ADHD community.
- **What it proves:** Demand for *seeing* the day as a shape — direct evidence
  for our Time Awareness Widget hypothesis. Its popularity in ADHD spaces
  confirms the externalized-time need.
- **Where it fails our user:** Fragile-plan failure mode (F4): one missed
  block visually breaks the day. Planning is still prerequisite to value.
- **Lesson for us:** Render time's passage without renderable *failure*. A
  day-progress visualization has no broken state; a day *plan* does.

## D. Timers

### Be Focused (and the Pomodoro clone field)

- **Model:** Classic Pomodoro timer with task counts; one of hundreds.
- **What it proves:** Commodity category; near-zero differentiation or
  pricing power; App Store is saturated with interval timers.
- **Where it fails our user:** A Pomodoro presumes the start has happened.
  25 minutes is an intimidating unit for a blocked user. No emotional layer.
- **Lesson for us:** If our public positioning ever reads as "a timer app,"
  we have lost. The timer inside Start Now is an implementation detail, not
  the product. This validates the brief's constraint ("not another Pomodoro
  clone") — and pushes us to name/frame the 2-minute mechanic around
  *starting*, not *timing*.

## E. Minimalist Motivation / Quote Apps

### Motivation (Monkey Taps), I Am, Stoic

- **Model:** Daily affirmation/quote pushers with themed packs, widgets,
  aggressive subscription paywalls. Massive download numbers, low regard.
- **What they prove:** Enormous top-of-funnel demand for emotional
  self-regulation content; widgets + notifications are proven delivery
  surfaces; people *want* to be talked to by their phone in a chosen voice.
  Stoic proves a "philosophical register" (memento mori, journaling) has an
  audience.
- **Where they fail our user:** Content is decorative (F7); zero action
  affordance; habituation within days; paywall resentment.
- **Lesson for us:** The demand these apps monetize is real and adjacent to
  ours; the retention they fail to earn is earned via *function*. Their
  widget-first distribution strategy (home-screen real estate as daily
  re-acquisition) is worth copying outright.

## F. Adjacent Inspirations

- **Time Timer (physical + app):** the canonical externalized-time product;
  a red disk that visibly depletes. Decades of adoption in ADHD/education
  settings. Strong prior for our "visual depletion" widget direction.
- **WeCroak:** five daily "you will die" quotes; a cult minimalist product.
  Proves a memento-mori niche exists; its deliberate uselessness beyond the
  reminder also shows the ceiling of awareness-without-action (F6).
- **Death Clock / life-expectancy apps:** mostly novelty; occasional viral
  spikes, poor retention; reinforces treating mortality features as an
  opt-in, off-by-default philosophy pack with hard ethics guardrails
  (`FeatureIdeaAssessment.md` §6) given TMT backfire risks
  (`ProcrastinationScience.md` §3.3).
- **"One thing" single-task apps (various):** small products that show a
  "just one intention" scope is viable and loved by a minimalist audience,
  but none pair it with time-awareness or tone design.

---

## Positioning Map

Two axes that cleanly separate the market:

- **X: Where the intervention acts** — on *avoidance* (blocking distraction)
  ⟷ on *approach* (initiating action).
- **Y: Emotional register** — *mechanical/stat-driven* ⟷ *emotionally
  designed*.

| | Acts on avoidance | Acts on approach |
|---|---|---|
| **Emotionally designed** | Forest, One Sec | **← open quadrant (us)** — only Finch is nearby, and it acts on neither time nor starting |
| **Mechanical / stats** | Opal, Freedom, Screen Time | Todoist, TickTick, Structured, Pomodoro apps |

The **emotionally designed, approach-side, time-centric** quadrant is
effectively empty. That is the opportunity. Full argument and risks in
`MarketGaps.md` and `ProductOpportunityReport.md`.

## Pricing Observations (for later business modeling — not a Phase 0 decision)

- One-time purchase precedent: Forest (~$4).
- Subscription precedents: Opal, Freedom, Motivation, Finch premium
  (~$40–100/yr).
- Quote apps demonstrate paywall-resentment risk; Forest demonstrates
  goodwill from honest one-time pricing.
- Our privacy-first, offline-first posture (Phase 3) is compatible with
  either; note that heavy server-side AI features (Feature 6's "AI Coach")
  would force subscription economics — one more reason they are out of MVP.

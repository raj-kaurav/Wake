# Competitive Analysis

**Phase:** 1 — Product Documentation
**Status:** Draft for review
**Basis:** Full app-by-app review in `../research/CompetitiveLandscape.md`;
failure-mode analysis in `../research/WhyProductivityAppsFail.md`. This
document is the product-strategy synthesis: positioning, defense, and
watchlist.

---

## 1. The Map

Two axes separate the market: where the intervention acts (avoidance side —
blocking distraction — vs. approach side — producing action), and the
emotional register (mechanical/stat-driven vs. emotionally designed).

| | Acts on avoidance | Acts on approach |
|---|---|---|
| **Emotionally designed** | Forest, One Sec | **Wake** (alone; Finch is adjacent but acts on neither time nor starting) |
| **Mechanical / stats** | Opal, Freedom, Screen Time | Todoist, TickTick, Structured, Pomodoro apps |

Wake claims the empty quadrant **and a new category label — time
awareness** — so that we are compared to clocks and calm, not to todo apps
(a comparison we'd win on feeling and lose on feature count, so we refuse
the frame).

## 2. Positioning Statement

> For ambitious people who know what to do and can't begin, **Wake is a
> time awareness app** that makes today feel finite and starting feel
> two minutes small — in a voice you choose. Unlike task managers,
> blockers, and motivation feeds, it keeps no lists, keeps no score, and
> counts it a win when you leave the app.

Anti-positioning (equally binding): never "productivity," never
"anti-procrastination app" as category label, never "timer," never
"quotes," never "habit."

## 3. Competitor-by-Competitor Product Stance

| Competitor | Their strength we respect | Our relationship | What we must never do because of them |
|---|---|---|---|
| **Forest** | One charming mechanic; honest one-time pricing | Complement (they protect sessions; we create them) | Add loss-mechanics (dead-tree guilt is their tax) |
| **One Sec** | Published efficacy; micro-intervention as a product | Mirror-image complement (they add friction to distraction; we remove it from starting) | Require OS-integration gymnastics in onboarding |
| **Opal / Freedom** | Subscription willingness in the space | Complement; possible future "pairs well with" story | Ship scores, dashboards, or blocking |
| **Finch** | Proof that gentleness retains at scale | Nearest emotional-design neighbor; different mechanism | Let the emotional layer become the product (bird-care problem); infantilize the register |
| **Todoist / TickTick** | Own the organized minority | Non-compete by constitution (P7) | Store a second intention — their gravity begins there |
| **Structured** | Proof of demand for seeing the day | We render time without renderable failure | Ship anything that can visibly "break" by 9:30 |
| **Pomodoro clones** | Commodity evidence that timers alone are worthless | Cautionary tale | Let store listing read as "timer app" (R3) |
| **Quote apps (Motivation, I Am, Stoic)** | Widget-first distribution; demand for chosen voice | We take their delivery surfaces and their audience's unmet need, with function instead of decoration | Ship decorative inspiration; aggressive paywalls |
| **WeCroak** | Memento-mori niche exists and tolerates radical minimalism | Prototype-of-spirit for The Stoic pack's restraint | Make mortality a default or a pressure mechanic |

## 4. Defense Analysis (who could copy us, and what actually protects us)

**Could copy the widget in a sprint:** any incumbent. A Todoist "day
progress" widget still sits on top of an overdue ledger; a Forest one still
monetizes guilt-adjacent mechanics. The *combination* — felt time + tiny
start + chosen voice + no debt — requires them to abandon their engagement
economics (their retention is built on the mechanics our constitution
bans). Structural defense, stronger than any feature.

**Could copy everything as a startup:** yes (risk R6). Defenses: speed to a
polished v1; the voice/content corpus (400–800 reviewed lines is real,
slow, taste-dependent work); category authorship (first to define "time
awareness" owns its vocabulary); and a community that adopted us *because*
of the constitution — an audience that punishes defection from it.

**Platform risk as competition:** Apple/Google could ship day-progress
lock-screen faces or richer spoken-time accessibility. Mitigation: they
build features, not stances; our voice system, start loop, and lapse design
don't fit OS settings panels. Monitor WWDC/IO announcements (watchlist).

## 5. Watchlist (standing, revisit each phase gate)

- One Sec expanding from "pause before app" to "start toward task" — the
  single most plausible convergent move.
- Finch or a Finch-like launching a "focus/start" companion mode.
- Structured softening its plan-breakage problem (e.g., planless mode).
- New entrants using "time blindness" / ADHD-first marketing (fast-growing
  keyword space) — watch for category-language collisions with ours.
- OS releases: WidgetKit refresh budgets, Android exact-alarm policy,
  live-activity APIs (both risk and opportunity for the loop's surfaces).

## 6. What We Take From Each (already absorbed into requirements)

Forest → single-mechanic clarity, honest pricing precedent. One Sec →
micro-intervention legitimacy, setup-tax warning. Finch → gentle-register
market proof, engagement-loop warning. Structured → day-as-shape demand,
breakable-plan warning. Quote apps → widget-first distribution, decorative-
content warning. Time Timer/WeCroak → restraint as durable identity.

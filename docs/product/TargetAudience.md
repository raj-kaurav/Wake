# Target Audience

**Phase:** 1 — Product Documentation
**Status:** Draft for review
**Research basis:** `../research/ProcrastinationScience.md` §4–5,
`../research/CompetitiveLandscape.md`, `../research/ExecutiveFunctionADHD.md`

---

## Audience Definition

Wake serves **ambitious self-directed people who know what they should be
doing and struggle to begin** — and who are tired of complicated systems
and of tools that make them feel worse.

Shared characteristics (from the brief, confirmed by research):

- Ambitious and self-aware — they diagnose their own procrastination
  accurately and often consume motivational content about it.
- Overwhelmed, not disorganized — they usually *have* a list; the list is
  the problem's monument, not its solution.
- Consistency-challenged — bursts of motivated tool adoption followed by
  abandonment (this shapes our lapse-recovery and re-entry design).
- Allergic to complexity — prior tools died by setup tax; they will give
  Wake about sixty seconds (P6).
- Emotionally bruised by previous tools — streak guilt, overdue red,
  disappointed mascots. Safety is a feature they can feel.

## Segments, Prioritized

### Tier 1 — Primary launch segments

**S1. Students (university/graduate, exam- and thesis-driven)**
Highest pain frequency and the largest self-identified procrastinator
population (~50% report serious problems). Deadline regimes create
recurring acute need; semester rhythms create fresh-start adoption windows
(`../research/BehavioralEconomics.md` §2). Price-sensitive; viral in
study-community channels (StudyTok, Discord study servers).

**S2. Independent knowledge workers & creators (developers, designers,
writers, freelancers)**
Maximum autonomy → maximum exposure to the starting problem; self-directed
projects (side projects, portfolios, invoicing, content) have no external
deadlines at all. Higher willingness to pay; articulate advocates in
high-signal channels (HN, design Twitter, dev newsletters).

### Tier 2 — High-affinity early adopters

**S3. The ADHD-adjacent community**
Time blindness makes Wake assistive in effect while we remain a
general-audience time awareness product in claims (medical boundary:
`../research/ExecutiveFunctionADHD.md` §4). Likely our most engaged users
and loudest organic channel; their needs set our defaults, not our
marketing language.

**S4. Founders / entrepreneurs**
Motivational-content heavy consumers with strong tool-hopping behavior;
excellent early evangelists; higher tolerance for the challenging voice.
Smaller population; served by the same product, prioritized in beta
recruiting rather than in feature decisions.

### Tier 3 — Served, not targeted

Professionals in structured employment (meetings supply external
scaffolding, so pain is lower but real for career side-goals), and the
general "I want a calmer relationship with time" audience that quote/stoic
apps currently monetize. We accept them gladly; we do not design for them
first.

## Who Wake Is NOT For (honest non-audience)

- People seeking a task manager, calendar, or full planning system — we
  refuse that scope (P7); they should use Todoist/Structured.
- People whose procrastination is a symptom of acute untreated depression —
  we are not a treatment and must not pose as one
  (`../research/EthicalConsiderations.md` §4.3); our design must merely be
  *safe* for them (P4, P9).
- Teams/enterprise — Wake is personal by design; no admin dashboards, no
  manager visibility, ever (would violate P11 and the product's soul).
- Users who genuinely want to be abused into action — we decline that
  demand on evidence and ethics grounds; the challenging voice is a coach,
  not a bully.

## Implications for Design Defaults

| Audience trait | Default it dictates |
|---|---|
| 60-second patience | Core loop before any configuration (P6) |
| Emotionally bruised | Nurturing voice as pre-selected default at the voice choice; calm visual register (P9) |
| Time blindness in a large minority | Shape-based widget, optional spoken time, externalized intention (`ExecutiveFunctionADHD.md` checklist) |
| Motivation-cycle churn | Weightless re-entry; no debt accumulates during absence (P3) |
| Dislike of systems | One intention max; no plans that can break (P7) |

## Market Size Note (order-of-magnitude, not a forecast)

Procrastination self-identification is near-universal; chronic prevalence
15–20% of adults puts the addressable population in the hundreds of
millions globally. Comparable single-mechanic behavioral apps (Forest,
Finch, One Sec) each demonstrated tens of millions of downloads. Precision
here is not decision-relevant for MVP; what matters is that every named
segment is reachable through identifiable organic channels at near-zero
acquisition cost.

# Product Decision Log

**Phase:** Governance (seeded at Phase 2 final approval / Phase 3 start)
**Status:** Living record — append-only for decisions; corrections via
new entries that supersede
**Purpose:** Permanent historical record of major product decisions.
Every Phase 3+ architectural choice of consequence should add an entry.

---

## Entry Template

```
### D-XXX — Title
- **Date:**
- **Context:**
- **Decision:**
- **Alternatives Considered:**
- **Rationale:**
- **Evidence:**
- **Consequences:**
- **Review Trigger:**
```

---

### D-001 — Product category: Time Awareness
- **Date:** 2026-07-29 (Phase 0 review / Phase 1)
- **Context:** Category ambiguity risk (timer / quotes / productivity).
- **Decision:** Position Wake as a **Time Awareness** product; anti-
  procrastination is an outcome, not the category label.
- **Alternatives Considered:** Anti-procrastination app; focus timer;
  motivation app; productivity tool.
- **Rationale:** Empty market quadrant; avoids feature-count wars with
  todo incumbents; matches mechanism (felt time).
- **Evidence:** Phase 0 competitive map; Opportunity Report.
- **Consequences:** Store/copy/IA language constrained; "productivity"
  banned from positioning.
- **Review Trigger:** H10 copy tests fail; press consistently miscategorizes
  after corrective listing language.

### D-002 — Dual-pillar philosophy
- **Date:** 2026-07-29 (Phase 0 revision)
- **Context:** Brief emphasized felt time; science also requires shrinking
  the start (mood-repair model).
- **Decision:** Philosophy = **"Make time felt. Make starting small."**
- **Alternatives Considered:** Single-pillar "make time felt, not tracked"
  only.
- **Rationale:** TMT + mood-repair are complementary; awareness without
  action affordance manufactures anxiety.
- **Evidence:** ProcrastinationScience; EvidenceBasedInterventions.
- **Consequences:** Constitution pillars I–II; every surface pairs Notice
  with MicroStart offer.
- **Review Trigger:** H1 shows awareness never converts; would force
  Start-first identity rethink.

### D-003 — Content Engine (not Quote Engine)
- **Date:** 2026-07-29 (Phase 0 revision)
- **Context:** Generic quotes have near-zero durable effect; quote-app
  positioning risk.
- **Decision:** **Content Engine** — functional types; quotes one capped
  type among several.
- **Alternatives Considered:** Standalone Quote Engine feature; no content.
- **Rationale:** Content as infrastructure for voices/slots/temperatures.
- **Evidence:** WhyProductivityAppsFail F7; FeatureIdeaAssessment §4.
- **Consequences:** Corpus workstream; no browsable content surface (P5).
- **Review Trigger:** Content habituates (R1) despite depth minimums.

### D-004 — MicroStart as canonical internal term
- **Date:** 2026-07-29 (Phase 2 final ratification)
- **Context:** "Start Now" blurred UX copy and architecture.
- **Decision:** Freeze **MicroStart** for engineering, analytics, docs,
  events, services, domain models. User copy stays independent (Start /
  Start Now / Begin / …).
- **Alternatives Considered:** TinyStart, Activation, FirstStep, Start
  Ritual, keep Start Now.
- **Rationale:** Names the size of the ask; avoids urgency/pressure in
  type names; distinct from Pomodoro "session."
- **Evidence:** Terminology.md audit; LanguageSystem.md.
- **Consequences:** `MicroStartService`, `MicroStartCompleted`, etc.;
  Phase 0–1 legacy phrasing not mass-rewritten.
- **Review Trigger:** Persistent external confusion; then revisit display
  only — not the ID.

### D-005 — Ritual framework (internal)
- **Date:** 2026-07-29 (Phase 2 final ratification)
- **Context:** "Feature" language invites feature-farm growth.
- **Decision:** Internally refer to capabilities as **Rituals**; do not
  expose "ritual" externally until validated.
- **Alternatives Considered:** Keep "feature"; expose rituals in MVP UI.
- **Rationale:** Identity forms around repeated acts; rituals resist
  engagement creep.
- **Evidence:** Rituals.md; BehaviorChangeModel reinforcing loop.
- **Consequences:** Phase 3+ docs use ritual names; MVPDefinition
  historical "feature" language remains.
- **Review Trigger:** External validation study approves/rejects ritual
  language in marketing.

### D-006 — Day Dots as Default V1 widget
- **Date:** 2026-07-29 (Phase 2 final ratification)
- **Context:** Need launch-ready widget that is honest on iOS/Android
  refresh budgets.
- **Decision:** **Day Dots = Default V1**; not permanent identity; Widget
  Evolution Program for long-term candidates.
- **Alternatives Considered:** Day Arc, Remaining field, Opportunity
  Tiles, Timeline Blocks, Living Horizon, Remaining Ribbon, Segmented Day.
- **Rationale:** Coarse-native (15 min) = platform honesty; opportunity
  framing in geometry; a11y-friendly fill≠hue.
- **Evidence:** Widgets.md comparison matrix.
- **Consequences:** V1 ships Day Dots; beta explores alternates; no
  visual-parity hacks.
- **Review Trigger:** Beta concept tests; H1 flat with Day Dots but not
  with an alternate mock.

### D-007 — BehaviorArchitecture as authoritative contract
- **Date:** 2026-07-29 (Phase 2 final ratification)
- **Context:** Risk of technical designs decoupling from behavioral
  philosophy.
- **Decision:** `BehaviorArchitecture.md` is the **behavioral API
  contract**. Every Phase 3+ technical proposal must map to Behavior
  Transition, Ritual, Emotional Goal, Success Metric, Anti-Goal, Ethical
  Guardrail.
- **Alternatives Considered:** Informal cross-refs; engineering-first
  architecture.
- **Rationale:** Protect philosophy from technical entropy.
- **Evidence:** Phase 2 review authorization.
- **Consequences:** Proposals without mapping are rejected; Phase 3 docs
  structured around the matrix.
- **Review Trigger:** Matrix row missing for a shipped surface; amend
  matrix first.

### D-008 — Memento Mori → optional philosophy pack (The Stoic)
- **Date:** 2026-07-29 (Phase 0 revision)
- **Context:** Mortality features have terror-management backfire risk;
  review asked not to reject outright.
- **Decision:** **The Stoic** pack — optional, disabled by default,
  post-MVP, ethics-gated. Regret simulation remains rejected.
- **Alternatives Considered:** Full reject; default Death Clock; research-
  only forever.
- **Rationale:** Niche demand (WeCroak) with hard safety constraints.
- **Evidence:** EthicalConsiderations §4.2; FeatureIdeaAssessment §6.
- **Consequences:** No MVP work; Horizon 2 + dedicated ethics review.
- **Review Trigger:** Ethics review outcome; G4 warning signs in base
  product.

### D-009 — North Star = Weekly Started Users (WSU)
- **Date:** 2026-07-29 (Phase 1)
- **Context:** Engagement KPIs would corrupt the product (P5).
- **Decision:** North star = users with ≥1 MicroStart in trailing 7 days;
  session length is a guardrail to keep *low*.
- **Alternatives Considered:** DAU/opens; time-in-app; streak length.
- **Rationale:** Success = action in life; metric must not incentivize
  attention traps.
- **Evidence:** SuccessMetrics.md; WhyProductivityAppsFail F5.
- **Consequences:** Analytics event design; product reviews reject
  engagement-upsell proposals.
- **Review Trigger:** WSU rises while UserSuccessDefinition / H8 worsen
  — then investigate metric gaming.

### D-010 — Voice IDs VoiceA / VoiceB (display labels unfinalized)
- **Date:** 2026-07-29 (Phase 2 final ratification)
- **Context:** Naming exploration ongoing; architecture must not depend
  on display strings.
- **Decision:** Freeze stable IDs **`VoiceA`** (challenging) and
  **`VoiceB`** (nurturing). Display labels temporary (Coach/Friend).
  Final names = Phase 5 branding.
- **Alternatives Considered:** Freeze Coach/Friend as IDs; energy names
  as IDs now.
- **Rationale:** Labels may change; IDs must not; no migration later.
- **Evidence:** ToneNamingExploration rounds 1–3; LanguageSystem.md.
- **Consequences:** Content schema/code use VoiceA/VoiceB; UI strings
  separate.
- **Review Trigger:** Phase 5 name ratification — update display keys
  only.

### D-011 — Emotional Temperature mandatory metadata
- **Date:** 2026-07-29 (Phase 2 final ratification)
- **Context:** Adaptive delivery not in MVP; risk of shipping content
  without fields needed later.
- **Decision:** Every content item must include Emotional Temperature
  (and Voice, Type, Context, Intensity) at authoring time.
- **Alternatives Considered:** Add temperature post-MVP; derive from
  intensity alone.
- **Rationale:** Avoid future migration; enable Recovering lock after
  lapse without new voice.
- **Evidence:** ContentSystem §1.4; EmotionalJourney Relief rules.
- **Consequences:** Corpus schema v1 includes field; selection may ignore
  adaptive rules until later.
- **Review Trigger:** Authoring cost overload — reduce variant depth
  before dropping the field.

### D-012 — Challenging voice contract (not Brutal)
- **Date:** 2026-07-29 (Phase 0)
- **Context:** "Brutally Honest" conflicts with shame→procrastination
  evidence.
- **Decision:** Keep two-voice architecture; challenging voice targets
  behavior/moment never person; Direct≠Brutal content contract.
- **Alternatives Considered:** Literal brutal mode; VoiceB-only launch.
- **Rationale:** Adverse selection + evidence base.
- **Evidence:** EthicalConsiderations §3; Wohl 2010; Sirois & Pychyl 2013.
- **Consequences:** Binding checklist; VoiceA never means contempt.
- **Review Trigger:** Line-level harm signals (R4); H7 failures.

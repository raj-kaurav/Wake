# Ethical Considerations

**Phase:** 0 — Discovery & Research
**Status:** Draft for review
**Purpose:** Identify ethical risks before design begins, per the brief's
requirement ("ensuring 'brutal mode' motivates without becoming manipulative
or harmful"), and define binding guardrails for later phases.

The frame throughout: this product deliberately operates on users' *emotions*
about time and self-worth. That is its value and its hazard. An emotionally
powerful design owes users a higher duty of care than a spreadsheet does.

---

## 1. The Population Is Not Neutral

Who downloads an anti-procrastination app? Disproportionately: people in the
guilt/anxiety phase of the procrastination spiral; students under deadline
distress; people with ADHD, anxiety disorders, or depression (procrastination
is heavily comorbid with all three). Design defaults must be safe for this
population, not for an idealized resilient user. Concretely:

- Assume some users open the app at emotional low points (2 a.m., deadline
  panic, post-failure shame).
- Assume some users will use any self-punishment affordance we provide to
  punish themselves.
- Assume mortality-related content will reach people with depression.

## 2. Manipulation vs. Persuasion — Our Line

We adopt this working standard (informed by the persuasive-technology ethics
literature, e.g., Fogg; and dark-patterns research):

> An influence technique is legitimate if it helps the user do what *they*
> already said they want to do, works with their full awareness, remains
> under their control, and they would endorse it if they fully understood
> how it works.

Applying it:

| Practice | Verdict |
|---|---|
| Time-awareness displays the user opted into | Legitimate — transparent, user-goal-aligned |
| Spoken time at intervals the user chose | Legitimate — same |
| Tiny-start framing ("just 2 minutes") | Legitimate *if honest* — the timer really may end at 2 minutes with genuine congratulation. If it always escalates, it becomes a foot-in-the-door trick and fails the endorsement test |
| Manufactured urgency (fake scarcity, countdown pressure unrelated to real time) | **Prohibited** |
| Guilt-based re-engagement notifications ("You've ignored us for 5 days…") | **Prohibited** |
| Streak-loss threats to drive opens | **Prohibited** |
| Variable-reward slot-machine mechanics | **Prohibited** |
| Emotional escalation to increase session length | **Prohibited and structurally excluded** — our success metric is leaving the app to act (see `WhyProductivityAppsFail.md` F5) |

The deepest protection is the metric choice: a team optimizing
*starts-into-real-work* has little incentive to build attention traps. This
must be locked into Phase 1's `SuccessMetrics.md` and Phase 3's
`Analytics.md`.

## 3. The "Brutally Honest" Mode — Full Analysis

### Why the idea is attractive

- A real audience asks for it ("don't coddle me"); drill-sergeant content
  performs well in motivational media.
- Chosen directness can signal respect and increase message acceptance
  (autonomy effect).
- It differentiates sharply from the saccharine register of wellness apps.

### Why the literal version is hazardous

1. **It contradicts the evidence base.** Self-criticism and shame reliably
   *increase* procrastination (Sirois & Pychyl, 2013; Wohl et al., 2010).
   A brutal mode that works as advertised would make the core problem worse.
2. **Adverse selection:** the users most drawn to self-punishing framing are
   often those already in shame spirals — the mode would concentrate harm on
   the most vulnerable segment.
3. **Parasocial abuse pattern:** an app that insults you daily, chosen or
   not, normalizes an abusive internal monologue. We would be scripting
   users' self-talk. Scripts get internalized.
4. **Brand/latent liability:** screenshots of the app calling a user a loser
   will circulate stripped of the "they opted in" context.

### The resolution: a challenging voice, not a brutal one

Keep the two-register architecture (it is genuinely valuable); redefine the
edgy pole as a **challenging voice** — a good coach or a straight-talking
friend, not a bully. (Label alternatives with UX rationale are explored in
`ToneNamingExploration.md`; provisional recommendation: "The Coach." The
behavioral contract below is binding regardless of the label.)

| Dimension | The challenging voice does | The challenging voice never does |
|---|---|---|
| Target | The behavior, the moment, the next action | The person, their character, their worth |
| Time reference | Present and immediate future ("It's 14:00. Start.") | Accumulated past failures ("Another wasted week") |
| Emotional tool | Challenge, brevity, dry wit | Shame, contempt, catastrophe, comparison to others |
| Failure response | "Didn't happen. Next window's now." | "You always do this." |
| Register | Blunt, concise, zero padding | Insulting, profane-as-edge, sarcastic about the user |

**Enforcement mechanisms to carry into later phases:**

- A written **content style contract** per voice (Phase 2 `Microcopy.md`)
  with the never-list above as hard rules.
- **Editorial review checklist** (see §5) applied to every line in the
  Content Engine — no generative/unreviewed content in v1.
- **Voice preview** during onboarding (hear/see samples before choosing);
  **one-tap voice switch** permanently available, never buried.
- Onboarding choice screen itself stays tone-neutral (no self-labeling like
  "I deserve tough love").

## 4. Other Ethical Risks and Positions

### 4.1 Time-awareness anxiety

For anxious users, ambient "time is running out" signals can shade from
awareness into dread. Positions: offer opportunity-framing variants
("6 hours still yours") not only depletion framing; make every awareness
surface individually disableable; instrument for signs of aversive use
(e.g., rapid widget removal, speak-time disabled within a day) as research
input, not as re-engagement triggers.

### 4.2 Mortality content (the optional philosophy pack)

Per the Phase 0 review decision, Death Clock/Memento Mori concepts are
recast as an **optional philosophy pack ("The Stoic") — disabled by
default**, rather than rejected outright. The ethics conditions are
non-negotiable and travel with the feature: strictly opt-in behind an
explicit consent step; reflective Stoic framing (practice, not countdown
pressure); no pseudo-precise life-expectancy math; excluded from the
challenging voice's sharper register; never a default surface or default
widget face; a dedicated ethics review before ship; and review against
suicide-prevention content guidelines. "Regret simulation" remains rejected —
it failed concept review (`FeatureIdeaAssessment.md` §6) and is not part of
the pack.

### 4.3 Not-a-therapist boundary

The app borrows single techniques from CBT/self-compassion research but is
not a mental-health treatment and must not claim to be (marketing, store
listing, in-app copy). If we ever detect-and-respond to user distress, the
response is signposting to real resources, not in-app counseling.

### 4.4 Privacy as an ethical stance (summary; full doc in Phase 3)

The product needs almost nothing about the user: a tone choice, a wake
window, optional intervals, an optional intention string. Position: **local-
first by default; no account for core features; no behavioral data sold or
shared; analytics minimal, aggregate, and opt-out-able; on-device TTS only.**
For a product whose subject matter is users' failures and anxieties, data
minimalism is not just compliance (GDPR etc.) but the only defensible
posture. Any future cloud feature must re-clear this bar explicitly.

### 4.5 Monetization ethics (flag for later)

Whatever the model (Phase 1+ decision), prohibited at concept stage:
paywalling safety features (voice switching, quiet hours, disabling
awareness), guilt-based upsells, and fake-urgency sales tactics inside an
app about urgency. The irony would be fatal.

### 4.6 Accessibility as ethics

An awareness app whose awareness surfaces are inaccessible to blind, deaf,
or motor-impaired users has failed its own premise. Speak Time began as an
accessibility-inspired idea; the whole product should hold that standard
(formalized in Phase 2 `Accessibility.md` and Phase 3
`AccessibilitySupport.md`).

## 5. Content Review Checklist (v0 — to be finalized in Phase 2)

Every line shipped in the content system must pass:

1. Does it target behavior/moment, never identity/worth?
2. Zero shame, contempt, sarcasm-at-user, catastrophizing, or comparison?
3. Does it pair awareness with an action (or explicitly grant rest)?
4. Is it honest? (No fake stakes, no inflated claims, no pseudo-facts.)
5. Would it be safe read at 2 a.m. by a distressed user?
6. Would the user endorse it knowing why we wrote it? (§2 test)
7. Challenging-voice extra: is it a coach line, not a bully line?
8. Nurturing-voice extra: is it permission-giving without excusing inaction
   forever? (Gentle ≠ "never start.")

## 6. Standing Ethical Commitments (proposed for ratification in Phase 1)

1. The success metric is user action in real life, never time-in-app.
2. No visible debt: the app never accumulates or displays failure history.
3. No dark patterns: the prohibited list in §2 is binding.
4. Challenging ≠ brutal: the §3 style contract is binding.
5. Local-first, minimal data, no sale/sharing of behavioral data.
6. Every awareness feature is opt-in-or-obvious and individually
   disableable.
7. Accessibility is a launch requirement, not a backlog item.
8. Mortality/regret mechanics do not ship without a dedicated ethics review.

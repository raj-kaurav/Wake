# Language System — Canonical Terminology

**Phase:** Governance (ratified with Phase 2 final approval)
**Status:** Frozen — canonical
**Authority:** Every future document, schema, event name, and module name
must align with this glossary. When conflict arises, this document wins.
Companion: `ProductDecisionLog.md`.

---

## 1. Layered Glossary

| Layer | Canonical Term | Notes |
|---|---|---|
| **Product Category** | Time Awareness | Not productivity, todo, habit, or anti-procrastination (outcome ≠ category) |
| **Product Philosophy** | Make time felt. Make starting small. | Dual pillar; short form everywhere |
| **Internal Behavior** | MicroStart | Architectural/domain/analytics term — frozen |
| **User Copy (behavior)** | Start (variants: Start Now, Begin, Just Start) | Independent of architecture; may evolve |
| **Internal Capability** | Ritual | Internal product/engineering language |
| **User Capability** | Activity | External/simple language; do not expose "ritual" until validated |
| **Voice IDs (stable)** | `VoiceA` / `VoiceB` | Architecture, content schema, code — frozen |
| **Temporary Display Labels** | Coach / Friend (provisional) | UX only; Phase 5 branding decision; never in IDs |
| **Content Platform** | Content Engine | Not "Quote Engine" |
| **Optional Philosophy Pack** | The Stoic | Off by default; ethics-gated; post-MVP |
| **Default V1 Widget** | Day Dots | Launch default; not permanent identity |
| **North Star Metric** | Weekly Started Users (WSU) | Counts MicroStarts, not engagement |
| **Behavior Contract** | BehaviorArchitecture.md | Behavioral equivalent of an API contract |

## 2. MicroStart Rules (frozen)

Engineering, analytics, documentation, event names, services, and domain
models **must** use MicroStart:

| Use | Example |
|---|---|
| Service | `MicroStartService` |
| Session / domain | `MicroStartSession` |
| Events | `MicroStartCompleted`, `MicroStartStarted`, `MicroStartAbandoned` |
| Timer | `MicroStartTimer` |
| Widget affordance (internal) | `MicroStartWidgetAction` |
| Analytics | `microstarts_per_active_user_day` |

User-facing copy remains independent and must **not** be forced to say
"MicroStart."

## 3. Voice ID Rules (frozen)

| ID | Role (contract, not label) | Temporary display (non-binding) |
|---|---|---|
| `VoiceA` | Challenging register — behavior/moment, never person | Coach (provisional) |
| `VoiceB` | Nurturing register — permission-giving, not toothless | Friend (provisional) |

- Content schema, settings storage, analytics segments, and code use
  `VoiceA` / `VoiceB` only.
- Display strings are localization keys; swapping labels must not require
  migrations.
- Phase 5 may assign final labels; candidates remain relationship /
  energy / behavior families (`../research/ToneNamingExploration.md`).

## 4. Ritual Language (internal, immediate)

Internally, do **not** refer to product capabilities as "features."

Use ritual names:

| Ritual | Scaffolds |
|---|---|
| **Morning Awareness Ritual** | Widget + S1 content + optional morning pulse |
| **MicroStart Ritual** | Start affordance + timer + completion |
| **Fresh Start Ritual** | Weightless return + Recovering content |
| **Midday Reset Ritual** | Midday pulse / Speak Time + S2 content |
| **Evening Reflection Ritual** | S3 content + rest face |
| **Awareness Ritual** (umbrella) | Any Notice-producing surface |

Externally: Activity / simple verbs. Do not expose "ritual" in store
listing or MVP UI until product validation says otherwise.

Historical Phase 0–1 docs may still say "feature"; new Phase 3+ docs and
all engineering use Ritual / MicroStart / VoiceA|B.

## 5. Content Metadata (mandatory)

Every content item **must** carry:

1. Voice (`VoiceA` \| `VoiceB`)
2. Content Type (T1–T7)
3. Context / slot (S1–S8)
4. Intensity (1–3)
5. Emotional Temperature (Calm \| Focused \| Grounded \| Reflective \|
   Urgent \| Recovering \| Celebratory)

Omitting metadata is forbidden even when adaptive delivery is not in MVP
— future systems must never require a migration for missing fields.

## 6. Words We Do Not Use (internal or external, as noted)

| Avoid | Prefer | Where |
|---|---|---|
| Feature (for capabilities) | Ritual | Internal |
| Start Now (as type/module name) | MicroStart | Internal |
| coach / friend (as IDs) | VoiceA / VoiceB | Schema/code |
| Quote Engine | Content Engine | Everywhere |
| Session (as primary noun for MicroStart) | MicroStart / MicroStartSession | Analytics/domain |
| Productivity app | Time awareness app | Positioning |
| Procrastination (as label for users) | — | User copy |

## 7. Change Control

Amendments to this glossary require: product-owner approval + entry in
`ProductDecisionLog.md` + updates to any Phase 3+ docs that cite the
changed term. Silent drift is a process defect.

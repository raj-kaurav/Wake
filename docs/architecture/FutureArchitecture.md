# Future Architecture

**Phase:** 3 — Technical Planning
**Status:** Draft for review — planning only
**Constraint:** No future item bypasses BehaviorArchitecture mapping or
OutOfScope constitutional bans.

---

## 1. Horizon 2 technical themes

| Theme | Architectural note | Gate |
|---|---|---|
| Lock screen / AOD / watch | Same DayShapeRenderer contract; Arc renderer for circular | Widget Evolution Program |
| The Stoic pack | New VoiceId e.g. `VoiceStoic`; consent store; separate content pack; ethics review | D-008 |
| Calendar-aware T2 | Read-only calendar adapter behind ContentEngine time-fact provider | Research demand |
| Live wallpaper (Android) | NOTICE-only; must not own MicroStart (no affordance) — P2 via widget still required | Battery |
| Own-voice prompts | Local audio store; never upload | P11 |
| Speak Time iOS parity | OS API dependent | H14 revisits |

## 2. Explicitly not architected

Cloud AI coach · sync accounts · social graph · screen-time SDK · regret
simulation · streak service · task DB.

## 3. Extensibility rules

1. New VoiceId = content pack + contract doc + Decision Log.
2. New Ritual = BehaviorArchitecture row before any module.
3. New Renderer = implements DayShapeRenderer; flag default off.
4. Any network requirement for a ritual → Privacy + P11 re-review.

## 4. Framework evolution

If MVP is dual-native, shared domain (KMP) may expand. If MVP is
cross-platform, native widget/TTS bridges remain owned adapters — never
leak into domain.

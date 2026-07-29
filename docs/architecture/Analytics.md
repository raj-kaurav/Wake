# Analytics

**Phase:** 3 — Technical Planning
**Status:** Draft for review
**Product contract:** `../product/SuccessMetrics.md`

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Validates loop metrics without creating A4 UI |
| Ritual | Instrument all; display none as scores |
| Emotional state | — (measurement ethics) |
| Metric | WSU; MicroStarts/user/day; guardrails |
| Anti-goal | A4 scorekeeping (never render analytics to user as performance) |
| Principle | P5, P11, P12 |

---

## 1. Event dictionary (MicroStart vocabulary)

| Event | When |
|---|---|
| `microstart_started` | Session → Running |
| `microstart_completed` | Honest complete / stop ≥20s |
| `microstart_abandoned` | Stop/cancel <20s |
| `microstart_again` | Completion → Again |
| `awareness_pulse_delivered` | N1 shown |
| `awareness_pulse_start_tapped` | Action |
| `awareness_quiet_today` | User retreat |
| `awareness_silence_downgraded` | Respectful silence |
| `speak_time_fired` | Utterance / carrier |
| `widget_microstart_tapped` | Widget affordance |
| `fresh_start_presented` | Flag consumed |
| `voice_selected` / `voice_switched` | VoiceA/B |
| `onboarding_completed` | With decision timing |
| `sentiment_pulse_answered` | H8 (optional) |

**Forbidden events:** anything requiring intention text; "days_missed";
ad attribution; competitor app usage.

## 2. Derived metrics

WSU, resilient adoption, return-after-gap, prompt-dependence ratio,
session-length guardrail — computed server-side or locally in privacy-
preserving pipelines. **Never** bound to UI models.

## 3. Transport

Opt-in; batched; offline queue; identifiable only by rotating install
token (not account). Delete path honored.

## 4. Experiment arms

Remote config for timer duration, framing, renderer flags — binary
defaults always safe if config unreachable.

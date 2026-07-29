# Privacy

**Phase:** 3 — Technical Planning
**Status:** Draft for review
**Ethics:** `../research/EthicalConsiderations.md` §4.4 · Principle P11

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Trust enables Offer→Start (users won't engage if surveilled) |
| Ritual | All |
| Emotional state | Safety |
| Metric | Zero intention exfiltration; opt-out honored |
| Anti-goal | — |
| Principle | P11 |

---

## Data inventory (complete for MVP)

| Data | Purpose | Leaves device? |
|---|---|---|
| VoiceId (VoiceA/B) | Content selection | Only as aggregate segment if analytics on |
| WakeWindow | Day shape / schedules | Aggregate optional |
| Schedules / silence level | Awareness | Aggregate optional |
| Intention string | MicroStart label | **Never** |
| ServingLog | Anti-habituation | Never |
| MicroStart aggregates | WSU / H-series | Opt-in analytics only |
| FreshStartFlag | Recovering content | Never as "days missed" |

## Policies

- No account. No ads. No data brokers. No ATT tracking use.
- Analytics: plain-language disclosure; feature-loss-free opt-out.
- On-device TTS only.
- Privacy nutrition label / Play Data Safety accurate to this inventory.
- Future cloud features require Decision Log + P11 re-clear.

## Empty / About

About screen lists the five local items in grade-6 language (`EmptyStates`
/ Microcopy).

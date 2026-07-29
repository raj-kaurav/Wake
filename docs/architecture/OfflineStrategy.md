# Offline Strategy

**Phase:** 3 — Technical Planning
**Status:** Draft for review

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Entire loop must work offline (Notice→MicroStart→Reflection) |
| Ritual | All MVP rituals |
| Emotional state | Competence; no "you're offline" shame wall |
| Metric | Core loop success rate with network disabled = 100% |
| Anti-goal | A1 (no online destination to browse) |
| Principle | P11 local-first |

---

## Guarantees

1. **MicroStart Ritual** works with airplane mode from cold start.
2. **Day Dots widget** computes from local clock + WakeWindow.
3. **Content Engine** serves from packaged pack (no CDN required).
4. **Speak Time** (Android) uses on-device TTS only.
5. **Analytics** queue locally and flush when online; failure to flush
   never blocks ritual UX (`EmptyStates.md` offline).

## Non-guarantees (honest)

- Store listing / remote config fetch for experiment arms may be stale
  offline — defaults ship in binary.
- Future Stoic pack download (if ever networked) is Horizon 2+ and must
  remain optional.

## Storage

| Data | Location | Sync |
|---|---|---|
| VoiceId, WakeWindow, schedules | Local prefs/db | None |
| Intention string | Local only | **Never transmitted** |
| Content pack | App bundle (+ optional update package signed) | Versioned |
| ServingLog | Local rolling | None |
| Analytics buffer | Local queue | Opt-in flush |

## Empty-state policy

No full-screen offline blocker. If a future online-only surface exists, it
degrades; MicroStart affordance never does.

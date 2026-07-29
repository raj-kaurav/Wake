# Notification Architecture

**Phase:** 3 — Technical Planning
**Status:** Draft for review
**UX contract:** `../ux/NotificationStrategy.md`

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Rest→Notice→Offer; Reflection via N2 |
| Ritual | Midday Reset, Morning Awareness, Evening Reflection, MicroStart close |
| Emotional state | Hand-on-shoulder; never alarm theater |
| Metric | Action rate; respectful-silence activations; zero unsolicited count=0 |
| Anti-goal | A3, A6; P5 re-engagement ban |
| Principle | P2, P5, P9 |

---

## 1. Types (exhaustive — matches UX N1–N5)

| Code | Trigger | Actions |
|---|---|---|
| `PulseNotification` | AwarenessScheduler | MicroStart, QuietToday |
| `MicroStartCompletedNotification` | Session end backgrounded | Open Completion, Again |
| `MicroStartRunningNotification` | Session running | Stop |
| `SpeakTimeCarrierNotification` (iOS) | Speak Time schedule | MicroStart |
| `ForegroundServiceNotice` (Android, if required) | Speak Time reliability | Open Settings |

**Forbidden notification categories** encoded as enum with no cases —
re-engagement, marketing, streak, setup nag. Adding a case requires
Decision Log + BehaviorArchitecture row.

## 2. AwarenessScheduler

Inputs: WakeWindow, pulse cadence, quiet hours, QuietToday, Focus/DND,
MicroStart running?, respectful-silence level, FreshStartFlag (content
only).

Outputs: scheduled platform notifications with ContentEngine line
(`VoiceId`, slot, temperature-filtered).

Rules from UX: suppress while MicroStart running; post-complete cooldown;
landmark restyles morning pulse content, never adds volume.

## 3. RespectfulSilenceEngine

```
ignored_streak >= threshold → downgrade cadence → floor pause
restore = explicit Settings only
```

Persists level locally; emits analytics `awareness_silence_downgraded`
(aggregate).

## 4. Platform notes

- **iOS:** UNNotificationRequest budgets; Speak Time = pre-rendered sound
  assets per HH:MM boundary; Focus respected; no critical alerts.
- **Android:** Notification channels (`awareness`, `microstart`,
  `speak_time`); exact alarms permission path in Permissions.md.

## 5. Deep links

`wake://microstart/start` → MicroStartService.start()
`wake://now` → Now
`wake://microstart/complete` → Completion
Trampoline-free on Android where possible (cold-start budget).

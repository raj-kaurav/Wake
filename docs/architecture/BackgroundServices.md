# Background Services

**Phase:** 3 — Technical Planning
**Status:** Draft for review

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | → Notice (Speak Time); MicroStart completion reliability |
| Ritual | Midday Reset / Awareness; MicroStart |
| Emotional state | Neutral lighthouse; trust (kept schedules) |
| Metric | H14/H15; completion never lost |
| Anti-goal | A2 (default 60 min); battery abuse ≠ trust |
| Principle | P8 honesty, P9, P10 |

---

## 1. Responsibilities allowed in background

1. Fire scheduled pulses / Speak Time boundaries.
2. Complete MicroStart when app killed.
3. Update widget timelines at coarse steps.
4. Flush analytics queue (opportunistic).

**Not allowed:** fetch motivational feeds, geofence stalking, always-on mic,
background social sync.

## 2. Speak Time — Android

Preferred path (spike H15 decides):

- `AlarmManager.setExactAndAllowWhileIdle` at interval boundaries within
  WakeWindow, **or**
- Foreground service only if OEM killing makes exact alarms unreliable —
  then N5 persistent notice with honest copy.

Pipeline: Alarm → `SpeakTimeWorker` → TextToSpeech ("It's HH:MM.") →
audio focus policy (skip on call; duck music per setting) → defer if
screen reader active.

Permissions: `SCHEDULE_EXACT_ALARM` / `USE_EXACT_ALARM` with
accessibility/time-awareness Play justification (`Permissions.md`).

## 3. Speak Time — iOS

No arbitrary background TTS. **Carrier notifications** with pre-rendered
audio assets for each quarter-hour (or configured interval grid) across
24h. Schedule rolling window of requests within pending limits. Honor
Focus. Document tier in Settings (D9).

## 4. MicroStart completion

On start: schedule absolute completion callback (notification + state
finalize). On foreground resume: reconcile. Never drop a ≥20s start
without Completing path.

## 5. Doze / App Standby / OEM

Device lab matrix (Pixel, Samsung, Xiaomi minimum). BatteryOptimization
doc owns user-facing guidance when OEM restricts.

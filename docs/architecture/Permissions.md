# Permissions

**Phase:** 3 — Technical Planning
**Status:** Draft for review
**UX:** F8 in-context pattern (`../ux/UserFlows.md`)

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Enables Notice rituals; never blocks MicroStart |
| Ritual | Pulses, Speak Time only |
| Emotional state | Competence; no pleading |
| Metric | Grant rate after priming; denial ≠ loop failure |
| Anti-goal | A8 (no permission maze in onboarding) |
| Principle | P6, P9, P10 |

---

## 1. Permission inventory

| Permission | When asked | If denied |
|---|---|---|
| Notifications | User enables pulses or Speak Time carrier | Settings deep link; core loop intact |
| Exact alarms (Android 12+) | Enabling Speak Time / precise pulses | Drift honesty copy; coarser schedule |
| Foreground service (Android) | Only if H15 forces Speak Time FGS | Feature limited |
| Battery exemption (OEM) | Optional help screen after detected kills | Documented; never required for MicroStart |

**Never asked:** contacts, location, microphone (recording Horizon 2),
motion, photo library, tracking/ATT (no ads), usage-access/screen-time.

## 2. Flow

1. User toggles ritual on.
2. Priming line in active Voice display label / VoiceId tone.
3. OS dialog.
4. Persist grant state; serve S8 copy if denied.

## 3. Onboarding

Zero OS permission dialogs (P6). Invitations only.

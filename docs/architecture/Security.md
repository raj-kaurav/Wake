# Security

**Phase:** 3 — Technical Planning
**Status:** Draft for review

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Protects trust (P8) and private intention |
| Ritual | All |
| Emotional state | Safety |
| Metric | No plaintext intention in logs/backups exfil |
| Anti-goal | — |
| Principle | P11 |

---

## Threat model (MVP, local-first)

| Threat | Mitigation |
|---|---|
| Malicious content pack update | Signed packs; ship-in-binary default; no unsigned remote lines |
| Analytics MITM | TLS; minimal payload; no intention field in schema |
| Logs leaking intention | Redaction policy; never log intention text |
| Backup exposure | Intention in app-private storage; exclude from world-readable paths |
| Deep link abuse | Validated routes only; no arbitrary navigation stacks |
| Dependency compromise | Pin versions; minimal deps surface |

## Non-goals

Enterprise MDM, E2E sync encryption (no sync), advanced attestation —
out of scope until accounts exist (they should not without Decision Log).

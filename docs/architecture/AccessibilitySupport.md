# Accessibility Support

**Phase:** 3 — Technical Planning
**Status:** Draft for review
**UX:** `../ux/Accessibility.md` (incl. cognitive §9)

### Behavioral mapping

| Question | Answer |
|---|---|
| Behavior transition | Full loop via sight/sound/touch/text |
| Ritual | All |
| Emotional state | Competence; Speak Time deferral to screen reader = respect |
| Metric | Release-blocking a11y suite pass |
| Anti-goal | — (accessibility is premise) |
| Principle | P10 |

---

## Implementation requirements

1. **Semantics:** Every control labeled; widget aggregated description;
   Timer pollable not chatty.
2. **Dynamic type / font scale:** Layouts reflow; no truncated critical
   copy.
3. **Contrast:** AA both Voice palettes × light/dark; widget owns
   background.
4. **Reduced motion:** Renderer + transitions honor platform flags.
5. **TTS coexistence:** Speak Time skips when VoiceOver/TalkBack speaking.
6. **Switch access:** Focus order per WireframeDescriptions.
7. **Cognitive:** Decision-count tests; Fresh Start path in UI tests;
   no badge APIs used.

Automated + manual matrix per release (Accessibility.md §10).

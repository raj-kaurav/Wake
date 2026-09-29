# Behavioral Economics Research

**Phase:** 0 — Discovery & Research (added in revision 1)
**Status:** Draft for review
**Purpose:** Catalog the behavioral-economics findings that bear on a time
awareness product, each with a concrete design consequence. Complements the
psychology-side review in `ProcrastinationScience.md`.

---

## 1. Present Bias & Hyperbolic Discounting

- **Finding:** People discount future outcomes non-exponentially: the drop-off
  is steepest in the near term ("present bias"; Laibson, 1997; O'Donoghue &
  Rabin, 1999). A reward in 10 minutes vastly outranks one in 10 days, far
  beyond any rational rate.
- **Relevance:** This is the economic formalization of the product's core
  enemy. Procrastination is present bias applied to effort: the small
  immediate cost of starting outweighs the large delayed benefit.
- **Design consequence:** Shrink the perceived immediate cost (two minutes,
  one tap) and *pull the reward into the present* (the completion moment, the
  felt relief of having started). Never argue with the user about the future;
  restructure the present.

## 2. Temporal Landmarks & the Fresh Start Effect

- **Finding:** Aspirational behavior spikes after temporal landmarks — new
  week, new month, birthdays, semester starts (Dai, Milkman & Riis, 2014).
  Landmarks open a "new mental account," separating the flawed past self from
  the aspirational present self.
- **Relevance:** Directly exploitable by a time awareness product — we own
  the surfaces where landmarks appear. This is among the strongest levers the
  revision-added research surfaces.
- **Design consequence:** The Content Engine should treat landmark moments
  (Monday morning, first of month, post-lapse return) as first-class content
  slots: "New week. Old file. Two minutes." Landmark framing also gives lapse
  recovery a scientific engine: any hour can be framed as a small landmark
  ("The afternoon is a clean page").

## 3. Loss vs. Gain Framing

- **Finding:** Losses loom larger than gains (~2:1 in classic prospect-theory
  estimates; Kahneman & Tversky, 1979), but loss-framed *messaging* can
  trigger avoidance rather than action, especially under low efficacy —
  consistent with the fear-appeal literature already cited.
- **Design consequence:** Time-remaining (gain/opportunity) framing is the
  default; time-elapsed (loss/depletion) framing is a variant to test,
  plausibly fitting the Coach-style voice. This is Open Question Q2; the
  framing decision is empirical, not aesthetic.

## 4. Defaults & Choice Architecture

- **Finding:** Defaults are among the most powerful known interventions
  (organ-donation natural experiments; Thaler & Sunstein's synthesis).
  Choice overload reduces action (Iyengar & Lepper, 2000).
- **Design consequence:** Every Wake decision ships with a good default and
  at most one alternative visible: default timer length (2 min), default
  intervals (60 min), default voice (the gentler voice — safety-first
  default per `EthicalConsiderations.md`), default widget framing. Settings
  exist; menus of options at decision moments do not. The Start button is
  the ultimate anti-choice-overload design: one option.

## 5. Commitment Devices

- **Finding:** People knowingly pay for external constraints on their future
  selves, and self-imposed deadlines improve performance though less than
  externally imposed ones (Ariely & Wertenbroch, 2002).
- **Relevance:** The entire blocker category (Freedom, Forest) is a
  commitment-device industry. Wake's Start Now is a *micro*-commitment
  device: pressing the button is a public promise to oneself, scoped to 120
  seconds — small enough that the future self who must honor it is only two
  minutes away, where discounting is weakest.
- **Design consequence:** Honor the micro-contract exactly (the timer ends
  when promised — trust economics). Larger commitment devices (deposits,
  social stakes) are out of scope: they import punishment dynamics.

## 6. Scarcity & Tunneling

- **Finding:** Scarcity captures attention and induces "tunneling" on the
  scarce resource (Mullainathan & Shafir, 2013). Deadline panic is time
  scarcity finally becoming visible — effective but costly (stress, poor
  work, spillover neglect).
- **Relevance:** Wake's thesis restated in these terms: **introduce mild,
  chosen time-salience early, so that brutal, involuntary time-salience never
  arrives.** A drip of scarcity awareness instead of a flood.
- **Design consequence:** Calibration matters more than cleverness. Ambient
  signals must sit below the anxiety threshold (user-tunable intensity;
  instrument for aversive-use signals). This is the ethical line in
  `EthicalConsiderations.md` §4.1 expressed economically.

## 7. Anchoring

- **Finding:** Numeric anchors shape judgments even when arbitrary (Tversky
  & Kahneman, 1974).
- **Design consequence:** "Two minutes" is an anchor that defines the felt
  size of "starting." All copy should anchor small units (minutes, not
  hours; "120 seconds" reads even smaller). Conversely, the widget anchors
  the day as *finite* — "16 waking hours" anchors lower than "all day."

## 8. Effort Justification & the IKEA Effect

- **Finding:** People value outcomes more when their own effort produced them
  (Norton, Mochon & Ariely, 2012).
- **Design consequence:** Attribute every win to the user, never to the app.
  Copy rule: "You started" not "Wake helped you start." The app should be
  felt as a doorway, not a crutch — this also protects against
  learned dependence and supports eventual "graduation" (a user who needs
  Wake less over time is a success story, and honestly marketing that is a
  differentiator).

## 9. Peak–End Rule

- **Finding:** Experiences are remembered by their peak and their end
  (Kahneman et al., 1993).
- **Design consequence:** The end of the two-minute timer is the memory of
  the whole session. It must be the best-designed moment in the product —
  calm, congratulatory, honest. Likewise each day's last interaction
  (evening widget state / final spoken time) shapes tomorrow's willingness
  to return; end the day warm, never with an audit.

## 10. Summary Table

| Principle | One-line design consequence |
|---|---|
| Present bias | Restructure the present; never argue about the future |
| Fresh start effect | Landmark-aware content slots; lapse recovery as fresh start |
| Framing | Opportunity framing default; depletion framing as tested variant |
| Defaults | One good default everywhere; choices in settings, not in moments |
| Commitment devices | Start Now = 120-second self-contract, honored exactly |
| Scarcity/tunneling | Mild chosen time-salience now to preempt panic later |
| Anchoring | Anchor small: minutes and seconds, finite day |
| Effort justification | Credit the user, never the app |
| Peak–end | The timer's end and the day's end are flagship design moments |

## 11. Key Sources

- Kahneman, D., & Tversky, A. (1979). Prospect theory. *Econometrica.*
- Tversky, A., & Kahneman, D. (1974). Judgment under uncertainty. *Science.*
- Laibson, D. (1997). Golden eggs and hyperbolic discounting. *QJE.*
- O'Donoghue, T., & Rabin, M. (1999). Doing it now or later. *AER.*
- Dai, H., Milkman, K., & Riis, J. (2014). The fresh start effect. *Management Science.*
- Ariely, D., & Wertenbroch, K. (2002). Procrastination, deadlines, and performance. *Psychological Science.*
- Mullainathan, S., & Shafir, E. (2013). *Scarcity.*
- Iyengar, S., & Lepper, M. (2000). When choice is demotivating. *JPSP.*
- Norton, M., Mochon, D., & Ariely, D. (2012). The IKEA effect. *Journal of Consumer Psychology.*
- Kahneman, D., et al. (1993). When more pain is preferred to less. *Psychological Science.*

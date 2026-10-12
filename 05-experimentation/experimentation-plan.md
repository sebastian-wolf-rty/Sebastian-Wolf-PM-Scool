# A/B Experiment Brief, Riverty business-unit case

## Parameters
| Parameter | Decision |
|---|---|
| Feature under test | Missed-payment explainer |
| Persona | Shift worker, income varies week to week, one or more open claims, resolving them in the portal. |
| Expected outcome | Evidence shows that consumers like Mara do not understand what an affordable instalment agreement looks like, why affordability information is requested, how recommended payment amounts are determined, and what happens if they miss a payment, combined with the fact that only 22% of portal visitors start an instalment journey and only 46% of journeys end in an agreement. |
| Primary success metric | In prototype tests with 8 participants in her situation, all 8 agree without asking the moderator what a missed payment does. In production this is the lever against the 31% seven-day agent-contact rate among journey starters. |
| Baseline rate | 19% of new agreements miss a payment within 60 days. |
| Guardrail metric | he monthly amount does not change on these screens, and every completer can restate the difference between one miss and a second miss. A plan must not be counted as a good Self-Service Rate outcome if she still cannot say what happens when she falls short. |
| Guardrail boundary | Consumer confidence in the decision must not decline |
| Second guardrail | · |
| Minimum Detectable Effect | 3 pts |
| Sample size per arm | 100 |
| Traffic split | 50/50 |
| Test duration | 2 weekly cycles |
| Significance threshold | 0.04 |

## Control vs. Variant
- **Control (A):** At the exact moment she's asked to commit, the system shows her a single number with no reasoning behind it — "It just gave me a number. I don't know why that number and not a different one, so I didn't trust it" — and no explanation of what happens if her variable income means she falls short — "Nobody told me what happens if I miss one payment versus two. I just assumed the worst." This persona drives the highest agent-escalation rate of any archetype in the research (high cost per claim), and is also the only persona tied to a confirmed post-agreement default — a case our own research explicitly flags as "resolved at creation, but didn't hold" (payment default risk).
Workaround: Call Consumer Support
- **Variant (B):** Screen A — Plan summary (€48 / 28th / 6 instalments / 2 claims · one plan). Agree disabled until acknowledged.
Screen B — Fixed oneMiss / secondMiss cards (≤40 words), grace-period line, checkbox, Continue disabled until checked.
Screen C — Same amount and payment day, repeated outcomes, “You reviewed this before you agreed.”
- **Held constant (isolation check):** No phone, chat, or agent contact controls; amount is not editable.

## Hypothesis
> I believe that Missed-payment explainer for Shift worker, income varies week to week, one or more open claims, resolving them in the portal. will result in Evidence shows that consumers like Mara do not understand what an affordable instalment agreement looks like, why affordability information is requested, how recommended payment amounts are determined, and what happens if they miss a payment, combined with the fact that only 22% of portal visitors start an instalment journey and only 46% of journeys end in an agreement., as measured by a 3 pts change in In prototype tests with 8 participants in her situation, all 8 agree without asking the moderator what a missed payment does. In production this is the lever against the 31% seven-day agent-contact rate among journey starters. within 2 weekly cycles. We will protect he monthly amount does not change on these screens, and every completer can restate the difference between one miss and a second miss. A plan must not be counted as a good Self-Service Rate outcome if she still cannot say what happens when she falls short. throughout the test.

## Shipping criteria
> We will **ship** if In prototype tests with 8 participants in her situation, all 8 agree without asking the moderator what a missed payment does. In production this is the lever against the 31% seven-day agent-contact rate among journey starters. improves by ≥ 3 pts at 0.04 and he monthly amount does not change on these screens, and every completer can restate the difference between one miss and a second miss. A plan must not be counted as a good Self-Service Rate outcome if she still cannot say what happens when she falls short. does not reach Consumer confidence in the decision must not decline after 2 weekly cycles.
> We will **iterate** if direction is positive but lift is below the MDE.
> We will **kill** if the primary metric shows no improvement or moves negatively.
> The read date is fixed at the end of 2 weekly cycles, no results reviewed before this date.

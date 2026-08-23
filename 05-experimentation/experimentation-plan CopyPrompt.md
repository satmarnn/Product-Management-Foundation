# A/B Experiment Brief, RouteLogic (B2B)

## Parameters
| Parameter | Decision |
|---|---|
| Feature under test | Real-Time Reassignment Push |
| Persona | The Dispatcher  who coordinates driver routes and monitors delivery status from a central dashboard. |
| Expected outcome | Instant reassignment notification - reassignment speed. |
| Primary success metric | 4-8min |
| Baseline rate | 8 -15min |
| Guardrail metric | < 8-15min |
| Guardrail boundary | > 8 -15min |
| Second guardrail | · |
| Minimum Detectable Effect | -3 |
| Sample size per arm | 15 |
| Traffic split | 50/50 |
| Test duration | 20 days |
| Significance threshold | 5% |

## Control vs. Variant
- **Control (A):** Reassignments take 8–15 minutes to reach drivers with no notification. Status updates lag 20–60 minutes behind reality.
- **Variant (B):** Reassignments take 8–15 minutes to reach drivers with no notification. Status updates lag 20–60 minutes behind reality.
- **Held constant (isolation check):** The reassignment flow itself: same screens, same taps, same confirmation dialog for the dispatcher.
The dispatcher's dashboard UI and status indicators — unchanged.
The driver app's underlying poll cycle — still runs in the background at the same interval; the notification supplements it, it doesn't replace it.
No "delivery confirmation" or "seen by driver" signal is added to the dispatcher's screen (that's Stage 1's second half, deliberately deferred so this test measures the notification alone).
No changes to WhatsApp usage, dispatcher training, or messaging — any change in workaround behavior must come from the product, not a nudge to stop.

## Hypothesis
> I believe that Real-Time Reassignment Push for The Dispatcher  who coordinates driver routes and monitors delivery status from a central dashboard. will result in Instant reassignment notification - reassignment speed., as measured by a -3 change in 4-8min within 20 days. We will protect < 8-15min throughout the test.

## Shipping criteria
> We will **ship** if 4-8min improves by ≥ -3 at 5% and < 8-15min does not reach > 8 -15min after 20 days.
> We will **iterate** if direction is positive but lift is below the MDE.
> We will **kill** if the primary metric shows no improvement or moves negatively.
> The read date is fixed at the end of 20 days, no results reviewed before this date.

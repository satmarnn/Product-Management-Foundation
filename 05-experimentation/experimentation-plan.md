# Experimentation Plan (Module 5)

## Get your documents ready
- **From M3, your hypothesis sentence:** Based on Reassignments time(8–15 minutes) taken to reach drivers with no notification. Status updates lag 20–60 minutes behind reality and Quantitative data of CSAT score by role(Coordinators) ×  Compliance  feature cluster : 2.2 and CSAT score by role(Coordinators) ×  Reporting  feature cluster : 1.3. I believe that Reflection of data in dashboard occurs real-time(Real time dashboard) and Reassignments will happen instantly so that reach drivers with instant notification(reduce High friction) for Coordinators and Drivers,  will result in Ontime delivery from drivers that aligned with dispatcher avoid reroutes, saves more time and accomplish more deliveries in a day, as measured by a 50%-75% change in  Assign routes & Compliance Checks. I will protect Timeframe will not increase beyond the benchmark for Assigned route feature and Compliance checks and will make a go/no-go decision after optimizing the feature with the effective workflow and fixing the identified issue behind the data communication speed rate.
- **From M3, your primary success metric & guardrail metric:** Primary success metric is Assign routes & Compliance Checks will match benchmark timeframe.
Guardrail Metric: Timeframe change should not impact the back end logic  of  core process(reassignment).
- **From M4, the feature you scoped in your PRD this is what you're testing:** FR-1 — Reassignment notification latency
When a reassignment write completes, a push notification must be dispatched to the driver's device within 10 seconds.
FR-2 — Offline fallback
If push delivery is not confirmed within 60 seconds, the system must automatically fall back to SMS.
FR-3 — Notification state visibility
The dashboard must display the reassignment's current state (Sent, Delivered, Acknowledged) and update it within 5 seconds of each state change, without requiring a manual page refresh.

## Define your experiment parameters
- **Feature under test pull from your M4 PRD:** Epic 1: Real-Time Reassignment Push
US-1: Instant notification on reassignment
As a Coordinator, I want the driver to be notified the moment I reassign their route, so that I don't have to call or text them myself to make sure they know.
US-2: Flag reassignments that go unanswered
As a Coordinator, I want to be alerted if a driver hasn't acknowledged a reassignment after a set time, so that I know to follow up before it becomes a missed delivery.

Epic 2: Real-Time Staleness Reflection
US-3: Know how old the data I'm looking at is
As a Coordinator, I want to see how long it's been since a delivery's status last updated, so that I can trust the dashboard instead of calling the driver to double-check.
US-4: See what's gone stale without hunting for it
As a Coordinator, I want stale deliveries automatically surfaced at the top of my dashboard, so that I don't have to scan the full list or keep a side tracking sheet to catch what's falling behind.
- **Persona pull your M2 persona:** The Dispatcher  who coordinates driver routes and monitors delivery status from a central dashboard.
- **Expected outcome the behaviour change you expect, from your M3 hypothesis:** Instant reassignment notification - reassignment speed.
 - Real-Time Staleness Reflection: Know how old the data I'm looking at is.
- **Primary success metric the one number that defines success, from M3:** Reassignment speed rate is 2* faster
Dashboard speed rate is 3* faster
- **Baseline rate today's rate of your primary metric, from your M3 data:** Reassignment speed is 8-15min.
Dashboard update speed is  30-60min
- **Guardrail metric & boundary what must not break, and how far it can move before you investigate:** Reassignment back end process and data update logic in dashboard should not change while working on increasing the speed.
- **Minimum Detectable Effect (MDE) the smallest improvement worth shipping, your floor:** Average time from reassignment to driver acknowledgment must drop to ≤2 minutes to count as a detectable attributable effect. Dashboard update average time reduce to 10 min.
- **Sample size per arm use the calculator in the builder, baseline + MDE:** 15
- **Traffic split & test duration 50/50 standard · cover ≥ 2 weekly cycles:** 50/50
- **Significance threshold p < 0.05 is standard, explain any deviation:** 5%

## Define your control and variant
- **Control (A) the current experience, reference your M2 moment of misery and M3 funnel/workflow data:** Reassignments take 8–15 minutes to reach drivers with no notification. Status updates lag 20–60 minutes behind reality.
- **Variant (B) your single change, copy the relevant screens & functional requirements from your M4 PRD:** Reassignments take 8–15 minutes to reach drivers with no notification. Status updates lag 20–60 minutes behind reality.
- **Isolation check, what has NOT changed? list everything identical between arms (app version, recommendation engine, notifications, onboarding). If something changed inadvertently, your test is compromised.:** The reassignment flow itself: same screens, same taps, same confirmation dialog for the dispatcher.
The dispatcher's dashboard UI and status indicators — unchanged.
The driver app's underlying poll cycle — still runs in the background at the same interval; the notification supplements it, it doesn't replace it.
No "delivery confirmation" or "seen by driver" signal is added to the dispatcher's screen (that's Stage 1's second half, deliberately deferred so this test measures the notification alone).
No changes to WhatsApp usage, dispatcher training, or messaging — any change in workaround behavior must come from the product, not a nudge to stop.

## Formalize your hypothesis & shipping criteria
- **Your hypothesis (filled in):** Real-Time Reassignment Push for the Dispatcher will result in a reduction in median reassignment-to-driver-acknowledgment time from 8–15min to 4–8min (a ≥3min improvement), measured by device-level notification-received timestamps compared against reassignment-confirmation timestamps, within 20 days or the pre-registered event-sample window, whichever is later.
- **Your shipping criteria (filled in):** Ship to 100% if, after the test window closes:

Primary: Median reassignment-to-acknowledgment time in Variant is ≥3min lower than Control, at p < 0.05.
Guardrail 1: Status-lag metric shows no significant degradation in Variant.
Guardrail 2: Driver app crash rate and notification opt-out rate stay within an agreed tolerance (e.g. ±2pp) of Control.
- **Hardest parameter to define, and did it change your hypothesis? quick debrief:** "Reaches the driver" is ambiguous across at least three different moments, and each gives a different, defensible-sounding number:

Sent — the server dispatches the push. Easiest to measure, but tells you nothing about the driver's actual experience — a push can be sent and never arrive.
Delivered — the device confirms receipt at the OS level. Better, but still doesn't mean the driver has seen it — phone could be in a pocket, screen off, notification sitting in the tray.
Acknowledged/seen — the driver actually opens or views the updated route. Closest to what the dispatcher's trust actually depends on, but it's the hardest to instrument reliably (does a screen-on event count? an app-foreground event? an explicit tap?).

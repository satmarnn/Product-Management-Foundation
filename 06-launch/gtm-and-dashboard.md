# GTM Launch Plan, RouteLogic (B2B)

| Field | Value |
|---|---|
| Feature | Real-Time Reassignment Push |
| Goal | Conversion |
| Launch tier | M, Targeted |

## Goal & Audience
- **Goal:** Conversion, Reduce dispatcher reliance on the WhatsApp workaround by closing the reassignment-notification gap — measured concretely as: cut reassignment-to-acknowledgment time from 8–15min to ≤5min (median), with no regression in status-lag accuracy or app stability, within the current quarter.
- **Target audience:** Dispatchers at enterprise accounts already flagged for renewal risk (Wave 1) — this is where the business cost of the trust gap is most acute and most measurable, per the ops manager and regional manager research findings.

## Launch Tier
- **M, Targeted**, Internal Enablement:  CS / Account Management: Brief before Enterprise accounts flagged for renewal risk— equip them to proactively mention this to at-risk accounts named in research (ops manager, regional manager threads) as evidence of responsiveness to the specific frontline complaints they raised.
Support: Update macros for "reassignment not received" tickets — expected resolution time drops from "check back in 15 min" to near-immediate; flag anomalies as bugs, not expected latency.
Sales (renewal conversations): Do not lead with this as a headline feature — position it as evidence of a workflow-first roadmap in progress, since one fix won't reverse an adoption trend on its own.

## Channels
1. **Owned: The dispatcher is in the dashboard for their entire shift — this is the one place we know they'll be, with zero extra effort required to reach them.**
2. **Owned: This is the highest-leverage channel for the accounts that actually matter here — the ones where research named renewal risk explicitly. A dispatcher noticing faster notifications passively is not the same as an ops manager hearing, from their AM, that the specific complaint they raised was acted on.**
3. **Owned: Targets the people who raised the risk in the first place, not just the dispatcher using the feature day-to-day. Closes the loop: "you told us this, here's what changed" — which does more for renewal risk than the feature working silently ever could.**

## Enablement & Assets
Sales / Account Management: The exact scope of what shipped — instant notification only, not a "received" confirmation, not a status-lag fix. They must not promise more than what's live. 1-page renewal talking-point sheet — "here's what they told us, here's what shipped, here's what's next" in plain language, no engineering jargon.
CS / Support: New expected resolution time for "reassignment not received" tickets — near-instant, not "check back in 15 minutes." Anything outside that window post-launch is a bug, not expected latency.
Updated support macro/script for reassignment-timing tickets, reflecting the new expected latency.
Internal escalation trigger sheet — what ticket volume/pattern in the first 72 hours should get flagged up as a possible guardrail breach, and to whom.

## Ownership, Budget & Timeline
- **Ownership & budget:** Finalize A/B test result & shipping decision - PM - Must complete before anything below starts — nothing ships or gets communicated on an unresolved test.
Confirm renewal-risk accounts account list - PM + AM
Write 1-page renewal talking-point sheet - Product marketing team.
No new spend required. Every asset here is a writing/time cost, not a dollar cost — consistent with the M-sizing and owned-only channel calls made earlier.
- **Timeline:** Phase 1:  Beta (Days 1-20+)
Day 1–20	A/B test runs (Control vs. Variant).
Day 20 (or later, if underpowered)	Go/no-go on shipping decision.
Parallel, Day 1–20	Draft assets that don't depend on the outcome.
Phase 2 -  Launch Moment (Wave 1: Days ~21–35)
Day 21	Feature flag enabled for Wave 1 accounts
Day 21	In-app changelog goes live
Day 22–23	Live CS/AM team briefing
Day 24–28	Direct outreach to named Wave 1 stakeholders
Phase 3 — Post-Launch (Wave 1 monitoring → Wave 2 decision → Stage 2 handoff)
Day 21–35	Continuous guardrail + diagnostic metric monitoring
Day 28–35	CS debrief capture (qualitative signal from renewal conversations)
Day 35	Wave 1 → Wave 2 go/no-go
Post-Wave 2  Handoff to Stage 2 scoping

## Success Metrics
- **Metrics:** 1. Reassignment-to-acknowledgment time (Leading indicator)
Target: Median ≤5min, down from 8–15min baseline, sustained at Wave 1 scale (not just during the A/B window).
2. WhatsApp-duplication rate per dispatcher (Lagging/behavioral indicator)
Target: Measurable decline from baseline, tracked via self-report and/or CS debrief capture (Phase 3), not just at launch but through the full Wave 1 window.
3. Renewal-risk account sentiment (Qualitative, from CS debrief)
Target: Direct evidence, in AM-reported conversations, that Wave 1 stakeholders (the ops manager and regional manager roles who named renewal risk in research) connect this change to their specific complaint.
- **Bad signal to watch for:** reassignment time hits the ≤5min target and holds — but the WhatsApp-duplication rate doesn't move.
- **Likely post-launch decision:** This is the most probable outcome, not the worst-case or best-case, because it's exactly what the bad-signal analysis predicts: reassignment speed hitting target while WhatsApp-duplication stays flat isn't a launch failure, it's a launch that did its narrow job (propagation speed) and surfaced that the goal needs the deferred second half (confirmation loop) to actually land.

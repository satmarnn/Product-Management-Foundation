# Product Health & Insights Summary

## Executive Summary

The product's backend and administrative capabilities remain a genuine strength, but core frontline usability has degraded to the point of threatening adoption and retention. Drivers and dispatchers are increasingly operating outside the platform — via texts, WhatsApp, and paper manifests — because fundamental workflows are slow, unreliable, or unreachable when connectivity is poor. The tension is structural rather than incidental: feature accumulation and reporting depth have expanded while the speed, resilience, and discoverability of the actions frontline users perform dozens of times a day have not kept pace.

## Thematic Synthesis

### Technical Stability

Reliability issues are concentrated at the moments that matter most — mid-route, under weak signal, and during dispatch handoffs — and they are severe enough to be actively pushing users toward informal, off-platform workarounds (texting dispatchers, paper backups, WhatsApp groups).

- Application crashes mid-route once the stop list exceeds roughly 40 stops, wiping remaining stops and forcing a full reload from the server — **Critical**
- Dispatch route reassignments take 8–15 minutes to reach the driver's device, with no push notification, so drivers act on stale information — **Critical**
- Proof-of-delivery photo uploads fail silently on weak signal in roughly a third of attempts, with no retry queue or confirmation, prompting repeated retakes — **High**
- Dispatcher-facing status updates lag 20–60 minutes behind actual delivery activity, undermining trust in the live dashboard — **Medium**

### Discovery / UX

Core, high-frequency actions have become harder to find and slower to execute as the product has accumulated features, disproportionately affecting new users and daily frontline workflows.

- Marking a delivery complete requires three taps across three separate screens, with no single-tap path — the most-cited frontline frustration — **High**
- Frequently used actions (Start Route, Mark Delivered) are now buried two to three menu levels deep, with no way to configure or prioritize a home screen — **High**
- New drivers report the interface is not learnable within a day; specific functions such as reporting a failed delivery are difficult to locate, and the onboarding tutorial cannot be reopened after first launch — **Medium**
- Overall feature surface has outpaced the needs of frontline users, who report using only a small fraction of available functionality while struggling to access the portion they do need — **Medium**

### Algorithmic Curation

Route optimization is not accounting for real-world constraints that drivers navigate daily, leading to routine manual overrides and eroding confidence in the system's guidance.

- Optimized routes do not account for road closures or access constraints such as loading docks and one-way streets, and there is no mechanism to save local corrections — **Medium**
- GPS-based "arrived at stop" detection drifts by up to 200 meters in dense urban areas, producing incorrect automatic status changes — **Low**

### Platform Sync / Connectivity

The product's dependence on continuous connectivity is a poor fit for a meaningful share of real-world usage conditions, particularly rural and low-signal routes.

- Offline mode does not cache the stop list, leaving drivers with a blank route and no way to work when connectivity drops — a condition that effectively blocks rural routes entirely — **High**
- The propagation delay for dispatch changes (noted above) and the dashboard status lag (noted above) both compound this sync gap between field and back office.

### Minor Technical Debt

Low-severity items — GPS drift in dense urban areas and an onboarding tutorial that cannot be reopened after first launch — remain open and contribute incrementally to the broader usability gap described above.

## Cross-Cutting Observation

Across both the interview notes and bug reports, a consistent pattern emerges: strength in administrative and reporting functionality is co-located with, and increasingly overshadowed by, fragility and friction in the daily field workflow. Multiple accounts describe adoption and renewal risk stemming specifically from the frontline experience rather than from the product's analytical or administrative capabilities.

# Individual Insights — Development Process

> Module 6 · Launch Impactful GTM Plans — ★ Deliverable 6 (reflection)



## Friction points

The Variant field in the A/B brief was a copy-paste error identical to Control — a small documentation slip, but it would have invalidated the entire experiment if it had shipped unreviewed. This is the clearest evidence in the whole process that a good template doesn't protect against fatigue-driven repetition; only a deliberate pressure-test step catches it.
The guardrail and primary metric started conflated ("protect < 8-15min" restating the same range as the improvement target). This friction point recurred conceptually later — the sample-size math (n=15) and the "reassignment speed" event-definition ambiguity (sent vs. delivered vs. seen) both stemmed from the same root habit: naming a metric before defining precisely what it measures.
Section-by-section GTM building without a running document created a real risk of drift — ownership listed roles instead of names by the time the full plan was pasted back in the final pressure-test, even though names had already been established earlier in the same thread. Incremental building is good for focus, but it needs a consolidation checkpoint or earlier decisions silently regress.
_____

## Key learnings

Speed metrics and trust metrics are not the same metric, and conflating them is the single most repeated failure mode across this entire exercise — it showed up in the experiment design (reassignment speed vs. dispatcher trust), the shipping criteria (technical pass vs. behavioral success), and the success metrics section (leading vs. lagging indicator). Once named once, it became the lens for reviewing everything downstream.
Deliberately deferring a feature (the "received/seen" confirmation) creates a predictable, nameable risk later — not a vague "something might go wrong" but a specific, describable bad signal (speed improves, duplication doesn't). Scoping decisions early in a roadmap should come with their downstream signal pre-written, not discovered after the fact.
A role is not an owner. This recurred at two points — the "Held Constant" experiment list once slipped from name to category, and the final GTM plan pasted back with "PM," "AM," "Product marketing team" as if those were commitments. The lesson generalizes: any document that outlives a single working session should be checked, not assumed, for whether accountability degraded into abstraction.

_____

## Aha! moment

The bad-signal analysis revealed that a technically successful launch and a strategically failed one look identical on the primary metric. Reassignment time hitting ≤5min and holding is unambiguous good news on its own dashboard — but paired with a flat WhatsApp-duplication rate, it's actually evidence that the deferred Stage 2 work isn't optional-later, it's blocking-now. That reframe — that the combination of metrics, not any single one, is what tells the true story — is the moment the whole exercise stopped being "did the feature ship correctly" and became "did the feature do what it was for." Everything from that point forward (the post-launch decision, the pressure-test's bad-signal rewrite) followed directly from holding that distinction rather than collapsing back into a single success/fail metric.

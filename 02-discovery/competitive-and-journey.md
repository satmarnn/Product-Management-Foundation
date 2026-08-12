# Competitive Analysis & Journey Map (Module 2)

## Responses
- **Role, who are you solving for? (the specific user segment or profile):** The Dispatcher  who coordinates driver routes and monitors delivery status from a central dashboard.
- **Goal, what is this user ultimately trying to achieve?:** Wants to trust that what the dashboard shows reflects reality, so they can coordinate the fleet without double-checking everything manually.
- **Friction, the main barrier (moment of misery) stopping them from succeeding:** Reassignments take 8–15 minutes to reach drivers with no notification.
Status updates lag 20–60 minutes behind reality.
The administrative burden here isn't paperwork — it's manually re-verifying a system that's supposed to do the verifying for them.
- **External tools, the outside platforms or tools the user is forced to use:** The research is explicit on this — the dispatcher doesn't file a ticket or escalate through official channels. They maintain a running WhatsApp group with drivers and treat that as the system of record, not the dashboard.
- **The process, the 3 to 5 manual steps the user takes to get the job done:** Reassign the route in-app — dispatcher makes the change on the platform as designed.
Assume it hasn't landed — because they know from experience it takes 8–15 minutes with no push notification (BUG-2044), they can't assume the driver has seen it.
Re-send the same instruction manually via WhatsApp — duplicating the action they just took in-app, in a channel they know is instant.
Wait for a reply, not a status change — they confirm receipt by watching for a text back from the driver, because the dashboard won't reflect it reliably even once it does land.
- **Core frustration, the exact moment the process feels most “broken”:** The dispatcher is now doing the job twice — once in the system they were given, and once by hand in a tool that wasn't designed for fleet coordination at all.
- **The evidence, a specific quote or behavior from the research that proves this:** Every reassignment now costs two actions instead of one, and every status check requires the dispatcher to hold two competing pictures of reality in their head and manually decide which to believe.
- **📎 Your journey map, a shareable link, or the map file you committed (e.g. journey-map.html):** https://github.com/satmarnn/Product-Management-Foundation/blob/main/02-discovery/Product_Health_Insights_Summary.md

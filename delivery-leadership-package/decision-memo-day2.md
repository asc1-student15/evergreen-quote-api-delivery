# Decision Memo: Day 2 Decisions

**Date:** 11/9/26
**Author:** Tina Matthys
**Decision area:** Day 2 Scope Updates

## Context
A partner aggregator wants renters coverage quotable through the API by Thursday.
The Platform team's monthly scan flagged a moderate-severity CVE on node:22-alpine, the base image the engineering team's Dockerfile uses. They cannot patch this until next week.

## Options considered
1. **Rejected Option A: Add Renter's Coverage AND Upgrade Node this week.** 
    Pros: Everything would be able to get out the door this week, with extra functionality added and no security risks.
    Cons: This puts a stretch on the developers to perform analysis and the additional work within the existing timeline.
2. **Option B: Add Renter's Cover BUT wait for the Platform team's Node Upgrade next week.** 
    Pros: Additional functionality will be provided and the Platform team's normal upgrades next week will keep our other scope intact for this week.
    Cons: The project will not go live until next week sometime.
3. **Rejected Option C: No updates to current scope BUT wait for the Platform team's Node Upgrade next week.**
    Pros: This is the least impactful option for our current scope and capacity.
    Cons: The partner will not get extra functionality, nor will the project go live on time.

## Recommendation and Why
We will pursue Option B, since the addition of Renter's coverage is a small scoped enhancement with the scaffolding already in place, but the time required to upgrade Node and keep it separate from this project's work would put other agreed-upn features at risk. We cannot go live without that Node upgrade, so we will communicate that to the sponsors.

## What would change my mind
If the Platform team were able to provide us with the upgrade code or get it pushed a week early for us, that would allow us to revisit Option A.

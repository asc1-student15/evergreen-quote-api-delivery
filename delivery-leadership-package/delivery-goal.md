# Delivery Goal: Evergreen Quote

## Goal

"By Thursday EOD, the assembled Evergreen Quote API is merged to main and demoed in a container on a local K8s cluster."

## "Done" looks like

- The API answers every documented route: list, fetch by id, create with a computed premium.
- The same data answers through GraphQL, with the explorer at `/explorer`.
- `npm test` passes; the safety net holds.
- The containerized API serves the same answers as the dev server, and the CI run on the merge commit is **green**.
- The cluster demo shows three API pods behind one Service.
- A reviewed PR is merged, branch deleted.
- `delivery-leadership-package/` is complete and committed.

## Out of scope (this week)
- No authorization
- No real rating engine
- No multi-region story

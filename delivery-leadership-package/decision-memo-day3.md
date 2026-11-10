# Decision Memo: Day 3 Decisions

**Date:** 11/9/26
**Author:** Tina Matthys
**Decision area:** Day 3 Copilot Usage

## Context
Used Copilot to create an additional test that POSTs to /api/quote with a missing field (no coverageAmount) and returns 400.

## Recommended Option Selected - Use Copilot's Suggested Test
Use the test that Copilot created each time a local or CI test is run, since it accurately verifies the API rejects a bad quote request when required data is missing.
Sends a POST request to /api/quote intentionally omitting coverageAmount, and expects a 400 error, since coverageAmount is a required field for a quote.
The server should validate incoming data before creating a record
If the field is missing, the request is invalid and should fail early instead of saving bad data.


## What would change my mind
If copilot would have returned a test that failed when 'npm test' was run, we wouldn't be able to use it without updates.

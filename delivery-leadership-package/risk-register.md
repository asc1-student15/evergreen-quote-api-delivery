# Risk Register

| # | Risk | Owner | Likelihood (L/M/H) | Impact (L/M/H) | Mitigation | Trigger to escalate |
|---|---|---|---|---|---|---|
| R1 | The API returns 201s but a number inserted into the DB is wrong | Dev Team | M | H | Run `npm test` after every assembly step, not just before merge, to clean up the entries; Re-seed if necessary | If tests are still red by Thurs at 16:00, hold the release |
| R2 | The quote service returns a quote that cannot possibly be correct using basic logic | Dev Team | M | H | Check calculations and base rates for errors; re-run tests | If any rates are still looking 'off' by Thurs at 16:00, hold the release |
| R3 | Build fails with a red CI run | Dev Team | L | H | Investigation into what specifically failed, then a clean 'npm run build' and 'npm test' | If the build is still failing on Thurs at 12:00, we cannot deploy |
| R4 | Database becomes unavailable and quotes are unable to be saved or retrieved | Dev Team | L | H | Consult with project sponsors to ask about removing the save/retrieve features and just providing real-time quoting, while the Dev Team investigates a fix | Any time the database goes down during development should be a trigger, but for the release, it will depend on project sponsor response |
| R5 | The coded rates are mismatched with what the API shows as the sponsor's expected rates | Dev Team | M | M | Correct the coded rates to match with the sponsor's expectations and ensure the API is updated to reflect that | If the mismatch cannot be fixed before Thurs at 14:00, the release should be held - we do not want mistrust associated with questionable rating |

## How I'll use this register
I'll review and add to this risk register each morning after check-in to confirm no expected issues are present. All project sponsors, plus managers and developers on the team, have access to these concerns.
# Delivery Review: Evergreen Quote

## Slide 1: Delivery goal & did we hit it?
- Goal (one sentence): The delivery goal was partially completed, since all parts of the planned work were completed and the code was merged to main with a green CI run, but the release deployment being held for an external team dependency.
- Hit? ☐ Yes  x Partially  ☐ No

## Slide 2: What shipped
http://localhost:3000/
```
{"message":"Evergreen Quote API","status":"ok"}
```
http://localhost:3000/api/quotes
```
[{"_id":"q1","type":"auto","age":41,"coverageAmount":50000,"monthlyPremium":96,"tags":["renewal"],"__v":0,"createdAt":"2026-11-10T19:28:53.632Z","updatedAt":"2026-11-10T19:28:53.632Z"},{"_id":"q2","type":"home","age":52,"coverageAmount":250000,"monthlyPremium":375,"tags":["new"],"__v":0,"createdAt":"2026-11-10T19:28:53.634Z","updatedAt":"2026-11-10T19:28:53.634Z"},{"_id":"q3","type":"life","age":29,"coverageAmount":100000,"monthlyPremium":84,"tags":["new"],"__v":0,"createdAt":"2026-11-10T19:28:53.634Z","updatedAt":"2026-11-10T19:28:53.634Z"},{"_id":"q4","type":"auto","age":23,"coverageAmount":30000,"monthlyPremium":100.8,"tags":["young-driver"],"__v":0,"createdAt":"2026-11-10T19:28:53.634Z","updatedAt":"2026-11-10T19:28:53.634Z"},{"_id":"q5","type":"home","age":38,"coverageAmount":180000,"monthlyPremium":248.4,"tags":["renewal","bundle"],"__v":0,"createdAt":"2026-11-10T19:28:53.634Z","updatedAt":"2026-11-10T19:28:53.634Z"},{"_id":"q6","type":"auto","age":67,"coverageAmount":40000,"monthlyPremium":96,"tags":["senior"],"__v":0,"createdAt":"2026-11-10T19:28:53.635Z","updatedAt":"2026-11-10T19:28:53.635Z"}]
```
http://localhost:3000/api/quotes/q1
```
{
  "_id": "q1",
  "type": "auto",
  "age": 41,
  "coverageAmount": 50000,
  "monthlyPremium": 96,
  "tags": [
    "renewal"
  ],
  "__v": 0,
  "createdAt": "2026-11-10T19:28:53.632Z",
  "updatedAt": "2026-11-10T19:28:53.632Z"
}
```

- Merged PR: https://github.com/asc1-student15/evergreen-quote-api-delivery/pull/11
- Latest CI Run: https://github.com/asc1-student15/evergreen-quote-api-delivery/actions/runs/42889463642

## Slide 3: Two key decisions
- **Decision 1:** Add Renter's Cover BUT wait for the Platform team's Node Upgrade next week. 
    Why it mattered: The change is fairly small and easy to safely implement. It will be a bonus feature to give the stakeholder for waiting an extra week to get the entire feature.
- **Decision 2:** Use the test that Copilot created each time a local or CI test is run, since it accurately verifies the API rejects a bad quote request when required data is missing.
    Why it mattered: Using Copilot to add unit tests saves us time and adds quality coverage/additional safety nets.

## Slide 4: Risks & injects
- Top risk we tracked: R3 | Build fails with a red CI run
- Inject #1 (Tue): 
The stakeholders wanted to increase scope to include Renter's coverage options. In addition, the Platform team informed us that a required Node Upgrade is required before we release our API.
    How we re-prioritized: We decided to add the Renter's coverage but hold off on the release until the Node Upgrade could be safely implemented.
- Inject #2 (Wed): 
A Prod Issue was reported indicating that all quotes were erroring to the user with unwanted behavior. In addition, the development team, while trying to fix the issue, committed an incorrect conditional that failed the CI run due to test assertion errors. 
    What we did: We reported the defect back to the development team for further investigation and will hold the fix until the CI run comes back green. 
    The go/no-go call: We decided to fix this issue but still hold the release for the Node Upgrade next week.

## Slide 5: What I'd do differently next round
- I would have my developers put in safeguards to not be able to commit code that fails on any unit tests

## Q&A prep: likely questions
- Why did you let scope creep and add Renter's coverage? 
    We had time at the end of the week and even into next week before we can release anyway.

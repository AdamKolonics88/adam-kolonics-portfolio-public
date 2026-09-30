# Test Plan Template

## Scope
What is being tested, what is not, and the environment used (never production personal data).

## Test cases
| ID | Area | Scenario | Steps | Expected result | Actual result | Evidence | Pass/Fail |
|---|---|---|---|---|---|---|---|

Cover at least:
- Every workflow state and transition, including rejected and cancelled paths
- Notifications (content, recipient, timing)
- Role-based access and row-level security for every role
- Data retention and deletion
- Error handling and retries
- Regression of previously working features

## Exit criteria
All critical cases pass with evidence; open defects are logged with an owner and a decision.

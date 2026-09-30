# Performance Review Platform

**Tools:** Power Apps, Power Automate, Power BI, SharePoint, Microsoft Forms
**Scope:** performance-evaluation system launched to production for 60 employees
**Diagram:** [architecture](../diagrams/performance-review-platform-architecture.md)

## 1. Context

Performance reviews for 60 employees needed one consistent process. Review data is sensitive, so who can see which record mattered as much as the workflow itself.

## 2. Business Problem

The organization needed structured input, clear routing between participants, and reporting, while each person could see only the data their role allowed. Review data also had to be removable when it was no longer needed.

## 3. My Role and Ownership

I built the system, wrote the test plans, ran the access testing, documented the solution, and completed the production handoff.

## 4. Solution Design

- **Input:** Microsoft Forms and Power Apps for structured review input.
- **Routing:** Power Automate sends each review step to the right participant.
- **Storage:** SharePoint as the system of record.
- **Reporting:** Power BI with row-level security, so each role sees only the records it is entitled to.
- **Deletion:** a designed path for removing review data.

The key decision was to enforce visibility in the reporting layer with row-level security and then prove it by testing each role, instead of relying on report sharing alone.

## 5. Workflow / Architecture Overview

Forms and apps → Power Automate routing → SharePoint storage → Power BI reporting with row-level security, plus a separate deletion path. See the [diagram](../diagrams/performance-review-platform-architecture.md).

## 6. Governance, Privacy, and Controls

- Role-based visibility in reporting, enforced by row-level security.
- A deletion path so review data does not remain indefinitely.

## 7. Testing and Release Readiness

- Test plans covering the review workflow from input to reporting.
- Row-level-security tests, checking what each role can and cannot see.
- A test of the deletion path.
- Documentation and a production handoff.

## 8. Outcome

Launched to production for 60 employees, with access rules verified by testing and the system documented and handed off.

## 9. What I Would Improve or Explore Next

Add a short regression test run before each review cycle, so access rules are re-checked whenever the reports change.

## 10. Public-Safe Disclosure

This case study is intentionally anonymized. It describes the workflow design, delivery approach, and governance considerations without disclosing confidential business information, internal URLs, personal data, source exports, or proprietary configurations.

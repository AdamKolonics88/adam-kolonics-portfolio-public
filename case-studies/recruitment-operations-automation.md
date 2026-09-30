# Recruitment Operations Automation

**Tools:** Jira workflows and automation rules, Power Apps, Power Automate, Microsoft 365
**Outcome:** estimated 15 hours per week of manual coordination saved
**Diagram:** [architecture](../diagrams/recruitment-operations-automation-architecture.md)

## 1. Context

Recruiters handled recurring candidate coordination manually, including application intake, scheduling, reminders, and offer preparation. As hiring activity increased, the coordination load increased with it.

## 2. Business Problem

Manual coordination took recruiter time and made timely status visibility harder to maintain. Candidate records are personal data, so the process also needed defined rules for how long data is kept and when it is deleted.

## 3. My Role and Ownership

I designed and built the workflow, wrote the requirements, configured the automations, tested the build, documented it, and handed it over to the recruiting team.

## 4. Solution Design

- **Intake:** one structured intake point, so every candidate record starts with the same information.
- **Status-driven routing:** each candidate moves through defined Jira workflow states. A recruiter changes the status; the automation rules and Power Automate flows then run the next coordination step.
- **Interview scheduling and reminders:** generated from the workflow and sent through Microsoft 365.
- **Offers:** generated and delivered as a workflow step instead of being assembled by hand.
- **Candidate-data lifecycle:** retention and deletion rules designed in from the start under GDPR.

The main design decision was to automate coordination, not judgment. Recruiters and hiring managers make every status decision; the workflow handles what follows.

## 5. Workflow / Architecture Overview

Intake → Jira workflow states → automated scheduling, reminders, and notifications → offer generation and delivery → retention and deletion. See the [diagram](../diagrams/recruitment-operations-automation-architecture.md).

## 6. Governance, Privacy, and Controls

- Retention and deletion rules for candidate data, set as part of the workflow rather than left to manual cleanup.
- Workflow states show where each candidate stands at any point.

## 7. Testing and Release Readiness

I tested the workflow states, transitions, and automated steps against written requirements before the team started using it, and documented how to operate it.

## 8. Outcome

The recruiting team moved candidate coordination from manual follow-up to a status-driven workflow. Estimated saving: about 15 hours per week of manual coordination.

## 9. What I Would Improve or Explore Next

Track time between workflow states so the time saving can be measured directly instead of estimated.

## 10. Public-Safe Disclosure

This case study is intentionally anonymized. It describes the workflow design, delivery approach, and governance considerations without disclosing confidential business information, internal URLs, personal data, source exports, or proprietary configurations.

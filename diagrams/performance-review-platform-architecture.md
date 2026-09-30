# Performance Review Platform — Architecture

Conceptual view only. No real forms, data, ratings, dashboards, or configuration are shown.

```mermaid
flowchart LR
    A[Structured Input<br/>forms and apps] --> B[Workflow Orchestration<br/>routing and notifications]
    B --> C[(Secure Data Store)]
    C --> D[Reporting<br/>row-level security]
    C --> E[Data Deletion<br/>privacy-aware lifecycle]
    T[[Workflow tests and<br/>row-level-security tests]] -.-> D
```

**Access control:** each role sees only its permitted records, enforced by row-level security and checked by role-by-role tests.
**Privacy:** review data has a designed deletion path.

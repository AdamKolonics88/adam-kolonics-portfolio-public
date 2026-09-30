# Recruitment Operations Automation — Architecture

Conceptual view only. No real systems, identifiers, fields, or rules are shown.

```mermaid
flowchart LR
    A[Candidate Intake] --> B[Workflow Orchestration<br/>status-driven routing]
    B --> C[Scheduling / Notifications<br/>interviews and reminders]
    B --> D[Offer Generation and Delivery]
    R{{Recruiter / hiring manager<br/>decides status changes}} --> B
    B --> E[Candidate-Data Lifecycle<br/>GDPR retention and deletion]
```

**Control point:** a recruiter or hiring manager changes each status; automation runs the coordination that follows.
**Privacy:** candidate data follows defined retention and deletion rules.

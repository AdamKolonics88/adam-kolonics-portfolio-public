# Automated AI Daily News Digest — Architecture

Conceptual view only. No real sources, keys, recipients, or logs are shown.

```mermaid
flowchart LR
    S[Scheduled Run] --> A[Collect Stories<br/>selected sources]
    A --> B[Rank Stories]
    B --> C[Source-Grounded Summaries<br/>LLM]
    C --> D{Already sent today?}
    D -- no --> E[Send Daily Digest]
    D -- yes --> X[Skip: idempotent send]
    M[Catch-up schedule] -. missed run .-> S
    T[[Automated tests]] -.-> D
```

**Delivery guards:** idempotent sends block a second send for the same day; catch-up scheduling re-runs a missed day; automated tests cover both.
**Grounding:** summaries are written from the source articles.

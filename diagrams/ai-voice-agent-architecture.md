# AI Voice Agent for Facility Operations — Architecture (In development)

Conceptual view only. No real work orders, vendors, numbers, endpoints, or accounts are shown.

```mermaid
flowchart LR
    A[Open Work Orders<br/>read-only integration] --> B[Call Orchestration]
    B --> C[Voice Agent<br/>telephony + voice AI]
    C --> D[Vendor Call<br/>ETA, access, parts, closeout]
    D --> E[Structured Extraction<br/>call outcome]
    E --> F{{Human Review}}
    F --> G[Action by a person]
    E -. unclear answer, passed as-is .-> F
```

**Data boundary:** work orders are read only; nothing is written back.
**Control point:** every structured outcome goes to a person; an unclear answer is passed on as unclear.
**Status:** in development.

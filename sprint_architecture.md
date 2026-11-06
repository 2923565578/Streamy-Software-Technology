```mermaid
---
title: Streamy Sprint Board Execution Lifecycle
---
flowchart TD
    subgraph Backlog [1. Backlog / Todo Pool]
        T1[Issue #1: Model Behavior Flow]
        T2[Issue #2: Draft Structural Class Maps]
        T3[Issue #3: Design Relational Storage]
        T4[Issue #4: Compile Python Skeletons]
    end

    subgraph ActiveSprint [2. Active Sprint / In Progress]
        Active["Active Developer Sprint Work"]
    end

    subgraph VerifiedDone [3. Done / Merged Production]
        Merged["Merged Base Code & Docs synced"]
    end

    T1 -->|Pick Task| Active
    Active -->|Code Review PR Approved| Merged
```
# Streamy Video Streaming Backend Platform

Software Technology Course Laboratory Node

- **Student Identity:** [XU HAOJIE]
- **Neptun System Code:** [DTR5N0]
- **Course Section Reference:** GEIAL314-B2a

## Workspace Environment Architecture

The diagram below maps out how our development environment connects local code authoring to remote version tracking, using a **Diagrams-as-Code** design pipeline.

```mermaid
---
title: Streamy Production Architecture Proof
---
flowchart TD
    UserNode["💻 Workstation Client <br> (Terminal CLI / Web Browser)"]
    LiveSandbox{"☁️ Cloud Sandbox <br> (mermaid.live)"}
    LocalIDE["🧩 VS Code IDE <br> (Markdown Preview Extension)"]
    GitStage["📦 Local Git Index <br> (Staging Ledger)"]
    RemoteHub["🐙 GitHub Remote Cloud <br> (Streamy Repository Workspace)"]

    UserNode -- 1. Sandbox Syntax --> LiveSandbox
    LiveSandbox -- 2. Verified Block Migration --> LocalIDE
    LocalIDE -- 3. git add CLI Operations --> GitStage
    GitStage -- 4. git push Pipeline Push --> RemoteHub
```

## Domain Model - UML Class Diagram

```mermaid
classDiagram
    Title -- Genre
    Title *-- Season
    Title *-- Review
    Title o-- Actor
    Season *-- Episode
```

## Streamy Application Engineering Development Lifecycle

为保证 **Streamy** 实现周期内的系统化跟踪，我们的开发者流水线遵循如下结构化迭代门禁审查框架。

```mermaid
---
title: Streamy Iterative SDLC Blueprint
---
flowchart TD
    subgraph SpecPhase ["1. Requirements Specification Block"]
        A["Inception Abstract Created"] --> B["SRs Requirements Compiling"]
    end

    subgraph DesignPhase ["2. UML Architectural Modeling"]
        B --> C["Draft System Border Graphs"]
        C --> D["Construct Advanced Class Models"]
    end

    subgraph ValidationGate ["3. Verification Gatekeeper Loop"]
        D --> E{"Does Architecture Match Code Specs?"}
        E -- "No: Refactor Blueprint" --> B
    end

    subgraph ProductionPhase ["4. Python Construction Layer"]
        E -- "Yes: Pass Gate" --> F["Compile Python Class Skeletons"]
        F --> G["Implement Internal Class Logic"]
    end

    classDef decisionStyle fill:#f9f,stroke:#333,stroke-width:2px;
    class E decisionStyle
```

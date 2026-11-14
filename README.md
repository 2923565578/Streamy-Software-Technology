# Project Overview

This repository uses Mermaid for architecture and domain documentation.

## System Architecture

```mermaid
flowchart LR
  Client[Web Client] -->|HTTPS| API[API Gateway]
  API --> Service[Listing Service]
  Service --> DB[(Database)]
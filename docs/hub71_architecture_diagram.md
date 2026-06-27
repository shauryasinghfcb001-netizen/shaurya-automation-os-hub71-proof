# Hub71 Architecture Diagram

_Current state: working internal system, being productized next._

```mermaid
flowchart LR
    A[Obsidian / JarvisMemory<br/>Local project memory] --> B[Obsidian Brain Connector<br/>Source-backed snapshot]
    B --> C[Brain Router<br/>Goal -> pipeline, worker, tools, next action]
    C --> D[Worker Prompt Generator<br/>Worker-specific handoff prompts]

    D --> E[Hub71 Submission Operator<br/>Submission packet and draft]
    D --> F[GitHub Proof Builder<br/>README, proof index, checklists]
    D --> G[Tool Connection Proof<br/>READY vs PARTIAL tools]
    D --> H[Web Command Center<br/>Local proof control panel]

    E --> I[Proof reports<br/>hub71_submission_index.md<br/>hub71_submission_final.md]
    F --> J[Proof folder<br/>proof/hub71]
    G --> K[Tool readiness report<br/>tool_connection_proof.md]
    H --> L[Local demo surface<br/>open/run proof files]

    subgraph Ready_Workers[READY workers/tools]
        R1[Claude / Claude Code]
        R2[Codex]
        R3[Playwright]
        R4[Ollama]
        R5[Web Command Center]
    end

    subgraph Partial_Future[PARTIAL / future tools]
        P1[OpenClaw - partial]
        P2[Hermes - partial]
        P3[n8n - partial]
    end

    D -.uses ready workers.-> Ready_Workers
    G -.tracks limits.-> Partial_Future
```

## Plain-English Architecture
- Obsidian / JarvisMemory is the local memory source.
- The Obsidian Brain Connector converts memory into a source-backed snapshot.
- Brain Router chooses the right pipeline, worker, tools, and next action for the goal.
- Worker Prompt Generator creates the handoff prompt.
- Operators turn that handoff into concrete artifacts: Hub71 submission copy, GitHub proof files, tool readiness reports, and demo checklists.
- Web Command Center is the local control panel for opening and running proof workflows.

## Tool Readiness
- READY: Claude / Claude Code, Codex, Ollama, Playwright, Obsidian/JarvisMemory, Web Command Center.
- PARTIAL: OpenClaw, Hermes, n8n.
- RUDRA: early project proof only, not the main company.

## Claim Boundary
This architecture represents a working internal system. It does not claim revenue, customers, public SaaS launch, external integrations, or fully automated partial tools.

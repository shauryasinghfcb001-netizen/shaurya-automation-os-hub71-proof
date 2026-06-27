# SHAURYA Automation OS Architecture

```mermaid
flowchart LR
    A[Obsidian / JarvisMemory<br/>Local project memory] --> B[Obsidian Brain Connector<br/>Source-backed snapshot]
    B --> C[Brain Router<br/>Goal -> pipeline, worker, tools, next action]
    C --> D[Worker Prompt Generator<br/>Worker-specific handoff prompts]

    D --> E[Hub71 Submission Operator]
    D --> F[GitHub Proof Builder]
    D --> G[Tool Connection Proof]
    D --> H[Web Command Center]

    E --> I[Submission copy and packet]
    F --> J[Proof index, README draft, demo checklists]
    G --> K[READY / PARTIAL tool status]
    H --> L[Local demo control panel]

    subgraph Ready[READY tools]
        Claude[Claude / Claude Code]
        Codex[Codex]
        Playwright[Playwright]
        Ollama[Ollama]
        WebCC[Web Command Center]
    end

    subgraph Partial[PARTIAL / future tools]
        OpenClaw[OpenClaw - partial]
        Hermes[Hermes - partial]
        N8N[n8n - partial]
    end

    D -.assigns ready work.-> Ready
    G -.documents limits.-> Partial
```

## Summary
SHAURYA Automation OS is a working internal operator system. It reads trusted local context, routes a goal to the right workflow, generates worker prompts, checks tool readiness, and produces proof reports.

## Current Proof Boundary
- Working today: Brain Router, Worker Prompt Generator, Tool Connection Proof, Hub71 Submission Operator, GitHub Proof Builder, Web Command Center.
- Ready tools: Claude / Claude Code, Codex, Ollama, Playwright, Obsidian/JarvisMemory, Web Command Center.
- Partial/future tools: OpenClaw, Hermes, n8n.
- RUDRA is early project proof only, not the main company.
- No revenue, customers, public SaaS launch, GitHub push, or Hub71 acceptance is claimed.

# Applied AI Engineer 

> Building reliable, verifiable, and energy-efficient AI: from cognitive architectures and continual learning to production systems for business and medicine.

**Contents:** [Applied Solutions for Business](#applied-solutions-for-business) · [AI in Software Development](#ai-in-software-development) · [Technology Stack](#technology-stack) · 

## Applied Solutions for Business

Alongside research, I design and deploy production AI systems where reliability, data isolation, and predictable behavior matter more than prototyping speed.

### 1. B2B SaaS Architecture and Data Isolation

- Design of multi-tenant platforms with strict tenant isolation: Row-Level Security (RLS) in PostgreSQL, schema- or database-per-tenant, and tenant-aware context at every application layer.
- Isolation at the AI-component level: separate collections and namespaces in vector stores (Qdrant, ChromaDB), tenant-ID filtering in retrieval, and protection against cross-tenant leakage through prompts and context.
- Role- and attribute-based access control (RBAC/ABAC), audit logs, secrets management, and compliance with personal-data protection frameworks (GDPR, 152-FZ).

### 2. Reliability Patterns for Distributed Systems

- Transactional Outbox (PostgreSQL + Redis/Celery) for guaranteed event delivery without loss or duplication.
- API idempotency: idempotency keys, safe request retries, and handler deduplication.
- Fail-closed logic: if a security or verification check fails or its service is unavailable, the system rejects the operation instead of letting it through.
- Exponential backoff retries, circuit breakers, dead-letter queues, rate limiting, and graceful degradation.
- Saga pattern for long-running business transactions; asynchronous processing (asyncio, Celery) under heavy load.

### 3. Integrating AI into Business Processes

- Pre-project analysis: process audit, identifying tasks with measurable AI impact, ROI/TCO and risk assessment, and choosing between cloud APIs and local deployment.
- Enterprise RAG systems: search and Q&A over internal knowledge bases, documents, and regulations, with mandatory source attribution and epistemic halting (refusal to answer) when supporting evidence is lacking.
- Agentic automation: workflow orchestration (LangGraph, MCP), integration with CRM, ERP, ticketing systems, and internal APIs, maintaining human-in-the-loop for critical decisions.
- Document processing: structured data extraction (contracts, invoices, requests), classification, routing, and summarization.
- Guardrails: structured-output validation (JSON Schema, Pydantic), constrained generation, PII filtering, prompt-injection defenses, and output verification before action execution.

### 4. Model Fine-Tuning and Adaptation

- Fine-tuning open models (Llama-3, Qwen) for client domains: SFT, parameter-efficient methods (LoRA/QLoRA, PEFT), and preference alignment (DPO).
- Dataset preparation and curation: cleaning, deduplication, annotation, synthetic data generation, and train/test leakage control.
- Distillation of large models into compact ones to reduce inference cost and latency.
- Strategic adaptation: choosing between prompt engineering, RAG, or fine-tuning based on task complexity, data volume, and budget.

### 5. Operating AI Systems (LLMOps)

- Quality evaluation: custom evaluation sets, regression testing of prompts and models, factuality, and completeness metrics.
- Observability: request tracing, monitoring of cost, latency, and quality drift, alongside privacy-aware logging.
- Cost and performance optimization: model routing, caching, quantization (AWQ, GGUF), vLLM inference, and token-budget control.
- Deployment: Docker, CI/CD, and local/private environments for clients with strict data-security requirements.

## AI in Software Development

I study and apply agentic systems for programming, both as a method to raise engineering productivity and as a research subject in its own right: determining where autonomous agents are reliable and where human oversight remains strictly required.

- **Agentic development tools:** Hands-on work with Claude Code, OpenCode, OpenClaw, and similar CLI/IDE agents; comparative analysis of their capabilities, limitations, and failure modes.
- **Multi-agent coding systems:** Role separation (planner, implementer, reviewer, tester), parallel subagents on independent tasks, and orchestration via LangGraph and MCP.
- **Context engineering:** Designing instructions, specifications, and repository structures that allow an agent to operate reliably; context-window management, cross-session memory, and external tool integration via MCP servers.
- **Quality control of agent-written code:** Automated tests as acceptance criteria, static analysis, typing, property-based testing, diff review, isolated environments (Docker, sandboxes), and least-privilege principles for agents.
- **Measuring effectiveness:** Evaluating agents on realistic tasks (e.g., SWE-bench paradigms), tracking quality, cost, and the share of human corrections, while analyzing typical failures (hallucinated APIs, incomplete refactorings, silent regressions).
- **Security:** Defense against prompt injection via dependencies and documentation, command-execution control, and rigorous auditing of agent actions.

My research on intent-grounded verification of coding agents is described in [Current Active Research](#current-active-research) at the end of this document.

## Technology Stack

| Area | Tools and Methods |
|---|---|
| **Cognitive Architectures & Knowledge Representation** | ontologies and knowledge graphs, Datalog / Prolog. |
| **World Models & Agent Systems** | Active Inference, LangGraph, Model Context Protocol (MCP), multi-agent orchestration. |
| **Formal Verification** | Lean 4, Coq, SMT solvers (Z3); formal safety bounds and deterministic logic. |
| **Memory & Retrieval** | Neo4j, Qdrant, ChromaDB; semantic chunking modeled on consolidation of episodic into semantic memory; hybrid (graph + vector) retrieval. |
| **Deep Learning** | PyTorch, Hugging Face Transformers, PEFT/LoRA, Attention Residuals, neuromodulation-inspired models. |
| **Interpretability & Topology** | Sparse autoencoders (SAE), circuit discovery, activation patching, representation steering, persistent homology (TDA). |
| **Inference & Optimization** | vLLM, llama.cpp, quantization (BitsAndBytes, AWQ, GGUF), local deployment of Llama-3 / Qwen / Kimi. |
| **Cognitive Cybernetics** | Predictive coding, optimal control theory. |
| **Backend & Infrastructure** | Python 3 (asyncio), FastAPI, PostgreSQL, Redis, Celery, Docker. |
| **Research Practices** | Reproducible experiments (Weights & Biases / MLflow), data and configuration versioning, factuality and robustness benchmarks. |





---
> *"Solve intelligence, and then use that to solve everything else."* — Demis Hassabis.

<div align="center">
  <a href="mailto:твоя_почта@gmail.com">
    <img src="https://img.shields.io/badge/Email-778388?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
  </a>
  <a href="https://www.linkedin.com/in/твоя_ссылка/">
    <img src="https://img.shields.io/badge/LinkedIn-778388?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  <a href="https://orcid.org/my-orcid?orcid=0009-0007-2913-5960">
    <img src="https://img.shields.io/badge/ORCID-778388?style=for-the-badge&logo=orcid&logoColor=white" alt="ORCID" />
  </a>
</div>

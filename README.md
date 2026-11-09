# Applied AI Engineer & Researcher in Synthetic Cognitive Architectures

> Building reliable, verifiable and energy-efficient AI: from cognitive architectures and continual learning to production systems for business and medicine.

## Research Mission

My work focuses on designing next-generation cognitive architectures and overcoming the structural limitations of current large language models (LLMs). I regard hallucinations not as an acceptable error margin of generative systems, but as an architectural defect that must be eliminated at the level of model design. My engineering program is built around **Zero-Hallucination architectures**: systems whose outputs are reproducible and whose safety-critical claims are subject to formal verification.

A separate line of work concerns the problems of deep transformer networks: attention degradation with depth and the dilution of hidden states under PreNorm normalization (PreNorm dilution). These problems belong to the same family as those addressed in the Attention Residuals line of work ([paper link]).

As an independent researcher, I study **biomimetic computational models** capable of continual learning without catastrophic forgetting. The ultimate goal is energy-efficient architectures that reproduce the mechanisms of hippocampal systems memory consolidation, in which new experience structurally reshapes the network topology instead of being merely cached in external vector stores.

## Key Research Directions

- **Continual learning and plasticity:** mitigating catastrophic forgetting (EWC, replay mechanisms, modular and sparse architectures), Complementary Learning Systems theory, Hebbian plasticity.
- **Neuro-symbolic AI:** hybrid systems combining statistical models with symbolic reasoning, ontologies and logic programming.
- **Reliability and verifiability of outputs:** constrained generation, source attribution, uncertainty quantification, calibration and conformal prediction.
- **Interpretability:** mechanistic interpretability of transformers, analysis of residual stream dynamics and hidden-state propagation across depth.
- **Agent systems and world models:** Active Inference, predictive models of the environment, dynamic modulation of agent hyperparameters as a computational analogue of neuromodulation.

### Depth-wise Information Flow in Deep Transformers

I work on the problem class addressed by **Attention Residuals**: how information and gradients are aggregated across the depth of a transformer.

**The problem.** Standard residual connections with PreNorm accumulate all layer outputs with fixed unit weights. Hidden-state magnitude then grows as O(L) with depth, so each layer's relative contribution is progressively diluted (*PreNorm dilution*): early-layer information is buried and cannot be retrieved selectively, and deeper layers are forced to learn ever-larger outputs to stay influential.

**The reference approach.** Attention Residuals replace fixed accumulation with softmax attention over preceding layer outputs, using one learned pseudo-query per layer. The block variant reduces memory and communication from O(Ld) to O(Nd) by attending over block-level summaries (about 8 blocks recover most of the gain). In the paper, this matches the loss of a baseline trained with 1.25× more compute, keeps output magnitudes bounded across depth, and distributes gradients more uniformly.

**My focus:**
- Analysis of hidden-state growth, gradient distribution and depth-wise attention patterns (including depth-wise attention sinks) in deep transformers.
- Interaction of depth-wise aggregation with low-bit quantization (AWQ, GGUF): how bounded activation magnitudes affect quantization error and activation outliers.
- Memory-efficient variants of depth-wise attention, including finer-grained blocking and linear-complexity alternatives.
- Connections to continual learning: stability of selective cross-layer retrieval under sequential task adaptation.

Reference: Kimi Team, *Attention Residuals*, arXiv:2603.15031 ([paper](https://arxiv.org/abs/2603.15031), [code](https://github.com/MoonshotAI/Attention-Residuals)).

## AI in Medicine (Research Direction)

I study the potential and the limits of AI in medicine. The cost of error here is maximal, so this direction naturally extends my program on reliable and verifiable architectures.

- **Clinical decision support:** systems grounded in verifiable sources (clinical guidelines, scientific literature), with mandatory attribution and refusal to answer when evidence is insufficient.
- **Medical RAG and knowledge graphs:** integration of biomedical ontologies (SNOMED CT, ICD, MeSH, UMLS) with graph and vector stores for precise and explainable retrieval.
- **Clinical text processing:** entity and relation extraction from discharge summaries and protocols, structuring of unstructured records, de-identification of personal data.
- **Reliability and safety:** uncertainty estimation, calibration, evaluation of hallucination robustness on medical benchmarks, human-in-the-loop for all clinically significant decisions.
- **Privacy and regulation:** local and isolated model deployment, HIPAA and GDPR requirements, approaches to validating software as a medical device (SaMD).
- **Multimodal data and continual learning:** adapting models to new clinical data without catastrophic forgetting.

> Research materials are not medical advice and are not intended for clinical use.

## Applied Solutions for Business

Alongside research, I design and deploy production AI systems where reliability, data isolation and predictable behavior matter more than prototyping speed.

### 1. B2B SaaS Architecture and Data Isolation
- Design of **multi-tenant** platforms with strict tenant isolation: Row-Level Security in PostgreSQL, schema- or database-per-tenant, tenant-aware context at every application layer.
- Isolation at the AI-component level: separate collections and namespaces in vector stores (Qdrant, ChromaDB), tenant-ID filtering in retrieval, protection against cross-tenant leakage through prompts and context.
- Role- and attribute-based access control (RBAC/ABAC), audit logs, secrets management, compliance with personal-data protection requirements (GDPR, Russian Federal Law 152-FZ).

### 2. Reliability Patterns for Distributed Systems
- **Transactional Outbox** (PostgreSQL + Redis/Celery) for guaranteed event delivery without loss or duplication.
- **API idempotency:** idempotency keys, safe request retries, handler deduplication.
- **Fail-closed logic:** if a security or verification check fails or its service is unavailable, the system rejects the operation instead of letting it through.
- Exponential backoff retries, circuit breakers, dead-letter queues, rate limiting, graceful degradation.
- Saga pattern for long-running business transactions; asynchronous processing (asyncio, Celery) under load.

### 3. Integrating AI into Business Processes
- **Pre-project analysis:** process audit, identifying tasks with measurable AI impact, ROI/TCO and risk assessment, choosing between cloud APIs and local deployment.
- **Enterprise RAG systems:** search and answering over internal knowledge bases, documents and regulations, with mandatory source attribution and refusal to answer when supporting evidence is lacking.
- **Agentic automation:** workflow orchestration (LangGraph, MCP), integration with CRM, ERP, ticketing systems and internal APIs, human-in-the-loop for critical decisions.
- **Document processing:** structured data extraction (contracts, invoices, requests), classification and routing of inquiries, summarization.
- **Guardrails:** structured-output validation (JSON Schema, Pydantic), constrained generation, PII filtering, prompt-injection defenses, output verification before executing actions.

### 4. Model Fine-Tuning and Adaptation
- Fine-tuning open models (Llama-3, Qwen) for a client's domain: SFT, parameter-efficient methods (LoRA/QLoRA, PEFT), preference alignment (DPO).
- Dataset preparation and curation: cleaning, deduplication, annotation, synthetic data generation, train/test leakage control.
- Distillation of large models into compact ones to reduce inference cost and latency.
- Choosing an adaptation strategy (prompt engineering, RAG or fine-tuning) based on the task, data volume and budget.

### 5. Operating AI Systems (LLMOps)
- **Quality evaluation:** custom evaluation sets, regression testing of prompts and models, factuality and completeness metrics.
- **Observability:** request tracing, monitoring of cost, latency and quality drift, privacy-aware logging.
- **Cost and performance optimization:** model routing, caching, quantization (AWQ, GGUF), vLLM inference, token-budget control.
- **Deployment:** Docker, CI/CD, local and private environments for clients with strict data-security requirements.

## AI in Software Development

I study and apply agentic systems for programming, both as a way to raise engineering productivity and as a research subject in its own right: where autonomous agents are reliable and where human oversight is required.

- **Agentic development tools:** hands-on work with Claude Code, OpenCode, OpenClaw and similar CLI/IDE agents; comparative analysis of their capabilities, limitations and failure modes.
- **Multi-agent coding systems:** role separation (planner, implementer, reviewer, tester), parallel subagents on independent tasks, orchestration via LangGraph and MCP.
- **Context engineering:** designing instructions, specifications and repository structure that let an agent work reliably; context-window management, cross-session memory, external tools via MCP servers.
- **Quality control of agent-written code:** automated tests as acceptance criteria, static analysis, typing, property-based testing, diff review, isolated environments (Docker, sandboxes) and least-privilege principles for agents.
- **Measuring effectiveness:** evaluating agents on realistic tasks (in the spirit of SWE-bench), tracking quality, cost and the share of human corrections, analyzing typical failures: hallucinated APIs, incomplete refactorings, silent regressions.
- **Security:** defense against prompt injection via dependencies and documentation, command-execution control, auditing of agent actions.

## Looking Ahead: Neuromorphic Systems

My long-term goal is an energy-efficient, truly autonomous synthetic intelligence. Today's LLMs are trained and served on clusters at megawatt scale, whereas the biological brain solves general-intelligence tasks on the order of 20 W. Closing this gap defines the next stage of my research: from algorithms to the computational substrate (neuromorphic platforms and hardware co-design).

### Neuromorphic Computing and Hardware Acceleration
- **Spiking Neural Networks (SNN):** event-driven sparse computation; training with surrogate gradients and local plasticity rules (STDP).
- **Platforms and frameworks:** Intel Loihi / Lava, SpiNNaker, BrainScaleS, snnTorch, Nengo, Brian2.
- **Accelerators and HPC:** CUDA, FPGA, in-memory computing, memristive architectures.
### Compute-in-Memory and Physics-Based Computing

I also study analog compute-in-memory (CIM) as a researcher: an artificial neural network can be embedded directly into the memory array, with the physics of the device itself performing part of the computation, instead of shuttling data between memory and processor as in the von Neumann architecture.

**Case study: neural dynamical systems on phase-change memristors** (Peking University and Chinese Academy of Sciences, *Science*, 2026). A neural dynamical system (NDS) couples a neural network with a continuous-time differential-equation solver, and was demonstrated on cortical surface reconstruction.
- Network weights are mapped to the multilevel conductance states of phase-change memory, so multiply-accumulate operations run inside the array.
- Conductance drift, normally treated as a device defect, is harnessed as a physical implementation of the solver's adaptive step-size search.
- Reported results: 2.12 ms latency per integration iteration at an error tolerance of 10⁻⁷; end-to-end reconstruction 50–478× faster than an NVIDIA A100 GPU; 3.8–36× faster and 12–25× lower power than prior NDS hardware.

**Research interests:** turning device non-idealities (drift, noise, variability) into computational resources; hardware-aware training of neural ODEs; real-time modeling of physical manifolds; potential relevance for medical imaging and robotics.
- **Efficiency metrics:** energy per operation and per inference, activation sparsity, comparison with dense transformer models on comparable tasks.

### Systems Programming
- **Rust and modern C++ (17/20)** for high-performance computing, low-level inference optimization and memory-safe code without the overhead of interpreted languages.
- Integration with the Python ecosystem: PyO3, pybind11, custom CUDA kernels, Triton.

### Cognitive Cybernetics
- **Predictive coding** and the free-energy principle as a computational basis for learning beyond classical backpropagation.
- **Optimal control theory:** LQR, model predictive control, links to reinforcement learning and Active Inference.
- Synthesis: hierarchical predictive world models implemented on a neuromorphic substrate.

### Planned Practical Work
| Direction | Deliverable |
|---|---|
| SNN | Spiking network implemented and trained with snnTorch; energy/accuracy comparison against an ANN counterpart |
| Predictive coding | Reproduction of a hierarchical predictive network in PyTorch; published code and report |
| Rust / C++ | Custom high-performance kernel (e.g., quantized matrix multiplication) with a benchmark against PyTorch |

## Technology Stack

| Area | Tools and methods |
|---|---|
| **Cognitive architectures and knowledge representation** | OpenCog, AtomSpace (hypergraph knowledge representation), ontologies and knowledge graphs, Datalog / Prolog |
| **World models and agent systems** | Active Inference, LangGraph, Model Context Protocol (MCP), multi-agent orchestration |
| **Formal verification** | Lean 4, Coq, SMT solvers (Z3); formal safety bounds and deterministic logic |
| **Memory and retrieval** | Neo4j, Qdrant, ChromaDB; semantic chunking modeled on consolidation of episodic into semantic memory; hybrid (graph + vector) retrieval |
| **Deep learning** | PyTorch, Hugging Face Transformers, PEFT/LoRA, Attention Residuals, neuromodulation-inspired models |
| **Inference and optimization** | vLLM, llama.cpp, quantization (BitsAndBytes, AWQ, GGUF), local deployment of Llama-3 / Qwen / Kimi |
| **Neuromorphic and HPC** | CUDA, FPGA, SNN (snnTorch, Nengo, Brian2), Rust, C++17/20 |
| **Cognitive cybernetics** | Predictive coding, optimal control theory |
| **Backend and infrastructure** | Python 3 (asyncio), FastAPI, PostgreSQL, Redis, Celery, Docker |
| **Research practices** | Reproducible experiments (Weights & Biases / MLflow), data and configuration versioning, factuality and robustness benchmarks |

## Principles

1. Reproducibility and measurability of results.
2. Formal guarantees where possible; empirical evaluation where necessary.
3. Architectural solutions instead of patches over symptoms.

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

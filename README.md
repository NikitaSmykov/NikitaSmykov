# Applied AI Engineer & AI Researcher

> Building reliable, verifiable, and energy-efficient AI: from cognitive architectures and continual learning to production systems for business and medicine.

**Contents:** [Applied Solutions for Business](#applied-solutions-for-business) · [AI in Software Development](#ai-in-software-development) · [Technology Stack](#technology-stack) · [Research & Science](#research--science)

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
| **Cognitive Architectures & Knowledge Representation** | OpenCog, AtomSpace (hypergraph knowledge representation), ontologies and knowledge graphs, Datalog / Prolog. |
| **World Models & Agent Systems** | Active Inference, LangGraph, Model Context Protocol (MCP), multi-agent orchestration. |
| **Formal Verification** | Lean 4, Coq, SMT solvers (Z3); formal safety bounds and deterministic logic. |
| **Memory & Retrieval** | Neo4j, Qdrant, ChromaDB; semantic chunking modeled on consolidation of episodic into semantic memory; hybrid (graph + vector) retrieval. |
| **Deep Learning** | PyTorch, Hugging Face Transformers, PEFT/LoRA, Attention Residuals, neuromodulation-inspired models. |
| **Interpretability & Topology** | Sparse autoencoders (SAE), circuit discovery, activation patching, representation steering, persistent homology (TDA). |
| **Inference & Optimization** | vLLM, llama.cpp, quantization (BitsAndBytes, AWQ, GGUF), local deployment of Llama-3 / Qwen / Kimi. |
| **Neuromorphic & HPC** | CUDA, FPGA, SNN (snnTorch, Nengo, Brian2), phase-change memristors / compute-in-memory, Rust, C++17/20. |
| **Cognitive Cybernetics** | Predictive coding, optimal control theory. |
| **Backend & Infrastructure** | Python 3 (asyncio), FastAPI, PostgreSQL, Redis, Celery, Docker. |
| **Research Practices** | Reproducible experiments (Weights & Biases / MLflow), data and configuration versioning, factuality and robustness benchmarks. |

---

## Research & Science

### Research Mission

My work focuses on designing next-generation cognitive architectures and overcoming the structural limitations of current large language models (LLMs). I regard hallucinations not as an acceptable error margin of generative systems, but as an architectural defect that must be eliminated at the level of model design. My engineering program is built around **Zero-Hallucination architectures**: systems whose outputs are reproducible and whose safety-critical claims are subject to formal verification.

A separate line of work concerns the problems of deep transformer networks: attention degradation with depth and the dilution of hidden states under PreNorm normalization (PreNorm dilution). These problems belong to the same family as those addressed in the *Attention Residuals* line of work (arXiv:2603.15031).

As an independent researcher, I study biomimetic computational models capable of continual learning without catastrophic forgetting. The ultimate goal is energy-efficient architectures that reproduce the mechanisms of hippocampal memory consolidation, in which new experiences structurally reshape the network topology instead of being merely cached in external vector stores.

### Core Research Mission: Zero-Hallucination Architectures

My central research mission is the elimination of hallucinations at the architectural level, creating systems capable of deterministic, verifiable reasoning.

**Measurable objective:** Formal results indicate that hallucination cannot be eliminated entirely for general computable models (Xu et al., 2024). The measurable target is therefore a bounded, calibrated error rate: selective risk at a given coverage (AURC), with abstention triggered by internal signals rather than post-hoc text checks.

**Working hypothesis (Latent Space Voids):** I hypothesize that the root cause of hallucinations lies in the latent voids of neural networks—regions of the representation space that training data never covered, where model behavior is undefined and an inhabited manifold gives way to statistical noise. I study how to resolve this inside the weights themselves, rather than by extensively scaling data or relying solely on external "prostheses."

**The role of retrieval:** External retrieval (RAG, vector databases) is a highly valuable engineering tool, and I actively use it in production systems. However, it routes queries around voids instead of removing them. A fundamental solution requires changing the mathematics of the latent space so that the feature space forms a continuous manifold with well-defined boundaries, allowing the model to detect when it has left it.

### Research Directions

- **Computational topology of representations:** Applying persistent homology and related TDA (Topological Data Analysis) tools to activation point clouds to quantify connectivity, holes, and the coverage of learned manifolds across layers.
- **Rethinking attention and depth-wise flow:** Exploring architectural mechanisms that keep representations well-conditioned in deep networks, including Attention Residuals as a candidate remedy for depth-wise dilution.
- **Mechanistic interpretability:** Leveraging sparse autoencoders (SAE) and circuit discovery to untangle polysemantic neurons, map the boundaries of learned concepts, and locate regions where deceptive behavior (e.g., sleeper-agent backdoors) can hide—going beyond behavioral testing such as RLHF.
- **Sleep-inspired consolidation:** Investigating wake–sleep cycles with synthetic "dreaming," following the SLEEP framework (Behrouz et al., Google Research, 2026; arXiv:2606.03979). I explore extending this idea to deliberately target low-density regions between known concepts, ensuring new knowledge interpolates continuously instead of overwriting existing manifolds or scattering into empty space.
- **Uncertainty at the boundary:** A model that can detect it is outside the learned manifold should deterministically halt generation or request data instead of producing statistical noise. This is the route I pursue toward Zero-Hallucination behavior.

### Why It Matters

- **Reliability:** Calibrated abstention in uncovered regions instead of confident hallucination.
- **Safety:** Mapping the latent space at the level of internal computations as a structural complement to behavioral red-teaming against jailbreaks and backdoors.
- **Out-of-distribution generalization:** Investigating whether the continuity and coverage of the latent space enables principled extrapolation.
- **Data and energy efficiency:** Testing whether architectural void-reduction allows highly capable models to be trained on smaller, curated datasets, which in turn fits energy-efficient hardware such as compute-in-memory (CIM).
- **Engineering-grade AI:** In physical design, a failure inside a void is not an amusing hallucination but a catastrophic structural defect. I use physics-grounded evaluation, where deterministic solvers (CalculiX, Gmsh) grade outputs pass/fail (e.g., RWE-Bench), as the standard for trustworthy AI in engineering.

### How I Plan to Measure It

- Define a void operationally: for layer-ℓ activations h_ℓ(x), a void score v_ℓ(x) equal to the distance to the k-th nearest neighbor among training-time activations (after whitening); alternatives include Mahalanobis distance, uncovered SAE feature regions, and topological holes in persistent-homology diagrams.
- Compare void statistics across layers and architectures (standard residuals vs. Attention Residuals).
- Test whether void statistics predict hallucination rates and failure under distribution shift, beyond logit-entropy and simple kNN/Mahalanobis baselines. Negative results will be reported.

### Key Research Directions

- **Continual learning and plasticity:** Mitigating catastrophic forgetting (EWC, replay mechanisms, modular and sparse architectures), Complementary Learning Systems theory, Hebbian plasticity.
- **Neuro-symbolic AI:** Hybrid systems combining statistical models with symbolic reasoning, ontologies, and logic programming.
- **Reliability and verifiability of outputs:** Constrained generation, source attribution, uncertainty quantification, calibration, and conformal prediction.
- **Interpretability:** Mechanistic interpretability of transformers, analysis of residual stream dynamics, and hidden-state propagation across depth.
- **Agent systems and world models:** Active Inference, predictive models of the environment, dynamic modulation of agent hyperparameters as a computational analogue of neuromodulation.

### Depth-wise Information Flow in Deep Transformers

I work on the problem class addressed by Attention Residuals: how information and gradients are aggregated across the depth of a transformer.

**The problem:** Standard residual connections with PreNorm accumulate all layer outputs with fixed unit weights. Hidden-state magnitude then grows as O(L) with depth, causing each layer's relative contribution to be progressively diluted (PreNorm dilution). Early-layer information is buried and cannot be retrieved selectively, while deeper layers are forced to learn ever-larger outputs to stay influential.

**The reference approach:** Attention Residuals replace fixed accumulation with softmax attention over preceding layer outputs, using one learned pseudo-query per layer. The block variant reduces memory and communication from O(Ld) to O(Nd) by attending over block-level summaries (about 8 blocks recover most of the gain). In the paper, this matches the loss of a baseline trained with 1.25× more compute, keeps output magnitudes bounded across depth, and distributes gradients more uniformly.

**My focus:**

- Analysis of hidden-state growth, gradient distribution, and depth-wise attention patterns (including depth-wise attention sinks) in deep transformers.
- Interaction of depth-wise aggregation with low-bit quantization (AWQ, GGUF): how bounded activation magnitudes affect quantization error and activation outliers.
- Memory-efficient variants of depth-wise attention, including finer-grained blocking and linear-complexity alternatives.
- Connections to continual learning: stability of selective cross-layer retrieval under sequential task adaptation. *(Reference: Kimi Team, Attention Residuals, arXiv:2603.15031)*

### Current Active Research

*Status: research design stage. The projects below are hypotheses with pre-specified failure criteria; no empirical results have been obtained yet.*

#### 1. Familiar Is Not Known: Knowledge-Sufficiency Gating of Refusal

**Background.** Interpretability work suggests that models carry a default "decline to answer" pathway that is suppressed when an entity is recognized. Hallucination can then arise when recognition fires without sufficient underlying knowledge: a void camouflaged by surface familiarity.

**Hypothesis.** Familiarity and knowledge sufficiency are separable signals. A small adapter that estimates *knowledge sufficiency* (rather than entity recognition) and causally gates the refusal pathway will reduce hallucination at a given coverage better than post-hoc probe-and-threshold baselines.

**Design.** Open models with available interpretability tooling (e.g., Gemma 2 2B with sparse-autoencoder/transcoder suites, Qwen); PopQA stratified by entity popularity; baseline: linear probe on mid-layer activations plus a threshold; metric: area under the risk–coverage curve (AURC).

**Failure criterion.** If the adapter does not beat the probe-plus-threshold baseline on AURC, the architectural coupling adds nothing, and I will report the negative result.

#### 2. Intent-Grounded Engineering: Overcoming Self-Reinforcing Hallucinations in Coding Agents

**The failure mode.** A coding agent misreads the task, writes tests that encode the same misreading, passes them, and confidently reports success. Execution feedback (compilers, test runners — the signal behind RLCEF-style training) cannot correct this when verification is derived from the agent's own interpretation: the outcome then depends on the true intent only through that interpretation, so the reward carries no information about whether the interpretation was right. Externally authored verifiers do carry that information, but sparsely and late, after the interpretation has already been committed.

**Working hypothesis.** The error lies in intent grounding rather than in code generation, and it can be addressed before the first execution-affecting action: by making verification statistically independent of the agent's reading, by locating and intervening on the representation of intent in the residual stream, and by rewarding evidence-gathering that resolves ambiguity.

**Research lines**

1. **Decorrelated verification.** Formalize a lower bound on false-success probability in terms of the correlation between interpretation errors of the code-writing and test-writing channels; measure it across model pairs and information partitions (e.g., a tester that sees only the prompt and the environment).
   *Failure criterion:* if cross-family or information-partitioned testers do not reduce false success by at least 25% relative to same-model self-testing at equal compute, or measured error correlation stays at or above 0.9, the independence hypothesis is rejected.
2. **Intent subspace: probing and steering.** Test whether the model internally represents the correct constraint while acting on a wrong one (the coding analogue of "knows but acts otherwise"), using contrastive minimal-pair prompts, SAE features, and activation patching; track the decay of intent projection during generation and apply representation-level steering before execution.
   *Failure criterion:* probe AUROC below 0.65 or less than 0.05 above output-entropy and verbalized-confidence baselines; steering no better than norm-matched random directions; or more than 2 pp collateral loss on unambiguous tasks.
3. **Epistemic value over intent hypotheses.** An Active-Inference-style agent that, besides the pragmatic reward, is rewarded for information gain over behaviorally distinct interpretations, gathered through read-only environment probes (no user in the loop).
   *Failure criterion:* less than 3 pp pass@1 gain over an execution-reward-only baseline on held-out task families, or a gain that vanishes against random probing at equal call budget.

**Shared infrastructure.** An intent-labeled benchmark: terminal tasks with injected ambiguities and ground-truth intent, to be released with code. Experiments on open models (e.g., Qwen2.5-Coder).

**Builds on:** TACT (arXiv:2605.05980), Latent Programming Horizons in Coding Agents (arXiv:2607.05188), Ambig-SWE (arXiv:2502.13069), Ask or Assume (arXiv:2603.26233), information-gain clarification in LLM agents (arXiv:2606.03135).

<!--
Results (uncomment and fill in as soon as real artifacts exist):

### Results
- [Repo link]: probe baseline for knowledge sufficiency, Gemma 2 2B, PopQA: AURC [x] vs [y]
- [Repo link]: Block Attention Residuals on a small transformer: norm growth and gradients vs baseline
- [Repo link]: intent-labeled terminal tasks v0 ([N] tasks), baseline false-success rate [z]
-->

### Looking Ahead: Neuromorphic Systems

My long-term goal is an energy-efficient, truly autonomous synthetic intelligence. Today's LLMs are trained and served on clusters at megawatt scale, whereas the biological brain solves general-intelligence tasks on the order of 20 W. Closing this gap defines the next stage of my research: moving from algorithms to the computational substrate (neuromorphic platforms and hardware co-design).

#### Neuromorphic Computing and Hardware Acceleration

- **Spiking Neural Networks (SNN):** Event-driven sparse computation; training with surrogate gradients and local plasticity rules (STDP).
- **Platforms and frameworks:** Intel Loihi / Lava, SpiNNaker, BrainScaleS, snnTorch, Nengo, Brian2.
- **Accelerators and HPC:** CUDA, FPGA, in-memory computing, memristive architectures.
- **Efficiency metrics:** Energy per operation and per inference, activation sparsity, and comparison with dense transformer models on comparable tasks.

#### Compute-in-Memory and Physics-Based Computing

I study analog compute-in-memory (CIM) as a researcher: an artificial neural network can be embedded directly into the memory array, with the physics of the device itself performing part of the computation, instead of shuttling data between memory and processor (bypassing the von Neumann bottleneck).

**Case study:** Neural dynamical systems on phase-change memristors (Peking University and Chinese Academy of Sciences, *Science*, 2026). A neural dynamical system (NDS) couples a neural network with a continuous-time differential-equation solver, demonstrated on cortical surface reconstruction.

- Network weights are mapped to the multilevel conductance states of phase-change memory, allowing multiply-accumulate operations to run inside the array.
- Conductance drift, normally treated as a device defect, is harnessed as a physical implementation of the solver's adaptive step-size search.
- Reported results: 2.12 ms latency per integration iteration at an error tolerance of 10⁻⁷; end-to-end reconstruction 50–478× faster than an NVIDIA A100 GPU; 3.8–36× faster and 12–25× lower power than prior NDS hardware.

**Research interests:** Turning device non-idealities (drift, noise, variability) into computational resources; hardware-aware training of neural ODEs; real-time modeling of physical manifolds; and potential relevance for medical imaging and robotics.

#### Systems Programming & Cognitive Cybernetics

- **Systems Programming:** Rust and modern C++ (17/20) for high-performance computing, low-level inference optimization, and memory-safe code without the overhead of interpreted languages. Integration with the Python ecosystem (PyO3, pybind11, custom CUDA kernels, Triton).
- **Cognitive Cybernetics:** Predictive coding and the free-energy principle as a computational basis for learning beyond classical backpropagation.
- **Optimal Control Theory:** LQR, model predictive control, and links to reinforcement learning and Active Inference.
- **Synthesis:** Hierarchical predictive world models implemented on a neuromorphic substrate.

### Planned Practical Work

| Direction | Deliverable |
|---|---|
| **Latent Voids** | Persistent homology (e.g., GUDHI or Ripser) on layer-wise activations of a small transformer; void statistics vs. hallucination rate; code and report. |
| **Familiar vs. Known** | Knowledge-sufficiency adapter on an open model; AURC comparison against a probe-plus-threshold baseline on popularity-stratified PopQA; code and report (including negative results). |
| **Intent-Labeled Benchmark** | Terminal tasks with injected ambiguities and ground-truth intent; public dataset, baselines, and evaluation code. |
| **Intent Probing & Steering** | Probes, activation patching, and steering for intent representation in an open coder model; comparison with norm-matched random-direction controls. |
| **SNN** | Spiking network implemented and trained with snnTorch; energy/accuracy comparison against an ANN counterpart. |
| **Predictive Coding** | Reproduction of a hierarchical predictive network in PyTorch; published code and report. |
| **Rust / C++** | Custom high-performance kernel (e.g., quantized matrix multiplication) with a benchmark against PyTorch. |

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

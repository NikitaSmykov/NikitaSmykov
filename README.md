
**Applied AI Engineer | Founder of Polyphoros & ACNN**

My research and engineering efforts are divided into two highly specialized deep-tech vectors: **AI-Native Biotechnology** and **Computational Neuroscience**. My core engineering philosophy centers on *Zero-Hallucination AI*—bridging LLMs, large-scale knowledge graphs, and formal mathematical verification (Lean 4) to eliminate probabilistic errors in critical biological systems.

Polyphoros | AI-Native Biotech & Drug Discovery

<img width="1024" height="1024" alt="Логотип Polyphoros" src="https://github.com/user-attachments/assets/2e7c9499-f829-4995-af25-6b49add4bea0" />

*Focus: De novo generation, biobetters, and epigenetic reprogramming agents.*
Building the **Q.E.D. Engine**—a deterministic, 4-stage in silico pipeline. We automate target identification and structural synthesis while mathematically verifying the safety pathways (ADMET) of generated molecules prior to *in vivo* trials.

**Polyphoros Open-Source & Architecture Initiatives:**
*   **Q.E.D. Engine Core:** `LangGraph`, `AutoGPT`, `Lean 4` (Formal verification adapter for drug safety).
*   **Target ID & Repurposing:** `PrimeKG` (Neo4j), `scGPT`, `CellOracle`.
*   **Structural Synthesis:** `GENTRL`, `DiffDock`, `ESM-3` (Reverse engineering of natural toxins).
*   **Toxicity & Pseudotime:** `DeepChem`, `PROGENy`, `STREAM/VITAE`.

#### The Polyphoros Tech Stack (Bio-Engineering Infrastructure)
To process massive biological datasets and orchestrate autonomous research, I utilize a high-throughput, locally deployable AI stack:

*   **Applied AI & Local Inference:** `PyTorch`, `Hugging Face Transformers`, `vLLM` (High-throughput serving), `Ollama` (Local Llama-3/Qwen for secure medical data), `BitsAndBytes` (4/8-bit Quantization), `OpenRouter API`.
*   **Agentic AI & Orchestration:** `LangGraph` (Cyclic drug-discovery workflows), `LangChain`, `Model Context Protocol (MCP)`.
*   **Advanced RAG & Vector Search:** `LlamaIndex`, `Qdrant` (Hybrid Search for biomedical literature), `ChromaDB`, `FAISS`, Semantic/Recursive Chunking.
*   **Data Engineering & ETL:** `Python 3 (OOP/Asyncio)`, `Pandas/Regex` (Data Cleansing), `Scrapy/BeautifulSoup` (Parsing FDA/Clinical databases).
*   **Databases:** `PostgreSQL` (Advanced SQL, CTEs, Window Functions for clinical data structuring).
*   **Backend, MLOps & Observability:** `FastAPI`, `Docker / Docker-compose`, `LangSmith` (Agent prompt tracing), `Prometheus + Grafana` (Hardware and GPU inference monitoring).

#### 📂 Polyphoros Open-Source Initiatives
A collection of internal healthcare infrastructure, multi-agent middleware, and clinical data pipelines developed at Polyphoros, released to the open-source medical AI community.

**1. Q.E.D. Clinical Orchestrator | FHIR-Native GraphRAG Middleware**

*Tech Stack: `FastAPI`, `LangGraph`, `Qdrant`, `Docker`, `HL7 FHIR`*

Architected an on-premise, multi-agent integration middleware designed to eliminate medical data silos. Unifies disjointed diagnostic outputs into a secure Patient Knowledge Graph. Fully PDPA/HIPAA compliant, utilizing local LLM inference to guarantee data privacy.

**2. Diagnostic Validation AI | Medical Computer Vision & HITL**

*Tech Stack: `LangGraph`, `Computer Vision`, `FastAPI`, `Docker`, `Llama-3 (Local)`*

Engineered a hybrid multi-agent medical assistant featuring a strict Human-in-the-Loop (HITL) validation architecture. Implemented Confidence-Based Routing to automatically escalate complex scans to human specialists if AI diagnostic confidence falls below 98%, ensuring Cyber Defence in Depth.

**3. Bio-Literature RAG System | Agentic AI & Dynamic Grounding**

*Tech Stack: `Python`, `LangGraph`, `PostgreSQL`, `LlamaIndex`, `Qdrant`*

Architected a production-ready Agentic AI system for parsing complex pharmacological research. Developed a robust Fallback Handler where the Planner-Agent autonomously detects knowledge gaps and safely re-routes queries to verified external medical databases, strictly preventing LLM hallucinations.

**4. Autonomous Clinical Coder | NLP & LLM Engineer**

*Tech Stack: `PyTorch`, `vLLM`, `Python`, `Pydantic`, `JSON Extraction`*

Developed an orchestration layer using Router-agents to automate administrative clinical workflows. Parses unstructured patient complaints and physician voice notes, transforming them into strictly formatted SOAP notes and valid ICD-10 JSON payloads for EHR integration.






 ACNN (Applied Centre for Neuroscience and Neurology)
 <img width="1364" height="768" alt="photo_5839202116059205906_w" src="https://github.com/user-attachments/assets/2f35b463-0127-4549-b24e-026af15b3f16" />

*[Currently in Stealth R&D mode]* Building the middleware and safety protocols for clinical BCI (Brain-Computer Interface) deployment, neural telemetry decoding, and functional connectome mapping.

**ACNN Infrastructure Stack:**
*   **ACNN-SafeStim:** Formally verified closed-loop BCI router (`Lean 4`, `Rust`, `Embedded C`). Guarantees zero-seizure cortical stimulation.
*   **ACNN-Drosophila-SNN:** *In Silico* connectome emulation (`neuprint-python`, `Brian 2`, `Neo4j`). Translating static synaptic topologies into dynamic Spiking Neural Networks.
*   **ACNN-CorticalStream:** Ultra-low latency spike sorting & motor decoding (`Rust`, `C++`, `SpikeInterface`).
*   **ACNN-TelemetryCore:** High-throughput ECoG/EEG distributed pipeline (`Apache Kafka`, `PostgreSQL`, `MNE-Python`).



## 🛠 The ACNN Tech Stack: Full-Cycle BCI & Connectome Architecture

To bridge the gap between carbon and silicon, my engineering stack spans low-latency signal processing, neuromorphic simulation, and formally verified AI orchestration.

###  BCI Telemetry & Signal Processing (Read/Write Layer)
*Extracting and decoding real-time neural spikes with zero-latency.*
- **Brain-Computer Interfacing:** `LSL (Lab Streaming Layer)`, `OpenBCI`, `SpikeInterface`
- **Time-Series Analysis & DSP:** `MNE-Python`, `Brainstorm`, `SciPy`, `Digital Signal Processing (DSP)`
- **Low-Latency Bridging:** `Rust`, `C++` (for microsecond-precision cortical stimulation routing)

###  Computational Neuroscience & In Silico Emulation
*Simulating the functional connectome and testing the "Ship of Theseus" protocols.*
- **Neuromorphic Emulation:** `NEST Simulator`, `NEURON`, `Brian 2` (Spiking Neural Network frameworks)
- **Cognitive Node Modeling:** `Nengo` (Large-scale brain modeling)
- **Graph Architecture:** `Neo4j`, `NetworkX`, `PrimeKG` (Mapping 3D synaptic pathways)

###  Neuro-Symbolic AI & Agentic Orchestration
*Translating raw EEG/ECoG noise into structured semantic commands.*
- **Agentic Frameworks:** `LangGraph`, `AutoGPT`, `CrewAI`
- **Foundation Models:** `Kimi K3`, `Llama 3`, `Transformers (Time-Series & Vision)`
- **Dynamic Grounding:** `GraphRAG`, `ChromaDB`, `FAISS`

###  Formal Verification & Cyber Defence (Zero-Hallucination)
*Mathematically proving that BCI feedback loops cannot harm the biological host.*
- **Theorem Proving:** `Lean 4` (Formal verification of neural API safety bounds)
- **Safety Engineering:** `Human-in-the-Loop (HITL)`, `Confidence-Based Routing`

###  Infrastructure & High-Performance Computing (HPC)
*Running tera-parameter models and connectome simulations on premise.*
- **Compute:** `CUDA`, `Triton`, `WASTE Engine` (Weight-Aware Streaming Tensor Engine)
- **Ops:** `Docker`, `Kubernetes`, `FastAPI`, `PostgreSQL`, `HL7 FHIR` (for clinical compliance)
---

📂 ACNN Open-Source Initiatives

A collection of internal low-latency infrastructure, neuromorphic middleware, and clinical BCI telemetry pipelines developed at ACNN.

### 1. ACNN-CorticalStream | Ultra-Low Latency Spike Sorting & Motor Decoding
**Tech Stack:** `Rust`, `C++`, `CUDA`, `TensorRT`, `SpikeInterface`, `LSL`
Architected a bare-metal DSP (Digital Signal Processing) pipeline for real-time spike sorting from 1024-channel high-density microelectrode arrays. Implemented a sub-millisecond motor intent decoding engine using quantized edge-optimized RNNs deployed via TensorRT, achieving the latency requirements necessary for seamless closed-loop neuro-prosthetics.

### 2. ACNN-SafeStim | Formally Verified Closed-Loop BCI Router
**Tech Stack:** `Lean 4`, `Rust`, `Embedded C`, `Formal Methods`
Engineered a mathematical verification layer for write-access cortical stimulation. Utilized the Lean 4 theorem prover to formally guarantee that dynamic electrical stimulation parameters (pulse width, frequency, amplitude) generated by the closed-loop ML model will never exceed safe charge-density thresholds. Achieved a mathematically proven zero-seizure guarantee before deploying code to embedded microcontrollers.

### 3. ACNN-ImplantVision | Vascular Avoidance Routing AI
**Tech Stack:** `Python`, `C++`, `PyTorch 3D`, `OpenCV`, `ROS2`
Developed a computer vision and 3D path-planning algorithm intended for automated robotic BCI insertion. Analyzes volumetric fMRI and OCT vascular maps in real-time to generate micro-thread insertion trajectories that strictly avoid cortical vasculature, minimizing tissue damage and bleeding during electrode implantation.

### 4. ACNN-Neuromorphic GraphRAG | Spiking Connectome Emulator
**Tech Stack:** `NEST Simulator`, `Nengo`, `Neo4j`, `LangGraph`, `Python`
Built an in silico emulation environment combining Spiking Neural Networks (SNNs) with GraphRAG. Maps massive functional connectome datasets (e.g., FlyEM, Allen Brain Atlas) into Neo4j to simulate synaptic routing and test neural decoding algorithms in a virtual environment prior to in vivo deployment.

### 5. ACNN-TelemetryCore | High-Throughput ECoG/EEG Distributed Pipeline
**Tech Stack:** `Apache Kafka`, `PostgreSQL`, `MNE-Python`, `Docker`, `HL7 FHIR`
Engineered a distributed, high-throughput ETL architecture to ingest, denoise, and standardize continuous multi-terabyte neural time-series data streams across distributed BCI clinical trials. Ensures zero data loss and strict HIPAA/PDPA compliance for sensitive brain-computer interface telemetry. Architecture designed with forward-compatibility for non-invasive, high-density neural telemetry (e.g., optical readout from electro-plasmonic nanoantennas and magnetoelectric stimulation), addressing the signal demultiplexing bottleneck inherent in nanoparticle BCI distribution.

### 6. ACNN-Drosophila-SNN | In Silico Connectome Emulation
**Tech Stack:** `neuprint-python`, `Brian 2`, `NetworkX`, `Neo4j`, `SciPy`
Engineered an in silico emulation pipeline to extract, map, and functionally simulate targeted sensori-motor sub-graphs of the adult Drosophila melanogaster connectome. Interfaced with the Janelia hemibrain database to convert static synaptic topologies into dynamic Spiking Neural Networks (SNNs). This serves as a foundational neuromorphic sandbox for testing closed-loop BCI routing protocols before mammalian in vivo deployment.

---
*"Solve intelligence, and then use that to solve everything else."*


### 📫 Let's Connect

<div align="center">

[![Email](https://img.shields.io/badge/Email-002B5B?style=for-the-badge&logo=gmail&logoColor=white)](mailto:nikos230612@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-002B5B?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/твоя_ссылка/)
[![ORCID](https://img.shields.io/badge/ORCID-002B5B?style=for-the-badge&logo=orcid&logoColor=white)](https://orcid.org/my-orcid?orcid=0009-0007-2913-5960)

</div>



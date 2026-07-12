<h1 align="center" style="color: #00B4D8;">Formal Biology & DeepTech Architecture</h1>

<p align="center">
 Results-driven Applied AI Engineer specializing in the rapid integration of Large Language Models (LLMs) into B2B and Enterprise workflows. Expert in designing autonomous, hallucination-free Retrieval-Augmented Generation (RAG) pipelines and deploying scalable backend architectures.
</p>

---

### 🧬 What I Do

- 🔬 **AI & NLP:** Building Multi-Agent systems, hybrid RAG pipelines, and precise data extraction engines.
- ⚙️ **Backend:** Developing asynchronous, high-load APIs to serve ML models securely and efficiently.
- 🌐 **Data Engineering:** Structuring unstructured medical/regulatory data (PubMed, FDA compliance) into actionable Knowledge Graphs.

---

### 🛠️ Core Tech Stack

<div align="center">
 
**AI & Machine Learning** <br>
![Python](https://img.shields.io/badge/Python-004D40?style=for-the-badge&logo=python&logoColor=00B4D8)
![LangChain](https://img.shields.io/badge/LangChain-00695C?style=for-the-badge&logo=chainlink&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-00796B?style=for-the-badge&logo=Ollama&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-00897B?style=for-the-badge&logo=database&logoColor=white)

**Backend & Data Engineering** <br>
![FastAPI](https://img.shields.io/badge/FastAPI-004D40?style=for-the-badge&logo=fastapi&logoColor=00B4D8)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-00695C?style=for-the-badge&logo=postgresql&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-00796B?style=for-the-badge&logo=pandas&logoColor=white)

**Infrastructure** <br>
![Docker](https://img.shields.io/badge/Docker-00897B?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-004D40?style=for-the-badge&logo=linux&logoColor=00B4D8)
![Git](https://img.shields.io/badge/Git-00695C?style=for-the-badge&logo=git&logoColor=white)

</div>

---

### 📚 Currently Learning & Exploring

* **Formal Verification & AGI:** Lean 4, OpenCog Hyperon (Atomspace), AI World Models & Cognitive Architectures.
* **Agentic AI & Orchestration:** Building autonomous Multi-Agent workflows and LLM Orchestrators.
* **LLM Engineering (Ops & Tuning):** Fine-Tuning (PEFT/LoRA), Model Quantization, Local Inference Optimization.
* **Graph Networks (Knowledge Graphs):** Neo4j, NetworkX, PyVis.
* **Advanced NLP & Scraping:** LlamaIndex, spaCy, Playwright, BeautifulSoup.
* **Bio-Informatics Research:** Parsing PubMed, PMC, bioRxiv, Google Scholar. Exploring OpenAI's GeneBench-Pro evaluation frameworks.

---


### 📫 Let's Connect

<div align="center">
 <a href="mailto:nickita.smykov@proton.me">
 <img src="https://img.shields.io/badge/Email-nickita.smykov%40proton.me-004D40?style=for-the-badge&logo=protonmail&logoColor=00B4D8" alt="Email" />
 </a>
 <a href="https://linkedin.com/in/YOUR_LINKEDIN_ID">
 <img src="https://img.shields.io/badge/LinkedIn-00695C?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
 </a>
 <a href="https://pin.it/3K0fpZAmJ">
 <img src="https://img.shields.io/badge/Pinterest-004D40?style=for-the-badge&logo=pinterest&logoColor=00B4D8" alt="Pinterest" />
 </a>
</div>

> [!TIP]
> ## 🧬 Independent R&D Initiative: Veyo (Formal Bio-Engineering & AGI for Longevity)
> 
> **Veyo** is a DeepTech initiative and a Potentially Strong Intellectual System (PSIS) designed to solve biological aging. The core mission is to transition biology from statistical guessing (AI-driven pattern matching) to **Formal Bio-Engineering**, utilizing mathematical logic and automated theorem proving.
> 
> ### 🛑 The Problem: Noise and Hallucinations in Biology
> Modern biomedical literature is saturated with logical inconsistencies. Standard LLMs hallucinate and lack strict logical coherence. Feeding raw PubMed articles to an AI is insufficient. **Veyo** solves this by translating biological hypotheses into the **Lean 4** formal language, verifying them against known biochemical constraints, and discarding 99% of invalid hypotheses.
> 
> ### 🏗️ Core Engineering Foundation: Preclinical GraphRAG Synthesizer
> To bridge the gap between commercial applied AI and the grand vision of Project Veyo, I am currently developing the **Preclinical GraphRAG Synthesizer** — an architect-level multi-agent system. This project moves away from primitive vector-based RAG (which merely retrieves similar text chunks) toward the strict extraction of facts and logical multi-hop connections. 
> 
> The architecture consists of three core engineering blocks:
> 
> 1. **Graph Database (Neo4j) & Network Mathematics:** Standard RAG is blind to multi-hop logic. If a PDF states *"Substance A inhibits Protein B, which causes Disease C,"* a vector DB (ChromaDB) only returns a text chunk. Neo4j stores this mathematically as a graph: `(Node: Substance A) -[Edge: INHIBITS]-> (Node: Protein B) -[Edge: CAUSES]-> (Node: Disease C)`. This allows for complex Cypher querying and true graph traversal rather than simple cosine similarity.
> 2. **Strict Data Extraction (Tool Calling + Pydantic):** To reliably ingest raw PubMed text into Neo4j, the LLM is forced to output rigidly structured JSON triplets (Subject-Predicate-Object), eliminating hallucinations. This is achieved via API-level Function Calling, with FastAPI and Pydantic validating the data types to ensure model errors never crash the backend.
> 3. **Agent Orchestration (LangGraph):** The system operates as a Finite State Machine (FSM) rather than a single-pass pipeline. The workflow loops through specialized agents: **Parser Agent** (extracts facts) ➡️ **Critic Agent** (checks for contradictions) ➡️ **Loader Agent** (commits to the graph). This requires advanced state management and cycle control across the execution graph.
> 
> ### 🧠 Advanced Architectural Pillars
> * **OpenCog Hyperon (Atomspace):** While Neo4j handles rapid traversal, Atomspace serves as the core dynamic storage. It stores biological entities as **hypergraphs** with variable connections, explicitly defining non-linear metabolic pathways for rigorous verification.
> * **Lean-Biology (Formal Verification):** We are developing a formalized language library based on **Lean 4**. If a hypothesis states that *Molecule X suppresses Y*, Lean forces the system to account for all conditions, preventing logical gaps.
> * **Autonomous Auto-Experimentation:** Veyo includes a feedback loop for automated Lab-on-a-Chip environments, testing verified predictions in real-time on robotic cell cultures.

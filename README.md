# 🧠 Lluma: Ontology-Grounded AI Assistant for Mental Health Support

Authors:

Ahmed OUIDANI¹*, Chihab OUCHEN¹, Abderrahman CHEKRY²

¹ Graduate School of Technology & Polydisciplinary Faculty, Cadi Ayyad University, Safi, Morocco
² LAPSSII Laboratory, Graduate School of Technology, Cadi Ayyad University, Safi, Morocco

📧 a.ouidani9533@uca.ac.ma

___
### 🩺 Overview
Lluma is a research project that integrates a formal mental health ontology with a Retrieval-Augmented Generation (RAG) framework powered by a Large Language Model (LLM).
It aims to provide context-aware, safe, and factually grounded mental health information, particularly in under-resourced regions like Morocco.

This repository contains:

- The ontology (lumaOnto.ttl) describing mental health concepts (e.g., anxiety, depression, insomnia).
- The implementation notebook (lluma(5).ipynb) showing how the ontology is integrated into a Hybrid RAG system built with LangChain and a local Mistral-7B model.

___
### 🧩 Repository Structure
```text
📂 Lluma/
├── 📜 README.md                ← Project overview
├── 🧠 lumaOnto.ttl             ← Mental health ontology (OWL/RDF format)
└── 💻 lluma.ipynb              ← Jupyter notebook (Hybrid RAG implementation)
```
___
### ⚙️ System Architecture

Lluma combines three main components:
1. Ontology Layer (Knowledge Base)
    - Built in OWL using Protégé
    - Captures disorders (GAD, MDD, Insomnia), symptoms, treatments, and relationships
    - Structured for graph traversal and semantic reasoning

2. Hybrid RAG Pipeline (LangChain)
    - Uses FAISS for semantic vector retrieval
    - Employs a custom HybridGraphRetriever combining:
      - Vector similarity search (semantic relevance)
      - RDF graph traversal (relational context)

3. Local LLM Engine
    - Model: Mistral-7B-Instruct-v0.2 via CTransformers
    - Generates grounded, empathetic responses
    - Memory: ConversationBufferMemory

___
### 📘 How to Run
#### 1️⃣ Requirements

Install dependencies in a clean Python environment (Python ≥3.10):
```
pip install langchain faiss-cpu rdflib sentence-transformers ctransformers jupyter
```

#### 2️⃣ Launch the notebook
```
jupyter notebook lluma.ipynb
```
#### 3️⃣ Configure your model

Ensure you have the Mistral-7B-Instruct-v0.2 weights available locally or specify the path inside the notebook cell.

4️⃣ Interact with Lluma

Run the conversation cells to test queries such as:

“What are common treatments for insomnia?”

“Can anxiety and depression occur together?”

“What should I do if I feel hopeless?”

🧠 Ontology Details

File: lumaOnto.ttl

Format: RDF/OWL

Editor: Protégé 5.x

Main Classes:

Disorder, Symptom, Treatment, Trigger, SeverityLevel

Main Object Properties:

hasSymptom, hasTreatment, triggeredBy, manifestsIn

You can visualize or edit the ontology using Protégé
.

📊 Key Results
Evaluation Aspect	Base LLM	Lluma (Ontology + RAG)
Factual Accuracy	❌ Frequent hallucinations	✅ Fully grounded in ontology
Safety in Sensitive Queries	❌ Risk of harmful suggestions	✅ Redirects to professionals, local crisis line
Domain Consistency	❌ Breaks persona	✅ Stays within mental health scope
📍 Citation

If you use Lluma or its ontology in your research, please cite:

Ouidani, A., Ouchen, C., & Chekry, A. (2025). Introducing Lluma: Large Language Understanding Mental Assistant. iJXX Journal, 2025.

BibTeX:

@article{ouidani2025lluma,
  title={Introducing Lluma: Large Language Understanding Mental Assistant},
  author={Ouidani, Ahmed and Ouchen, Chihab and Chekry, Abderrahman},
  journal={iJXX Journal},
  year={2025}
}

🤝 Contributing

Contributions are welcome!
You can:

Extend the ontology with new disorders or localized knowledge

Improve the RAG retriever or model prompt design

Help evaluate the system through user studies

⚠️ Disclaimer

Lluma is a research prototype for educational and scientific use only.
It does not provide medical advice or replace consultation with qualified healthcare professionals.

# SolarSight O&M: Multimodal RAG for Automated PV Infrastructure Diagnostics

## Project Overview
**SolarSight O&M** is a Multimodal Retrieval-Augmented Generation (RAG) system designed to bridge the gap between visual diagnostic data and engineering expertise in the solar energy sector. 

In large-scale solar farms, O&M (Operations & Maintenance) engineers deal with massive amounts of Electroluminescence (EL) imagery. Currently, cross-referencing these images with manufacturer-specific technical manuals is a manual, error-prone process. **SolarSight O&M** automates this by aligning visual fault features with textual repair protocols in a joint latent space.

## Key Features
- **Cross-Modal Retrieval:** Query the system with an EL image of a faulty solar cell to retrieve the exact relevant page from a technical PDF manual.
- **Zero-Shot Diagnosis:** Utilizes Gemini 1.5 Pro to identify defects like micro-cracks, PID, and busbar failures without manual labeling.
- **Grounded Action Plans:** Generates step-by-step repair strategies based strictly on retrieved manufacturer documentation to prevent LLM hallucinations.

## Tech Stack
- **Orchestration:** LlamaIndex
- **Reasoning Engine:** Gemini 1.5 Pro (Multimodal LLM)
- **Embeddings:** CLIP (Contrastive Language-Image Pre-training)
- **Vector Store:** Pinecone / ChromaDB
- **Frontend:** Streamlit
- **Domain Focus:** Energy Science, PV Diagnostics, Infrared Thermography

## Project Structure
```text
├── data/
│   ├── images/       # EL imagery (PVE-EL Dataset)
│   └── manuals/      # Manufacturer PDFs (Jinko, Trina, etc.)
├── src/
│   ├── engine.py     # RAG pipeline logic
│   └── embedder.py   # CLIP embedding generation
├── app.py            # Streamlit dashboard
└── requirements.txt

# nlp-project-agent

# 🕵️‍♂️ Sector-Specific ReAct Agent
This project aims to transform a traditional static Large Language Model (LLM) into an autonomous ReAct agent that can reason, decide, and act by using external knowledge sources.

## 🏗️ Selected Domain: Zoning & Urban Planning Consultancy
## 📌 Selected Sector and Motivation

The selected domain for this project is Zoning and Urban Planning Consultancy. This sector was chosen because zoning regulations require precise interpretation of technical legal documents, such as development plans, zoning codes, floor area ratios (FAR), building height limits, and land-use restrictions. These rules are often complex, context-dependent, and prone to misinterpretation if answered without direct reference to official documents.

Therefore, zoning consultancy is an ideal domain to demonstrate:
- The importance of evidence-based reasoning
- The risks of hallucination in LLMs
- The advantages of tool-assisted decision-making using ReAct agents

### Project Structure
```text
imar_rag/
│
├── data/
│   ├── raw/                 # Original PDF regulation document
│   ├── processed/           # Extracted and cleaned text
│   └── chroma_final/        # ChromaDB vector database
│
├── imar_rag.ipynb           # Main Colab notebook
├── README.md                # Project documentation


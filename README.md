# nlp-project-agent

## 🕵️‍♂️ Sector-Specific ReAct Agent
This project aims to transform a traditional static Large Language Model (LLM) into an autonomous ReAct agent that can reason, decide, and act by using external knowledge sources.


## 📌 Selected Sector and Motivation

The selected domain for this project is Zoning and Urban Planning Consultancy. This sector was chosen because zoning regulations require precise interpretation of technical legal documents, such as development plans, zoning codes, floor area ratios (FAR), building height limits, and land-use restrictions. These rules are often complex, context-dependent, and prone to misinterpretation if answered without direct reference to official documents.

Therefore, zoning consultancy is an ideal domain to demonstrate:
- The importance of evidence-based reasoning
- The risks of hallucination in LLMs
- The advantages of tool-assisted decision-making using ReAct agents


### 🧠 Methodology
🔹 Retrieval-Augmented Generation (RAG)
- The Planned Areas Zoning Regulation document was converted from PDF to text
- The text was split into semantic chunks
- Embeddings were generated using sentence-transformers/all-MiniLM-L6-v2
- A ChromaDB vector database was used for semantic retrieval

🔹 ReAct Reasoning Loop
- The agent follows a structured reasoning cycle:
Thought → Action → Observation → Answer
- At each step, the agent explicitly states:
-- Thought: its reasoning and decision-making
-- Action: the tool to be used
-- Observation: the tool’s output
-- Answer: the final response once sufficient information is gathered

### Project Structure
```text
imar_rag/
│
├── data/
│   ├── raw/
│   │   └── planli_alanlar_imar_yonetmeligi.pdf
│   │       # Original zoning regulation document (PDF)
│   │
│   ├── planli_alanlar_imar_yonetmeligi.txt
│   │   # Extracted and cleaned text version of the regulation
│   │
│   ├── chunks.jsonl
│   │   # Text chunks used for embedding (323 chunks)
│   │
│   └── chroma_final/
        # ChromaDB vector database
```

### Scenerio Tests
As required in Step 4: Scenario Tests, the agent was evaluated using both single-hop and multi-hop query types.
A total of 6 test scenarios were executed, and all agent logs were recorded and documented with screenshots.


- This test evaluates whether the agent can directly retrieve the definition of Emsal (KAKS) for residential areas from the zoning regulation knowledge base without requiring any external data or computation:

<img width="453" height="51" alt="Ekran görüntüsü 2025-12-29 172703" src="https://github.com/user-attachments/assets/a16a62f1-ef52-4b87-a35d-48b345a72a59" />

<img width="1480" height="50" alt="Ekran görüntüsü 2025-12-29 172931" src="https://github.com/user-attachments/assets/61da1cff-59ef-4ab3-8293-822f3907b90f" />



- This scenario tests the agent’s ability to correctly apply the emsal calculation formula using the built-in calculator tool after interpreting the zoning coefficient:

<img width="606" height="47" alt="Ekran görüntüsü 2025-12-29 172747" src="https://github.com/user-attachments/assets/17fc6067-82c1-4b1c-b6c1-06021399572b" />

<img width="808" height="247" alt="Ekran görüntüsü 2025-12-29 172809" src="https://github.com/user-attachments/assets/0a14afc1-1981-4eea-abe3-a3ce49d780ba" />

- This test checks whether the agent can first retrieve up-to-date legal information from the web and then reason about its implications on emsal (KAKS) calculations:

<img width="685" height="48" alt="image" src="https://github.com/user-attachments/assets/3b32758b-2260-42c4-81f8-975b7e6b4717" />

<img width="1732" height="57" alt="image" src="https://github.com/user-attachments/assets/81a93450-0ab6-41e4-8667-84b473f90825" />

- Description:
This comprehensive scenario tests the agent’s ability to: retrieve the emsal (KAKS) definition from the regulation knowledge base, fetch real-time exchange rate data from the web, compute construction area and convert total construction cost from USD to TL using chained calculations:

<img width="778" height="277" alt="image" src="https://github.com/user-attachments/assets/0ea72b8b-ef79-496e-9b3e-b08eb87402cf" />

<img width="518" height="48" alt="image" src="https://github.com/user-attachments/assets/ffa38e42-2241-4b05-bbcb-d9e7ecd38a04" />













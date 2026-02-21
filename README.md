# Kansas Food Pantry Assistant

A conversational food pantry assistant built using semantic retrieval, intent classification, structured data filtering, and optional LLM-based response generation.

This system helps users locate food assistance resources across Kansas using natural language queries.

---

## Features

- 🔎 Semantic search using FAISS + MiniLM embeddings  
- 🧠 Zero-shot intent classification (BART-MNLI)  
- 📍 City and county-based filtering  
- 📅 Multi-day pantry planning  
- 🪪 ID / residency / student requirement detection  
- 🗄 SQLite-backed structured storage  
- 💬 Interactive Gradio chatbot interface  
- 🤖 Optional quantized local LLM generation (Llama, Mistral, Qwen)  

---

## System Architecture

### 1. Data Layer
- JSON dataset ingestion  
- Canonicalization of names, phones, addresses  
- Structured hours parsing  
- SQLite database with indexed fields  

### 2. Retrieval Layer
- SentenceTransformer embeddings (MiniLM)  
- FAISS vector search  
- Composite ranking (semantic similarity + confidence score)  

### 3. Understanding Layer
- Zero-shot intent classification  
- Slot extraction (city, county, days, ID requirements)  
- Hybrid rule-based + semantic filtering  

### 4. Response Layer
- Deterministic templated responses  
- Optional LLM rewriting with quantized HuggingFace models  

### 5. Interface
- Gradio conversational chatbot  

---

## Technologies

- Python  
- SQLite  
- FAISS  
- SentenceTransformers  
- HuggingFace Transformers  
- spaCy  
- Gradio  
- Selenium (for dataset creation)  

---

## 📦 Dataset Creation

The pantry dataset was created using an automated web scraping pipeline to collect food pantry information across all Kansas counties.

### Data Collection Process

1. Retrieved Kansas county names using the U.S. Census API  
2. Visited county-level pantry listings on KansasFoodSource  
3. Opened individual pantry pages and extracted:
   - Pantry name  
   - Address  
   - Phone number  
   - Operating hours  
   - Additional information  
   - Source link  
4. Cleaned and structured the data into JSON format  


## Running the Application

Install the required dependencies and execute the main Python script.  
The Gradio interface will launch in your browser.

---

## Example Queries

- "Pantries in Wichita open Saturday"
- "Food pantry without ID requirement"
- "Mobile pantry near me"
- "Help me plan for Monday and Tuesday"

---

## Notes

- Designed specifically for Kansas pantry data  
- Combines structured database filtering with semantic retrieval  
- Built as an applied AI retrieval and conversational system project  

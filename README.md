# RAG-Implementation  
_A minimal, production-style Retrieval-Augmented Generation (RAG) Implementation_  

##  Project Overview  
This repository provides a lightweight but fully functional RAG pipeline to build a vector-searchable knowledge base and ask questions grounded in documents.  
It uses:  
- **Embeddings** to convert documents into vector form  = semantic representation of words/sentences/documents 
- **Vector DB** to index and retrieve relevant chunks  
- **LLM** to generate answers using the retrieved context  


## Tech Stack & Dependencies Used :
- **Python** (3.10+)  
- [Chroma](https://docs.trychroma.com/docs/overview/getting-started) — open-source vector database
- [Langchain](https://docs.langchain.com/oss/python/langchain/overview)  — open-source framework to build  Agents and Applications powered by LLMs
- [Ollama](https://docs.ollama.com/quickstart) - open-source tool allows to run LLM's on on local machines
( I've personally used : [llama2:13b](https://ollama.com/library/llama2) 13B parameter model in my local macOS ) 
  

## 📂 Repository Structure  
```
RAG-Implementation/
├─ data/                     ← put your raw document files here
├─ my_embedding_functions.py ← custom embedding logic  
├─ generateVectorDB.py       ← builds the vector DB using custom embedding logic
├─ queryRAG.py               ← Python script to query the stored vector DB .
├─ requirements.txt          ← install required dependencies  
├─ .gitignore  
```

## Usage & Setup  

### 1. Clone the repo  
```
git clone https://github.com/NaveenKumar-Marupalli/RAG-Implementation.git
cd RAG-Implementation
```

### 2. ( Optional ) Create a [Python virtual environment](https://docs.python.org/3/tutorial/venv.html)  (or) [Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) Environment 


### 3. Install dependencies  
```
pip install -r requirements.txt
```

### 4. Place the "pdf" files (or) documents inside "data/" folder
( I've personally kept [my Resume as .pdf file](https://naveen-kumar-marupalli.vercel.app/) inside "data/" folder .

### 5. Ingest documents and build vector DB  
```
python generateVectorDB.py
```

### 6. Query the RAG system  
```
python queryRAG.py  "Your-Custom-Query based on data ?"
```

## 💡 Example  
```
$ python queryRAG.py  "Your-Custom-Query based on data ?"
Answer:
... [answer with citations like – Sources: ['data/file-1.pdf:{page-id}:{chunk-index}', 'data/file-2.pdf:{page-id}:{chunk-index}']] ...
```

- #### LLM's response ( WITHOUT RAG & context data ) :
<img width="795" height="596" alt="image" src="https://github.com/user-attachments/assets/fc1b3d51-7c1a-4a1f-a9a9-a1e596d66ab0" />

- #### After implementing RAG , Query response retrieved from stored vector DB :
<img width="1196" height="412" alt="image" src="https://github.com/user-attachments/assets/e8184a9d-bbb4-42e9-ac80-15f5d3836bd8" />




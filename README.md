# 🧠 Routing Agent with LlamaIndex, Groq, and HuggingFace Embeddings

This project demonstrates a routing agent setup using [LlamaIndex](https://github.com/jerryjliu/llama_index), [Groq's LLaMA3-70B model](https://console.groq.com/), and [HuggingFace Embeddings](https://huggingface.co/BAAI/bge-small-en-v1.5) for answering queries from multiple domain-specific documents.



## 🚀 Features

- ✅ Uses `Groq` to access **LLaMA 3-70B** via LlamaIndex
- ✅ HuggingFace `bge-small-en-v1.5` model for text embeddings
- ✅ Indexes and queries PDF documents (`AeroFlow` and `EcoSprint`)
- ✅ Routes questions automatically to the correct index using `RouterQueryEngine`
- ✅ Built in **Google Colab** with interactive Q&A support



## 📁 Project Structure
```text
├── AeroFlow_Specification_Document.pdf
├── EcoSprint_Specification_Document.pdf
├── routing_agent_llamaindex.ipynb
├── README.md
└── LICENSE.txt
```



## 🧱 Requirements

- Python ≥ 3.8
- `llama-index`
- `nest_asyncio`
- `huggingface_hub`
- `groq` API Key
- Google Colab or local Jupyter environment



## 🔧 Setup Instructions
1. **Upload PDF documents:** Place AeroFlow_Specification_Document.pdf and EcoSprint_Specification_Document.pdf in the working directory or Colab file manager.

2. **Set up API Keys:**

```python
from google.colab import userdata
Settings.llm = Groq(model="llama3-70b-8192", api_key=userdata.get('GROQ_API_KEY'))
```

3. **Configure Embedding & LLM:**

```python
from llama_index.embeddings.huggingface import HuggingFaceEmbedding
Settings.embed_model = HuggingFaceEmbedding(model_name="BAAI/bge-small-en-v1.5")
```

4. **Create Document Indexes:**

- Read, chunk, and index each document (AeroFlow and EcoSprint)

- Create individual query engines

5. **Route Queries Using Router Agent:**

- Automatically select the appropriate document source using RouterQueryEngine

- Example queries:

```python
response = router_agent.query("What colors are available for AeroFlow?")
print(response)

response = router_agent.query("What colors are available for EcoSprint?")
print(response)
```



## 🤖 Technologies Used
- LlamaIndex

- Groq (LLaMA3-70B)

- HuggingFace Transformers

- Google Colab

- Python



## 📌 Sample Use Case
🔍 Ask: "What colors are available for AeroFlow?"
✅ The agent routes the query to the AeroFlow specification index and provides a relevant, grounded answer.

---

## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE.txt) file for details.



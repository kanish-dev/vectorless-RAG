
# Vectorless RAG with PageIndex

Traditional RAG systems rely on embeddings and vector similarity search, which often struggle with document structure, context loss, and "vibe-based" retrieval. This repository implements **Vectorless RAG**, a reasoning-based approach using the **PageIndex** framework to navigate documents hierarchically—just like a human would.

## 🚀 Overview

Instead of splitting documents into arbitrary chunks and converting them into mathematical vectors, this project uses **PageIndex** to:

1. **Index by Structure:** Create a hierarchical "Table of Contents" tree of the document.
2. **Reason-Based Retrieval:** Use an LLM to navigate the tree nodes based on summaries and titles.
3. **Precise Extraction:** Retrieve only the exact sections needed to answer a query, preserving context and reducing noise.

### Why Vectorless?

* **No Vector Database:** Eliminates the need for Pinecone, Milvus, or Chroma.
* **Zero Embeddings:** No more "nearest neighbor" guesswork; retrieval is based on structural reasoning.
* **High Traceability:** Every answer can be traced back to a specific node/section in the document.
* **Perfect for Long Docs:** Ideal for financial reports, legal contracts, and technical manuals where structure matters.

---

## 📁 Repository Structure

* `pageindex_Vectorless_RAG.ipynb`: The main Jupyter Notebook containing the implementation logic.
* `sample_document.pdf`: A sample PDF used for demonstrating the retrieval capabilities.
* `outputs/`: Directory containing generated outputs and reasoning traces.
* `.gitignore`: Standard Python/Jupyter ignore rules.

---

## 🛠️ Getting Started

### Prerequisites

* Python 3.10+
* An API Key from [dash.pageindex.ai](https://dash.pageindex.ai/)
* An OpenAI API Key (or your preferred LLM provider)

### Installation

Clone the repository and install the required dependencies:

```bash
git clone https://github.com/kanish-dev/vectorless-RAG.git
cd vectorless-RAG
pip install pageindex openai python-dotenv

```

### Usage

1. Open `pageindex_Vectorless_RAG.ipynb` in your preferred editor (VS Code or Jupyter Lab).
2. Set your environment variables:
```python
PAGEINDEX_API_KEY = "your_pageindex_key"
OPENAI_API_KEY = "your_openai_key"

```


3. Run the cells to:
* Upload `sample_document.pdf`.
* Generate the structural tree index.
* Perform a reasoning-based query.



---

## 🧠 How it Works

| Feature | Traditional Vector RAG | Vectorless RAG (This Repo) |
| --- | --- | --- |
| **Search Method** | Cosine Similarity (Math) | Hierarchical Reasoning (Logic) |
| **Storage** | Vector Database | Document Tree Index |
| **Chunking** | Fixed-size (e.g., 512 tokens) | Natural (Sections/Headings) |
| **Accuracy** | High for "vibes" | High for specific facts/structure |

---

## </> Outputs
<img width="549" height="418" alt="document tree structure" src="https://github.com/user-attachments/assets/e6b75211-17a4-4c32-a81c-88d8e1522ce2" />
<img width="850" height="370" alt="query seraching in vectorless rag" src="https://github.com/user-attachments/assets/51876eb4-3c3d-4ec8-818a-6ce1470bb69e" />
<img width="689" height="355" alt="finding answers for multiple queries" src="https://github.com/user-attachments/assets/84bd6774-0c37-4863-bedb-6940e9351c6c" />



## 🤝 Contributing

Contributions are welcome! If you have ideas for improving the retrieval logic or adding more sample documents, feel free to open an issue or submit a pull request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](https://www.google.com/search?q=LICENSE) file for details.

---

**Built with ❤️ by [Kanishka R Reddy](https://github.com/kanish-dev)**

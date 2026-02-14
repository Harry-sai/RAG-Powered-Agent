# 🤖 RAG-Powered Agent

A Retrieval-Augmented Generation (RAG) system built for the **Insurellm** use case.

This project combines semantic search with a large language model to generate answers grounded in internal company knowledge. Instead of relying purely on the LLM’s memory, the system retrieves relevant documents first and then generates responses based on that context.

The result:
✔ More accurate answers
✔ Reduced hallucination
✔ Transparent source context

---

# 🧠 How the System Works

### 1️⃣ User Query

A user asks a question through the Gradio chat interface.

### 2️⃣ Retrieval

The system:

* Converts the question into embeddings
* Searches a vector database
* Retrieves the most relevant document chunks

### 3️⃣ Augmented Generation

The retrieved context is injected into the LLM prompt.

### 4️⃣ Grounded Answer

The model generates an answer strictly based on the retrieved information.

Each answer also displays the **relevant context source**, so users can see where the information came from.

---

# 🚀 Running the Application

## ▶ Run the Chat App

From the root directory:

```bash
python app.py
```

This will launch a Gradio interface in your browser.

You can now:

* Ask questions
* See retrieved context
* Inspect grounded responses

---

## 📊 Run the Evaluation Dashboard

```bash
python evaluator.py
```

This launches a separate Gradio dashboard that evaluates both:

* Retrieval performance
* Answer quality

---

# 📈 Evaluation System Explained

The evaluation framework measures two major components of RAG:

---

## 🔎 1. Retrieval Evaluation

This measures how well the system retrieves the correct documents.

Metrics:

### • Mean Reciprocal Rank (MRR)

Measures how early the correct document appears in search results.
Higher = better ranking quality.

### • Normalized Discounted Cumulative Gain (nDCG)

Measures ranking quality considering position and relevance.

### • Keyword Coverage

Checks whether important query keywords appear in retrieved documents.

---

### Retrieval Dashboard Example

<img width="1688" height="767" alt="Screenshot 2025-12-28 000559" src="https://github.com/user-attachments/assets/2a60ab93-7c18-4d93-8184-6e478b082b93" />


The bar chart shows performance across categories like:

* direct_fact
* temporal
* comparative
* numerical
* relationship
* spanning
* holistic

---

## ✍ 2. Answer Evaluation

This measures the quality of generated answers.

Metrics:

### • Accuracy (0–5)

Is the answer factually correct?

### • Completeness (0–5)

Does it fully answer the question?

### • Relevance (0–5)

Is the response directly addressing the query?

---

### Answer Evaluation Dashboard

<img width="1646" height="551" alt="Screenshot 2025-12-28 012507" src="https://github.com/user-attachments/assets/b72aadcd-b468-4d21-8ea4-04cbddd7b63e" />


Scores are averaged per category and color-coded for quick diagnosis.

---

# 🧪 Evaluation Flow

When you click **“Run Evaluation”**:

1. A predefined test dataset is executed.
2. Each question:

   * Runs through the RAG pipeline
   * Retrieves documents
   * Generates answers
3. Metrics are computed automatically.
4. Results are visualized with charts and summary cards.

The dashboard reports:

* Overall retrieval strength
* Weak categories
* Answer quality distribution
* Total tests executed

This helps identify:

* Embedding weaknesses
* Chunking problems
* Prompt issues
* Category-specific performance gaps

---

# 📂 Project Structure

```
RAG-Powered-Agent/
│
├── app.py                 # Main RAG chat application
├── evaluator.py           # Evaluation dashboard
├── implementation/        # RAG pipeline logic
├── vector_database/       # Embeddings + semantic search index
├── knowledge-base/        # Source documents
├── evaluator/             # Test datasets & evaluation logic
└── requirements.txt
```

---

# 🎯 What This Project Demonstrates

* End-to-end RAG pipeline
* Semantic search using vector embeddings
* Context-grounded LLM generation
* Structured evaluation framework
* Category-based performance analysis
* Interactive dashboards for diagnostics

This is not just a chatbot —
it’s a measurable, testable RAG system.


Tell me what you want next.

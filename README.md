# Graph-Augmented Lightweight RAG with Relevance Grading for Low-Resource Environments

This project presents a lightweight graph-augmented Retrieval-Augmented Generation (RAG) approach designed for environments with limited computational resources.

The goal is to improve document retrieval quality while maintaining a simple and efficient architecture, inspired by GraphRAG but significantly less computationally expensive.

Traditional retrieval approaches often face limitations such as the difficulty retrieving the most relevant context, the limited token windows for LLMs, and the high computational costs in advanced systems. This project proposes a graph-based retrieval expansion strategy combined with a relevance grading step to improve the quality of retrieved information.

The retrieval pipeline works as follows:

1. **Dense Retrieval**
   The system first retrieves a set of *seed chunks* using dense embeddings.

2. **Graph Expansion**
   A text/concept graph connects document chunks through shared concepts.
   Retrieved seed chunks are expanded by exploring connected chunks in the graph.

3. **Relevance Grading**
   A MiniLM cross-encoder evaluates the relevance between the query and candidate chunks.

4. **Answer Generation**
   The top-ranked chunks are provided as context to the language model to generate the final answer.

The system is evaluated on a small benchmark built from the CIA World Factbook.

* 10 country documents
* documents divided into section-based chunks
* factoid-style question answering task

Evaluation focuses on:

* answer correctness
* evidence recall

The proposed approach is compared with two standard retrieval methods:

* **BM25** (keyword-based retrieval)
* **Dense retrieval** using neural embeddings

The lightweight graph-augmented approach  improves retrieval and answer accuracy compared to the baselines, demonstrating that graph-based expansion can enhance RAG systems even in low-resource settings.

Davide Altieri

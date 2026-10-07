# Retrieval-Augmented Generation (RAG) Pipeline

This document explains the high-level Retrieval-Augmented Generation (RAG) workflow used in the Mental Wellbeing Chatbot project.

The goal of the RAG system was to improve response grounding and reduce hallucinated AI responses by retrieving information from authorized mental wellbeing reference material.

Due to a non-disclosure agreement (NDA) signed with the project supervisor, implementation details and source code are intentionally excluded.

> **Ownership note:** The RAG pipeline was implemented by my project partner, using AI-assisted coding tools. My role was reviewing the code, agreeing on design choices such as chunk size, and manually testing the pipeline's behaviour. This document explains how the pipeline works, based on course instruction and my partner's walkthrough of her implementation.
>
> RAG was an optional extension in the project's fourth and final milestone, which we added for learning.

---

# Why RAG Was Used

Large Language Models can sometimes generate inaccurate or unsupported responses.

Because this project focused on mental wellbeing support, the application used RAG to:
- improve response reliability
- provide more grounded responses
- reduce hallucinated outputs
- limit responses to authorized wellbeing-related contexts

---

# High-Level Workflow

1. Mental wellbeing reference material was split into text chunks (we tested and agreed on a chunk size that gave the best retrieval results)
2. Each chunk was converted into a vector embedding and stored in the database
3. Each user query was converted into an embedding with the same model
4. Similarity search compared the query embedding with the stored embeddings by vector distance and retrieved the **top 3** closest chunks
5. The retrieved chunk text and the user's question were combined into a prompt, together with a predefined set of response rules (following guidelines from our professor)
6. The language model generated a grounded response, following those rules and the retrieved context

This helped the chatbot provide more context-aware and reliable responses.

---

# Domain-Constrained Responses

The chatbot was intentionally designed to respond only within authorized mental wellbeing-related contexts.

If users submitted unrelated prompts, the chatbot responded within its defined boundaries instead of generating unrestricted answers.

**How I tested this:** I sent off-topic prompts and confirmed the chatbot stayed within its defined scope instead of answering freely (see the *Domain-Constrained Responses* screenshot in the README).

This supported:
- safer AI-assisted interactions
- ethical AI behavior
- more reliable response generation

---

# Key Learnings

This project strengthened understanding of:
- Retrieval-Augmented Generation (RAG)
- vector embeddings
- semantic similarity search
- grounded AI response generation
- AI-assisted application workflows
- ethical AI system design

---

# Repository Notice

This repository intentionally excludes:
- source code
- datasets
- embedding configurations
- internal prompts
- protected project materials

This repository exists strictly for educational and portfolio demonstration purposes.

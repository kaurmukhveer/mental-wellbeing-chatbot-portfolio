# Retrieval-Augmented Generation (RAG) Pipeline

This document explains the high-level Retrieval-Augmented Generation (RAG) workflow used in the Mental Wellbeing Chatbot project.

The goal of the RAG system was to improve response grounding and reduce hallucinated AI responses by retrieving information from authorized mental wellbeing reference material.

Due to NDA and academic project restrictions, implementation details and source code are intentionally excluded.

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

1. Mental wellbeing reference material was divided into smaller text chunks
2. Text chunks were converted into vector embeddings
3. User queries were also converted into embeddings
4. Similarity search retrieved the most relevant contextual information
5. Retrieved context was added to the AI prompt
6. The language model generated grounded responses using the retrieved context

This helped the chatbot provide more context-aware and reliable responses.

---

# Domain-Constrained Responses

The chatbot was intentionally designed to respond only within authorized mental wellbeing-related contexts.

If users submitted unrelated prompts, the chatbot responded within its defined boundaries instead of generating unrestricted answers.

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

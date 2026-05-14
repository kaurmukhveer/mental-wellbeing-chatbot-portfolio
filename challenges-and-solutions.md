# Challenges and Solutions

This document summarizes some of the key challenges encountered during the development of the Mental Wellbeing Chatbot project and the approaches used to address them.

---

# Secure Authentication

## Challenge
The application required secure multi-user authentication and protected session handling.

## Solution
A custom JWT-based authentication workflow was implemented using:
- middleware authorization
- bcrypt password hashing
- cookie-based session management

This improved understanding of backend security and session handling.

---

# Persistent User Sessions

## Challenge
Users needed persistent and isolated conversation history across sessions.

## Solution
Database-backed session handling allowed users to:
- revisit conversations
- rename chat sessions
- delete sessions
- maintain persistent chat history

---

# Grounded AI Responses

## Challenge
AI responses needed to remain relevant and avoid hallucinated outputs.

## Solution
A Retrieval-Augmented Generation (RAG) workflow retrieved relevant contextual information before generating responses.

The chatbot was also restricted to authorized mental wellbeing-related contexts.

---

# Modular Development

## Challenge
Managing frontend, backend, authentication, and AI workflows became increasingly complex during development.

## Solution
A modular layered architecture separated:
- frontend UI
- backend APIs
- authentication middleware
- business logic
- database interaction

This improved maintainability and testing workflows.

---

# Team Collaboration

The project was developed collaboratively using:
- sprint-style workflows
- iterative testing
- collaborative debugging
- incremental feature integration

AI-assisted development tools were also used selectively during development.

---

# Key Learnings

This project strengthened understanding of:
- backend engineering
- authentication workflows
- modular software design
- Retrieval-Augmented Generation (RAG)
- REST API integration
- collaborative software development
- ethical AI-assisted systems

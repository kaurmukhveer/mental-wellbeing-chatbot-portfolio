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

# Cross-Origin Session Cookies in Production

## Challenge
After deployment, login returned **200 OK** and set a session cookie, but the next request to `/auth/me` returned **401 Unauthorized**. Everything worked locally.

## Investigation
Using browser DevTools, I inspected the request and response headers, the `Set-Cookie` behaviour, and the network traffic. The cookie was being set but not sent back on later requests. The root cause: the Netlify frontend and the Render backend were on different domains, so browser cross-site cookie policies blocked the cookie, even with `SameSite=None; Secure` configured.

## Solution
I routed frontend API calls through a Netlify `/api` proxy that redirects `/api/*` to the Render backend. The browser now treats API requests as same-origin, so the session cookie is sent normally and its HTTP-only and Secure protections are unchanged.

## Lesson
A local environment can hide production-only problems such as cross-origin behaviour. Tracing the actual request and response headers found the cause faster than guessing.

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

My partner used AI-assisted coding tools to build the frontend and the RAG component. I reviewed and tested that code before it was integrated.

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

# Engineering Decisions

This document summarizes some of the major engineering and architectural decisions made during the development of the Mental Wellbeing Chatbot project.

The project focused on building a secure, modular, and maintainable AI-assisted web application while balancing simplicity, scalability, and ethical AI interaction.

---

# Why React + Vite?

The frontend was developed using React and Vite to support:
- component-based UI development
- fast frontend iteration
- maintainable interface structure
- responsive user interactions

React simplified the management of reusable UI components, while Vite provided a lightweight and efficient frontend development workflow.

---

# Why Node.js + Express?

The backend was developed using Node.js and Express because they provided:
- lightweight REST API development
- efficient frontend-backend integration
- modular routing structure
- simple request handling workflows

This stack supported rapid iteration while maintaining clear backend organization.

---

# Why Use a Modular Layered Architecture?

The application was designed using a layered architecture separating:
- frontend UI
- API routing
- authentication middleware
- business logic
- database operations
- AI-assisted workflows

This separation improved:
- maintainability
- debugging
- scalability
- component isolation
- testing workflows

The modular structure also made it easier to update components independently without affecting unrelated parts of the system.

---

# Why Implement Custom Authentication?

Instead of relying entirely on third-party managed authentication services, the project implemented a custom JWT-based authentication workflow.

This decision provided deeper learning and hands-on experience with:
- authentication middleware
- secure session handling
- JWT validation
- password hashing
- user authorization workflows

The authentication system used:
- JWT token validation
- bcrypt password hashing and salting
- cookie-based session management
- middleware authorization layers

This approach strengthened understanding of backend security concepts and user session management.

---

# Why Use Retrieval-Augmented Generation (RAG)?

The project implemented Retrieval-Augmented Generation (RAG) to improve response grounding and reduce hallucinated AI outputs.

Instead of allowing unrestricted responses, the system:
- retrieved context from authorized mental wellbeing reference material
- performed similarity-based context retrieval
- injected relevant context into prompts before response generation

This approach improved:
- contextual relevance
- response grounding
- response consistency
- safer AI-assisted interactions

The chatbot was intentionally restricted to responding within authorized mental wellbeing-related contexts.

---

# Why Persistent Chat Sessions?

Persistent chat sessions were implemented to improve user experience and maintain conversation continuity across sessions.

Users were able to:
- revisit previous conversations
- rename sessions
- delete sessions
- maintain long-term conversation history

This required secure user-specific data handling and session isolation within a multi-user environment.

---

# Why Emphasize Ethical AI Design?

Because the project involved mental wellbeing support, ethical system behavior was considered important throughout development.

The application included:
- clear disclaimers
- domain-constrained responses
- grounded retrieval workflows
- restricted response scope

The chatbot was intentionally designed as a supportive educational tool rather than a replacement for professional healthcare services.

---

# Development Approach

The project was developed collaboratively using an iterative sprint-style workflow.

Development practices included:
- modular incremental development
- component-level testing
- collaborative debugging
- iterative feature refinement
- agile-inspired sprint planning

AI-assisted development tools were also used selectively to support frontend implementation and workflow acceleration.

---

# Key Engineering Lessons

This project strengthened understanding of:
- fullstack application architecture
- backend engineering concepts
- authentication workflows
- modular software design
- REST API communication
- Retrieval-Augmented Generation (RAG)
- scalable system organization
- collaborative software development
- engineering tradeoff analysis
- ethical AI-assisted systems

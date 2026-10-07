# Security Design

This document summarizes the high-level security concepts and authentication design decisions used during the development of the Mental Wellbeing Chatbot project.

The goal of the system was to provide secure multi-user interaction while protecting user sessions, credentials, and conversation history.

Due to a non-disclosure agreement (NDA) signed with the project supervisor, implementation-level details and source code are intentionally excluded.

> **My role:** I implemented the backend authentication layer described here: JWT handling, bcrypt password hashing, HTTP-only cookie sessions, and the authentication middleware.

---

# Authentication Strategy

Instead of relying entirely on third-party managed authentication systems, the project implemented a custom authentication workflow to better understand backend security architecture and session management.

The authentication workflow included:
- JWT-based session validation
- middleware authorization
- password hashing and salting
- secure cookie handling
- user-specific session isolation

This approach provided hands-on experience with backend authentication concepts and secure API workflows.

---

# JWT-Based Session Validation

JSON Web Tokens (JWT) were used to manage authenticated user sessions.

At a high level:
1. Users authenticated through secure login workflows
2. JWT tokens were generated after successful authentication
3. Tokens were securely validated through middleware
4. Protected routes required valid authentication state

Tokens were stored in **HTTP-only cookies** (with `secure` and `sameSite` settings), so client-side JavaScript cannot read them. This reduces the risk of token theft through cross-site scripting (XSS).

This workflow helped maintain secure session handling across the application.

---

# Password Security

User passwords were never stored in plain text.

The application used:
- bcrypt hashing with per-password salts
- storage of password hashes only (hashing is one-way, so the original password cannot be recovered)

This protects user credentials even if the database is exposed.

---

# Middleware Authorization

Authentication middleware was used to:
- validate user authentication state
- restrict unauthorized access
- protect secured API routes
- isolate user-specific data access

This layered structure improved backend organization and centralized security validation workflows.

---

# Secure Multi-User Architecture

The application supported multiple users simultaneously while maintaining user-specific data separation.

Security considerations included:
- isolated user conversation history
- protected session management
- secure account deletion workflows
- controlled access to persistent chat data

The system was designed to ensure users could only access their own conversation history and sessions.

---

# Environment Configuration

Sensitive configuration values were managed using environment variables instead of hardcoded credentials.

This included:
- API configuration values
- database connection settings
- authentication-related configuration

This approach improved security and deployment flexibility.

---

# CORS and API Protection

Cross-Origin Resource Sharing (CORS) configuration was used to control which origins could call the backend API.

In production, the frontend (Netlify) and backend (Render) ran on different domains, and browser cross-site cookie policies blocked the session cookie. This was resolved by routing API calls through a same-origin Netlify `/api` proxy, which kept the cookie's HTTP-only and Secure protections intact (see [challenges-and-solutions.md](challenges-and-solutions.md)).

The backend architecture also separated:
- routing logic
- middleware validation
- business logic
- database operations

This separation improved maintainability and reduced tightly coupled security workflows.

---

# Ethical Security Considerations

Because the application focused on mental wellbeing support, protecting user privacy and maintaining responsible AI-assisted interactions were considered important throughout development.

The project emphasized:
- secure session handling
- responsible response generation
- user-specific data isolation
- ethical AI interaction boundaries

---

# Key Security Learnings

This project strengthened understanding of:
- JWT authentication workflows
- middleware authorization
- password hashing and salting
- session management
- backend API security
- secure multi-user systems
- environment-based configuration
- layered backend architecture
- secure frontend-backend communication

---

# Repository Notice

This document intentionally excludes:
- source code
- authentication secrets
- deployment credentials
- environment variables
- internal implementation logic
- protected project materials

This repository exists strictly for educational and portfolio demonstration purposes.

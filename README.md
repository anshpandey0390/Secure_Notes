# 🛡️ Secure Notes Application

**Enterprise-Grade Security Meets Intelligent Note-Taking.**

Secure Notes is a full-stack, highly secure note-taking application designed to provide users with a private, collaborative, and data-driven environment. Built with modern software engineering principles, it goes beyond basic CRUD operations by integrating advanced behavioral analytics, optimistic locking for real-time collaboration, and proactive security monitoring.

---

## ✨ Core Features & Complex Logic

This project implements three major Complex Logic (CL) components that demonstrate advanced algorithmic design, data-driven decision making, and multi-step workflows.

### 1. Data-Driven Activity Analysis (CL-1)
* **Iterative Streak Detection:** A custom algorithm calculates user engagement by tracking consecutive days of note creation.
* **Dynamic Rule Evaluation:** Evaluates user metrics (e.g., average character count, total notes) against predefined thresholds to generate activity insights.
* **Real-Time Dashboard:** Displays analytics directly to the user, turning raw database metrics into actionable visual data.

### 2. Collaborative Editing & Conflict Resolution (CL-2)
* **Optimistic Locking:** Implements a "Latest Wins + Version History" strategy to handle concurrent modifications by multiple users on the same note.
* **Data Preservation:** If a version conflict is detected, the system archives the previous version to a `NoteHistory` table before applying the new state, ensuring zero data loss.
* **Third-Party Integration:** Automatically triggers a formatted HTML email via `JavaMailSender` to notify users when they have been invited to collaborate.

### 3. Security-Oriented Behavior Monitoring (CL-3)
* **Context-Aware Authentication:** Tracks and logs sensitive security events like failed logins and password reset requests.
* **Temporal Thresholds:** Evaluates user behavior over time (e.g., limiting password resets to 3 per hour).
* **Automated Mitigation:** Applies conditional branching to trigger controlled responses, such as temporary account restrictions or warning states, actively preventing brute-force attacks.

### 🔒 Additional Security Features
* **Stateless Authentication:** JSON Web Tokens (JWT) for secure session management.
* **Password Cryptography:** BCrypt hashing and salting for all stored credentials.
* **Audit Logging:** Comprehensive tracking of note creation, updates, and deletions.
* **Role-Based Access Control (RBAC):** Strict separation between standard Users and System Administrators.

---

## 🛠️ Tech Stack

**Frontend (Client-Side)**
* **React.js** - UI Library
* **Tailwind CSS** - Utility-first styling
* **Framer Motion** - Advanced UI animations
* **Material UI (MUI)** - Data grids and tooltip components
* **Axios** - API communication

**Backend (Server-Side)**
* **Java 17 & Spring Boot 3** - Core backend framework
* **Spring Security & JWT** - Authentication and authorization
* **Spring Data JPA (Hibernate)** - ORM and database management
* **JavaMailSender** - Automated email dispatch

**Database**
* **MySQL / PostgreSQL** - Relational data storage

---

## 📂 Project Architecture

This repository uses a monorepo structure containing both the frontend and backend environments:

```text
Secure_Notes/
├── backend/                  # Spring Boot Application
│   ├── src/main/java/...     # Controllers, Models, Repositories, Services
│   ├── src/main/resources/   # application.properties, static assets
│   └── pom.xml               # Maven dependencies
│
└── frontend/                 # React Application
    ├── public/               # index.html, manifest
    ├── src/                  # Components, Context API, utils
    ├── package.json          # Node dependencies
    └── tailwind.config.js    # Tailwind configuration

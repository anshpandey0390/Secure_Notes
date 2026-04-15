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

🚀 How to Run the Project Locally
Prerequisites
Before you begin, ensure you have the following installed on your machine:

Java Development Kit (JDK) 17 or higher

Node.js (v16 or higher) and npm

MySQL Server (Running locally on port 3306)

A code editor (IntelliJ IDEA for backend, VS Code for frontend)

Step 1: Database Setup
Open your MySQL client (e.g., MySQL Workbench).

Create a new database named securenotes:

SQL
CREATE DATABASE securenotes;

Step 2: Backend Setup
Open your terminal and navigate to the backend folder:

Bash
cd backend
Open src/main/resources/application.properties and configure your credentials:

Properties
# MySQL Credentials
spring.datasource.username=YOUR_MYSQL_USERNAME
spring.datasource.password=YOUR_MYSQL_PASSWORD

# Email Configuration (For Collaboration & Password Resets)
spring.mail.username=YOUR_GMAIL_ADDRESS
spring.mail.password=YOUR_GMAIL_APP_PASSWORD

# JWT Secret (Generate a strong 256-bit string)
spring.app.jwtSecret=YOUR_SUPER_SECRET_JWT_KEY
Run the Spring Boot application:

Bash
./mvnw spring-boot:run
(The backend server will start on http://localhost:8080)

Step 3: Frontend Setup
Open a new terminal window and navigate to the frontend folder:

Bash
cd frontend
Install the necessary Node modules:

Bash
npm install
Start the React development server:

Bash
npm start
(The application will automatically open in your browser at http://localhost:3000)

🤝 Usage Guide
Sign Up: Create a new account via the /signup route.

Create a Note: Use the Rich Text Editor to format and save a secure note.

Collaborate: Click the "Share" icon on any of your notes and enter a colleague's email. They will receive an automated email invitation.

Test Conflict Resolution: Open the shared note in two different browsers. Edit them simultaneously and watch the backend archive the older version to the NoteHistory table while accepting the newest edit.

View Analytics: Navigate to the "My Notes" dashboard to see the live output of the CL-1 Activity Algorithm.

  # Arbor — Document Version Control System

  A web-based document management platform with structured version control, role-based access, and a review workflow
  for teams.

  Built as a university project and deployed on Google Cloud Platform.

  ---

  ## Overview

  Arbor allows teams to create, version, and review documents through a structured approval process. Authors submit
  documents, reviewers approve or reject versions with comments, and admins manage users and roles — all through a
  clean, responsive web interface.

  ---

  ## Features

  | Feature | Description |
  |---|---|
  | Role-based access | Reader, Author, Reviewer, Admin — each with tailored permissions |
  | Document versioning | Every edit creates a new version submitted for review |
  | Review workflow | Reviewers approve or reject versions with inline comments |
  | Diff viewer | Side-by-side comparison of new vs previous version |
  | Role requests | Users can request a role upgrade, admins approve or reject |
  | Light / Dark theme | Full theme support across all components |
  | Responsive UI | Works on desktop and mobile |

  ---

  ## Tech Stack

  **Frontend**
  - React 19 + Vite
  - React Router v7
  - CodeMirror 6 (markdown editor + diff viewer)
  - CSS custom properties (no UI library)
  - Deployed on **Vercel**

  **Backend**
  - Java + Javalin
  - JWT authentication
  - BCrypt password hashing
  - Deployed on **Google Cloud Run**

  **Database**
  - MySQL on **Google Cloud SQL**

  ---

  ## Repository Structure

  arbor-vcs/
  ├── frontend/        → React frontend (submodule)
  ├── backend/         → Java backend (submodule)
  ├── database/        → SQL schema
  └── docs/            → User manual, technical documentation, architecture diagram

  ---

  ## Architecture

  See [`docs/`](./docs/) for the full architecture diagram and technical documentation.

  ---

  ## Getting Started

  ### Prerequisites
  - Node.js 18+
  - Java 23
  - Maven
  - MySQL

  ### Frontend
  ```bash
  cd frontend
  npm install
  npm run dev

  Backend

  cd backend
  mvn package
  java -jar target/app.jar

  Database

  Run the schema script against your MySQL instance:
  mysql -u root -p < database/schema.sql

  ---
  User Roles

  ┌──────────┬───────────────────────────────────────┐
  │   Role   │              Permissions              │
  ├──────────┼───────────────────────────────────────┤
  │ Reader   │ View approved documents               │
  ├──────────┼───────────────────────────────────────┤
  │ Author   │ Create documents, submit new versions │
  ├──────────┼───────────────────────────────────────┤
  │ Reviewer │ Approve/reject versions, add comments │
  ├──────────┼───────────────────────────────────────┤
  │ Admin    │ Full access to all features           │
  └──────────┴───────────────────────────────────────┘

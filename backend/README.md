# Backend - Student Research Group Manager

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Installation](#-installation)


---

## 🌟 Overview

This backend provides a complete REST API for managing students, professors, research groups, and mentorship relationships. It includes JWT authentication, role-based access control, and real-time features like notifications and group chat.

**Key Capabilities:**
- User management with three roles (Admin, Student, Professor)
- Group creation and membership management
- Mentorship request workflow
- Real-time chat with read receipts
- Notification system for all user actions
- Bulk import via CSV

---

## 🛠️ Tech Stack

- **Framework**: FastAPI 0.100+ (async Python web framework)
- **ORM**: SQLAlchemy 2.0+ (SQL toolkit and ORM)
- **Database**: PostgreSQL 15+ (relational database)
- **Migrations**: Alembic (database version control)
- **Auth**: JWT tokens with python-jose
- **Password Hashing**: bcrypt via passlib
- **Validation**: Pydantic v2 (data validation)
- **CORS**: FastAPI CORS middleware

---

## 📦 Installation

### Prerequisites

- Python 3.9 or higher
- PostgreSQL 15 or higher
- pip (Python package manager)

### Step 1: Clone and Setup Virtual Environment

```bash
cd backend

python -m venv venv

source venv/bin/activate
```

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 3: Configure Database

Edit `alembic.ini` and set your PostgreSQL connection:

```ini
sqlalchemy.url = postgresql://username:password@localhost:5432/student_manager
```

**Create the database:**

```bash
# Using psql
psql -U postgres
CREATE DATABASE student_manager;
\q
```

### Step 4: Run Migrations

```bash
# Apply all migrations
alembic upgrade head
```
### Step 5: Start Server

```bash
# Development mode (auto-reload)
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

**API will be available at:**
- Base URL: `http://localhost:8000`
- Swagger Docs: `http://localhost:8000/docs`

The Operator Platform

The Operator is a high-performance Context Management System (CMS) designed to eliminate "context drift" for software engineers and day traders.

Unlike standard productivity tools that enforce rigid structures, The Operator uses a Polymorphic Data Architecture to unify diverse data shapes—from boolean project tasks to complex financial trade entries—into a single, queryable timeline.

🚀 Key Features

Polymorphic Item Engine: A "Universal Node" architecture using PostgreSQL JSONB to store diverse entity types (Trades, Tasks, Checkpoints) in a single relational table without schema migration fatigue.

Context Checkpoints: A "Save State" system for deep-work projects, allowing developers to restore mental context in seconds after a hiatus.

Trading Journal V1: Integrated trade tracking with R-Multiple calculations and psychological state tagging.

Signal-Based UI: Fully reactive frontend built with Angular Signals for fine-grained performance updates without Zone.js overhead.

🛠 Tech Stack

Frontend (Client)

Framework: Angular 18+ (Standalone Components)

State Management: Angular Signals & RxJS Interop

Styling: Tailwind CSS + Phosphor Icons

Build: Vite / Esbuild

Backend (API)

Framework: Django 5 + Django REST Framework (DRF)

Database: PostgreSQL 16 (Relational + JSONB)

Authentication: JWT (SimpleJWT)

Task Queue: Celery + Redis (Planned for Analytics)

Infrastructure

Containerization: Docker & Docker Compose

CI/CD: GitHub Actions (Linting & Testing)

🏗 Architecture Overview

The system ignores the traditional separation between "Journaling" and "Project Management." Instead, it treats every interaction as an Item with a specific type and a dynamic payload.

```
classDiagram
    Project "1" --> "*" Item : contains
    class Item {
        UUID id
        String type
        JSONB payload
        String status
    }
    class Project {
        UUID id
        String mode
        JSONB settings
    }
```

⚡ Quick Start

Prerequisites

Docker & Docker Compose

Node.js 20+

Installation

Clone the repository

git clone [https://github.com/YOUR_USERNAME/operator-platform.git](https://github.com/YOUR_USERNAME/operator-platform.git)
cd operator-platform


Start the stack (Backend + DB)

docker-compose up -d --build


Start the Frontend

cd frontend
npm install
npm start


Access the API at localhost:8000/api and the UI at localhost:4200.

📝 License

MIT

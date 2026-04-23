# Zenno

Zenno is a developer productivity and wellbeing platform that turns daily coding activity into meaningful insights, progress signals, and supportive nudges.

## Our Mission

We built Zenno to help developers improve focus, reduce burnout risk, and make consistent progress by understanding how work actually happens across tools, projects, and habits.

## What Zenno Does

Zenno combines local activity intelligence with cloud analytics and AI assistance to provide:

- clear visibility into where time goes (apps, projects, languages, contexts)
- personal productivity trends over time
- context-aware nudges for healthier and more focused work sessions
- social and collaboration surfaces (profiles, peers, chat)

## Core Product Features

- **Developer Analytics Dashboard**
  - performance and behavior metrics
  - tool usage and language distribution
  - project and skills insights

- **Context Intelligence**
  - classifies work states like Flow, Debugging, Research, Communication, and Distracted
  - combines heuristic and ML-assisted signals

- **Zenno Agent Nudges**
  - personalized nudges based on recent activity and wellbeing context
  - resilient generation pipeline with fallback behavior

- **Profile and Community**
  - public profile experience
  - peer discovery and engagement
  - direct chat and notifications

- **Cross-Platform Experience**
  - web app
  - mobile app
  - desktop agent runtime

## What We Built

Zenno is delivered as a multi-repository platform:

- `website` - React + Vite frontend for landing pages and product experience
- `mobile_app` - Flutter mobile app for analytics, profile, chat, and notifications
- `desktop-agent` - local Windows agent for activity capture, context detection, and nudge orchestration
- `backend` - NestJS API for auth-protected data, analytics endpoints, chat, notifications, and preferences
- `nlp` - FastAPI-based nudge generation service with local GGUF model runtime and training pipeline
- `.github` - organization-level docs and standards

## Tech Stack and Tools

### Frontend (Web)

- React 18 + TypeScript
- Vite build tooling
- Zustand (state management)
- Axios (API client)
- React Router
- Socket.IO client
- Firebase Web SDK (authentication + web messaging integration)

### Mobile App

- Flutter + Dart
- Riverpod (state management/DI)
- GoRouter (navigation)
- Dio (network layer)
- Firebase Core/Auth/Messaging
- flutter_local_notifications (local notification presentation)
- Socket.IO client

### Backend API

- NestJS 11 + TypeScript
- MongoDB (primary cloud database)
- Mongoose ODM (`@nestjs/mongoose`)
- Firebase Admin SDK (ID token verification)
- Socket.IO gateway (`@nestjs/websockets`)
- Swagger/OpenAPI (`@nestjs/swagger`)
- Schedule/cron jobs (`@nestjs/schedule`)
- Cloudinary integration (profile image uploads)

### Desktop Agent Runtime

- Python
- SQLite (local first data store on user machine)
- pywebview (desktop authentication UI)
- requests + keyring (API + token persistence)
- scikit-learn / XGBoost (context classification path)
- pandas/numpy/joblib (data processing/model utilities)

### NLP / AI Service

- FastAPI + Uvicorn
- Pydantic schemas
- llama-cpp-python (GGUF inference)
- Qwen2.5-0.5B-Instruct GGUF model family
- LoRA fine-tuning and merge/export pipeline

### Authentication and Notifications

- **Authentication:** Firebase Authentication across web, mobile, and desktop flows
- **Push notifications (web):** Firebase Cloud Messaging + service worker
- **Push notifications (mobile):** Firebase Messaging + local notification rendering
- **In-app notifications:** backend-managed notification APIs + unread state + preferences

### Infrastructure, DevOps, and Tooling

- Git + GitHub (multi-repo platform)
- GitHub Actions (CI/CD pipelines)
- Docker + Docker Compose
- AWS EC2 deployment target (current backend + nlp deployment setup)
- npm / Node.js tooling
- Python virtual environments + pip
- Flutter toolchain

## How Zenno Works (At a Glance)

1. Desktop agent captures local activity and behavioral signals.
2. Backend API stores, aggregates, and serves analytics data.
3. NLP service generates nudge text with fallback safety.
4. Website and mobile app present insights, settings, and collaboration flows.
5. Notifications and chat keep users engaged across sessions.

## Current Deployment Endpoints

Current production hosting (as maintained by the Zenno team):

- **Website:** [https://zenno.dev](https://zenno.dev)
- **Backend API docs:** [https://api.zenno.dev/api/docs](https://api.zenno.dev/api/docs)
- **NLP API docs:** [https://nlp.zenno.dev/docs](https://nlp.zenno.dev/docs)

## Repository Documentation

Each repository contains its own detailed technical README with:

- setup and run instructions
- environment variables and secrets guidance
- architecture and module-level details
- CI/CD and deployment specifics (where applicable)

If you want to contribute or deploy a specific component, start with that repo’s README.

---

Last Updated: 2026-04-23

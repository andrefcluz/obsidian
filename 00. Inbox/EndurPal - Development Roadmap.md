---
created: 2025-10-16T19:46
updated: 2025-10-18T09:57
tags:
  - endurpal
---
## 🗺️ **Full Development Roadmap**

### **PHASE 0 — Planning & Foundation**

> Goal: Define the product vision, tech setup, and project structure.

**Key Tasks**
1. **Define core features**
    - User authentication & profiles
    - Training plan management
    - Workout tracking
    - Calendar view
    - Performance metrics
    - Optional: Marketplace / community section
2. **Decide on MVP scope**
    - Focus on the essential value: “Simplified training management for amateur runners.”
    - List features that can wait (social, advanced analytics, etc).
3. **Initial UI/UX exploration (lightweight)**
    - Sketch core flows: login → dashboard → add/edit workout → view stats.
    - Use **Figma** or **Pen & Paper** mockups — no detailed design yet.
    - The goal: a general structure for the app, not pixel-perfect visuals.
4. **Architecture decisions**
    - Frontend: **Next.js + Tailwind CSS**
    - Backend: **FastAPI**
    - Database: **PostgreSQL**
    - Authentication: JWT (FastAPI + NextAuth or custom API tokens)
    - Containerization: **Docker Compose**
    - ORM: SQLAlchemy or Tortoise ORM
    - Optional: **Redis** (for caching / sessions)
5. **Version control & collaboration setup**
    - Create GitHub repo (monorepo or separate backend/frontend repos)
    - Decide branching strategy (main / dev / feature branches).

---

### **PHASE 1 — Environment & Project Setup**

> Goal: Get everything running locally in containers.

**Key Tasks**
1. Initialize FastAPI project
    - Set up basic endpoints (`/health`, `/users`, `/workouts`)
    - Add DB connection (SQLAlchemy models)
    - Configure `.env` for local credentials
    - Dockerize backend
2. Initialize Next.js frontend
    - Scaffold project
    - Integrate TailwindCSS
    - Add routing & placeholder pages
    - Dockerize frontend
3. Configure Docker Compose
    - Combine frontend, backend, and PostgreSQL containers
    - Confirm communication via network (e.g., backend available at `http://api:8000`)
4. Set up basic CI/CD
    - GitHub Actions: build & test
    - Optional: Linter / formatter (Prettier, Black, Ruff, ESLint)

---

### **PHASE 2 — Database & API Design**

> Goal: Model the core data and build the first endpoints.

**Key Tasks**
1. **Database modeling**
    - Entities:
        - `User`
        - `Workout`
        - `TrainingPlan`
        - `ActivityType`
        - `Metrics` (pace, distance, HR, etc.)
    - Relationships: one-to-many between user and plans/workouts.
2. **Implement FastAPI models & schemas**
    - Create Pydantic models for input/output
    - Add CRUD endpoints for each core entity
3. **Authentication system**
    - JWT-based auth
    - `/auth/register`, `/auth/login`, `/auth/me` endpoints
    - Secure routes with dependency injection
4. **Testing**
    - Write unit tests for core models and endpoints
    - Use `pytest` + `httpx` for integration tests

---

### **PHASE 3 — Frontend Integration (Basic UI)**

> Goal: Connect frontend with backend and build a usable prototype.

**Key Tasks**
1. Connect Next.js to backend API
    - Axios or Fetch wrapper for API calls
    - Implement `.env.local` for API URL
2. Implement authentication flow
    - Register / Login pages
    - Store JWT securely (HttpOnly cookie or localStorage, depending on setup)
    - Display user data after login
3. Build core pages (basic layout only)
    - Dashboard with upcoming workouts
    - Workout creation/edit form
    - Calendar view (static or minimal dynamic)
4. Add global state management (optional at first)
    - Start with React Context, later migrate to Zustand or Redux if needed

---

### **PHASE 4 — Core Features**

> Goal: Turn the prototype into a real MVP.

**Key Tasks**
1. **Workout management**
    - Add / edit / delete workouts
    - Filter by date, distance, or type
2. **Calendar / timeline integration**
    - Integrate a simple calendar component (e.g., React Big Calendar)
    - Sync with backend
3. **Metrics tracking & dashboard**
    - Display simple summaries: total distance, avg pace, etc.
    - Add charts using Recharts or Chart.js
4. **User profile & preferences**
    - Update personal data, HR zones, etc.
5. **UI/UX improvements**
    - Apply consistent Tailwind styling
    - Improve navigation and usability

---

### **PHASE 5 — Testing, Performance & Polish**

> Goal: Prepare for production.

**Key Tasks**
1. Write end-to-end tests (Playwright or Cypress).
2. Optimize API queries (indexes, pagination, caching).
3. Add error handling & validation throughout.
4. Improve UI performance (lazy loading, code splitting).
5. Refine design: typography, colors, spacing, dark mode.

---

### **PHASE 6 — Deployment & Launch**

> Goal: Make it live and maintainable.

**Key Tasks**
1. **Docker production setup**
    - Use multi-stage Docker builds for small images
    - Add Nginx reverse proxy
2. **Deploy**
    - Choose host (e.g., Render, Railway, Fly.io, or VPS like Hetzner)
    - Setup CI/CD pipeline for automatic deploys
3. **Monitoring & maintenance**
    - Add uptime monitor (UptimeRobot)
    - Centralized logging (e.g., Logtail, Loki)
    - Add analytics for user activity
4. **Domain & HTTPS**
    - Configure domain and SSL (Cloudflare or Let’s Encrypt)


---

### **PHASE 7 — Post-Launch Iteration**

> Goal: Start user feedback loop & add advanced features.

**Possible next steps**
- Strava/Garmin integration
- Social/community feed
- Marketplace for coaches
- Training plan templates
- AI recommendations (long-term roadmap)

---

## ⚙️ Recommended Order Summary

| Order | Focus Area              | Why                            |
| ----- | ----------------------- | ------------------------------ |
| 1     | Architecture & planning | Avoid future rework            |
| 2     | Backend + DB setup      | Foundation of the system       |
| 3     | Frontend scaffold       | Needed to test API integration |
| 4     | Authentication          | Enables personal data flow     |
| 5     | Core CRUD features      | MVP functionality              |
| 6     | UX refinement           | Once system logic works        |
| 7     | Deployment              | Make it accessible             |
| 8     | Enhancements            | After user validation          |
 
 ---

## 🗺️ Visual Roadmap (High-Level Timeline)

**Phase 0: Planning & Foundation (Week 1-2)**
- Define core features and MVP scope
- Create light UI/UX sketches using Figma or paper for initial layout ideas
- Choose tech stack and architecture
- Create GitHub repo & workflow

**Phase 1: Environment & Setup (Week 3)**
- Initialize FastAPI backend (Dockerized)
- Initialize Next.js frontend (Dockerized)
- Setup PostgreSQL container
- Connect services with Docker Compose
- Add CI/CD + linting

**Phase 2: Database & API Design (Weeks 4-5)**
- Model database entities (User, Workout, TrainingPlan, etc.)
- Build FastAPI CRUD endpoints
- Implement authentication (JWT)
- Write unit & integration tests (pytest)

**Phase 3: Frontend Integration (Weeks 6-7)**
- Connect frontend with backend API
- Implement login/register flow
- Create dashboard & workout form pages
- Integrate basic calendar
- Implement global state management (React Context or Zustand)

**Phase 4: Core Features (Weeks 8-10)**
- Implement workout management CRUD
- Calendar view with filters
- Dashboard metrics (distance, pace, HR)
- Profile & settings pages
- Apply responsive UI with Tailwind

**Phase 5: Testing & Polish (Weeks 11-12)**
- Add end-to-end tests (Playwright/Cypress)
- Optimize API queries and loading times
- Improve validation and error handling
- Refine UI/UX (dark mode, layout consistency)

**Phase 6: Deployment & Launch (Weeks 13-14)**
- Final Docker production setup (multi-stage builds)
- Add Nginx reverse proxy
- Deploy to hosting (Render/Fly.io/Railway)
- Setup HTTPS + custom domain
- Add monitoring & logging

**Phase 7: Post-Launch Iteration (Ongoing)**
- Collect feedback & analytics
- Implement advanced features (Strava/Garmin sync, templates)
- Optimize performance
- Add community & marketplace features

---

## 🧩 Trello Board Template (Desktop-Friendly Copy-Paste)

### List 1 — Planning
- Define MVP scope
- Sketch UI (Figma or paper)
- Choose tech stack
- Create GitHub repo
### List 2 — Setup
- Initialize FastAPI project
- Initialize Next.js project
- Add Docker Compose setup
- Configure CI/CD (GitHub Actions)
### List 3 — Backend
- Model database entities
- Create CRUD endpoints
- Add JWT authentication
- Write tests (pytest)
### List 4 — Frontend
- API connection setup (Axios)
- Login/Register flow
- Dashboard view
- Workout management UI
- Calendar integration
### List 5 — Core Features
- Workout filtering
- Metrics dashboard
- Profile settings
- Responsive design
### List 6 — Testing & Polish
- E2E tests (Playwright/Cypress)
- Performance optimization
- Validation and error UX
- Dark mode & visual polish
### List 7 — Deployment
- Final Docker build setup
- Add Nginx proxy
- Deploy backend & frontend
- Setup domain + SSL
- Add monitoring tools
### List 8 — Future Ideas
- Strava/Garmin integration
- Community features
- AI-based training suggestions
- Marketplace for coaches

---

✅ **Tip:** Copy each bullet as a card in Trello manually. This version avoids Markdown checkbox syntax, so it displays consistently on both desktop and mobile.

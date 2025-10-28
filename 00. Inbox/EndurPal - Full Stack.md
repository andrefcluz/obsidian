---
created: 2025-10-16T20:46
updated: 2025-10-18T10:06
tags:
  - endurpal
---


## 🧱 COMPLETE STACK — Next.js + FastAPI Edition

### 🧩 **1. Frontend Layer (User Interface)**

| Tool                       | Purpose                                       | Cost   |
| -------------------------- | --------------------------------------------- | ------ |
| **Next.js (latest)**       | Handles routes, pages, server-side rendering  | ✅ Free |
| **TypeScript**             | Adds type safety to your React code           | ✅ Free |
| **Tailwind CSS**           | Fast, modern styling with utility classes     | ✅ Free |
| **ShadCN/UI**              | Prebuilt components built on Tailwind + Radix | ✅ Free |
| **Framer Motion**          | Smooth transitions and animations             | ✅ Free |
| **Recharts (or Chart.js)** | Display pace/HR/volume charts                 | ✅ Free |
| **Lucide Icons**           | Clean icon set (SVG-based)                    | ✅ Free |

💡 _Frontend runs independently but communicates with your FastAPI backend via REST (or GraphQL) requests._

---

### ⚙️ **2. Backend Layer (FastAPI)**

|Tool|Purpose|Cost|
|---|---|---|
|**FastAPI**|Main backend framework (Python-based)|✅ Free|
|**Uvicorn**|ASGI server to run FastAPI|✅ Free|
|**SQLAlchemy**|ORM for working with relational databases|✅ Free|
|**Pydantic**|Data validation and serialization|✅ Free|
|**Alembic**|Database migrations (schema changes)|✅ Free|
|**AuthLib / PyJWT**|Manage authentication tokens (JWT-based)|✅ Free|
|**CORS Middleware**|Allow requests from your Next.js frontend|✅ Free|

💡 You’ll expose endpoints like:

`GET /api/workouts POST /api/workouts GET /api/users/me`

Next.js then calls these via `fetch()` or Axios.

---

### 🗄️ **3. Database Layer**

|Tool|Purpose|Cost|
|---|---|---|
|**PostgreSQL**|Reliable relational database|✅ Free (local or free tier cloud)|
|**SQLAlchemy ORM**|Simplifies queries and schema definitions|✅ Free|
|**Alembic**|Database versioning (migrations)|✅ Free|

💡 Alternative for dev/testing: use **SQLite** locally, then switch to PostgreSQL in production.

---

### 🔐 **4. Authentication**

Two main paths depending on how much you want to handle manually:

#### 🅰️ Custom Auth (Full Control)
- Use **FastAPI + PyJWT/AuthLib** to issue JWT tokens
- Store users in your PostgreSQL DB
- Next.js frontend stores token (in cookies or local storage)
- Each API call includes the `Authorization: Bearer <token>` header
#### 🅱️ External Auth Provider
- Use **Auth0** or **Supabase Auth** only for authentication
- Still keep your backend logic in FastAPI
- Simpler and faster to set up

✅ Both options are free to start with.

---

### ☁️ **5. Hosting**

|Service|Purpose|Cost|
|---|---|---|
|**Vercel**|Hosts your Next.js frontend|✅ Free|
|**Railway.app** or **Render.com**|Easy hosting for FastAPI backend|✅ Free tiers|
|**Supabase / Neon.tech / ElephantSQL**|Host your PostgreSQL database|✅ Free tiers|

💡 Example architecture:

`Frontend (Next.js) → hosted on Vercel Backend (FastAPI) → hosted on Render or Railway Database (PostgreSQL) → hosted on Supabase or Neon`

---

### 🔧 **6. Development Tools**

|Tool|Purpose|
|---|---|
|**VS Code**|Code editor|
|**Git & GitHub**|Version control and CI/CD|
|**HTTP Client (Thunder Client, Postman)**|Test backend APIs|
|**Docker**|Optional — containerize backend for consistency|
|**ESLint + Prettier**|Clean code formatting|
|**Figma**|UI/UX mockups (optional)|

---

### 📁 **7. Folder Structure**

#### Frontend (Next.js)

`frontend/  ├─ app/                # Pages & routes  ├─ components/         # UI components  ├─ lib/                # Helpers (API calls, hooks)  ├─ styles/             # Tailwind setup  ├─ public/             # Static files  └─ utils/              # Utility functions`

#### Backend (FastAPI)

```
backend/  
├─ app/  
│   ├─ main.py         # FastAPI entry point  
│   ├─ api/            # Routers (endpoints)  
│   ├─ models/         # SQLAlchemy models  
│   ├─ schemas/        # Pydantic schemas  
│   ├─ core/           # Config, security, etc.  
│   ├─ db/             # Database session & setup  
│   └─ utils/          # Helper functions  
├─ alembic/            # Migrations  
└─ requirements.txt    # Dependencies
```

---

### 🔗 **8. Frontend ↔ Backend Communication**

- The frontend calls the backend like this:
    
```
const res = await fetch(`${process.env.NEXT_PUBLIC_API_URL}/api/workouts`, {   
	headers: {     
		Authorization: `Bearer ${token}`,   
	}, 
}); 
const data = await res.json();
```
    
- Backend responds with JSON (FastAPI automatically serializes Python objects).
    

---

### ✅ **9. Cost Overview (All Free Tiers)**

|Component|Platform|Cost|
|---|---|---|
|Frontend (Next.js)|Vercel|€0|
|Backend (FastAPI)|Render / Railway|€0|
|Database|Supabase / Neon / ElephantSQL|€0|
|Styling/UI|Tailwind + ShadCN + Framer Motion|€0|
|Charts|Recharts / Chart.js|€0|
|Auth|Custom JWT or Supabase/Auth0 free tier|€0|
|GitHub|Repo + deployment integration|€0|

**💰 Total monthly cost:** €0  
_(You’ll only pay when you start having serious traffic or database usage)_

---

### 🚀 TL;DR — Your Final Stack

| Category                | Technology                                         | Notes                             |
| ----------------------- | -------------------------------------------------- | --------------------------------- |
| **Frontend**            | Next.js + TypeScript                               | React-based, fast SSR/SSG         |
| **Styling**             | Tailwind CSS + ShadCN/UI                           | Modern, efficient styling         |
| **Charts & Animations** | Recharts + Framer Motion                           | Visual feedback for users         |
| **Backend**             | FastAPI + Uvicorn                                  | Lightweight, high-performance API |
| **Database**            | PostgreSQL + SQLAlchemy + Alembic                  | Solid relational base             |
| **Auth**                | JWT or Supabase Auth                               | Secure login                      |
| **Hosting**             | Vercel (frontend), Render (backend), Supabase (DB) | Free and scalable                 |
| **Dev Tools**           | VS Code, Docker, GitHub, ESLint, Prettier          | For development workflow          |

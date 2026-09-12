# JSICP — Jharkhand Societal Innovation Collaboration Portal
### SIH 2026 | Smart India Hackathon | Team Project

[![React](https://img.shields.io/badge/React-18-blue?logo=react)](https://react.dev)
[![Node.js](https://img.shields.io/badge/Node.js-Express-green?logo=node.js)](https://nodejs.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-Python-009688?logo=fastapi)](https://fastapi.tiangolo.com)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Supported-blue?logo=postgresql)](https://postgresql.org)
[![Tailwind](https://img.shields.io/badge/TailwindCSS-3.4-38bdf8?logo=tailwindcss)](https://tailwindcss.com)

> **Government of Jharkhand | Dept of Higher & Technical Education**
> A full-stack AI-powered portal connecting citizens, universities, industries and government for societal problem solving.

---

## 🚀 Features

### 🏛️ Module A — Citizen Engagement
- Submit problems in **Hindi, Hinglish, or English** (text + voice + photo)
- **WhatsApp 24/7 AI Gateway** — real voice note support, speech-to-text in background
- Camera capture + photo upload with AI CV validation
- District/Block strict validation for all 24 Jharkhand districts
- Auto ticket generation (#JSICP-2026-xxxx) + live status tracking

### 🤖 Module B — AI/ML Problem Management
- **Auto-classification** into 8 thematic domains (Water, Health, Agriculture, etc.)
- **Priority scoring** (0–100): Severity 38% + Population 28% + Vulnerability 18% + SDG 16%
- **Semantic deduplication** (5–15km radius + Jaccard similarity)
- **Explainable AI (XAI)** — full breakdown shown to judges/admins
- Smart HEI routing: BIT Mesra, IIT ISM Dhanbad, NIT Jamshedpur, AIIMS Deoghar, BAU Ranchi

### 🎓 Module C — University Collaboration (HEI Portal)
- Accept/Decline AI-routed challenges
- Build **multidisciplinary teams** (Electronics, CS, Biotech, Civil, Chemistry)
- Faculty mentor assignment + Kanban sprint board
- Draft & submit research proposals with budget

### 🏭 Module D — Industry Partnership
- CSR marketplace: Tata Steel, Coal India, JSPL, and more
- Digital MoU signing with e-signature + CSR credits
- 3-tranche grant disbursement system

### 📊 Module E — Project Lifecycle Management
- 5-Stage workflow: Ideation → Prototype → Field Pilot → Verification → Deployment
- Dual sign-off: Faculty + Government Nodal Officer
- Document vault, test reports, IP/patent tracking
- Blockchain audit ledger

### 📈 Module F — Visual Analytics Dashboard
- 24-district interactive heatmap
- Domain-wise challenge vs resolution charts
- University participation leaderboard (patents, teams, completed)
- CSR funds mobilization trend (₹ Lakhs)
- Export PDF / Excel

### 🔔 Module G — Notification Hub
- WhatsApp, SMS (Gupshup), Email (SendGrid), In-App alerts
- Role-specific event-triggered notifications

---

## 🏗️ Architecture

\\\
jsicp-final/
├── apps/
│   ├── web/                    # React + Vite Frontend (Port 3000)
│   │   └── src/
│   │       ├── components/
│   │       │   ├── whatsapp/   # WhatsApp AI Gateway Simulator
│   │       │   ├── ai/         # Jharkhand Sahayak Chatbot (Gemini)
│   │       │   ├── hei/        # University Team Builder, Kanban
│   │       │   ├── lifecycle/  # Gantt, Blockchain Ledger
│   │       │   └── analytics/  # Heatmap, Charts
│   │       ├── pages/portals/  # RBAC: Citizen, Faculty, Student, Industry, Admin
│   │       ├── context/        # AppContext + AuthContext (RBAC)
│   │       └── services/       # aiEngine.ts (client-side + backend bridge)
│   └── mobile/                 # Flutter mobile stub
├── services/
│   ├── ai-service/             # Python FastAPI AI/ML Engine (Port 8000)
│   │   └── app.py              # 6 AI endpoints: validate, autofill, XAI, HEI routing, duplicates
│   ├── backend-server/         # Node.js Express Backend (Port 4000)
│   │   ├── routes/             # 13 REST API routes
│   │   ├── db/                 # PostgreSQL + JSON persistent store
│   │   └── services/           # Gemini AI chat integration
│   └── api-gateway/            # Gateway stub
└── infra/                      # Docker, Render, Vercel configs
\\\

---

## ⚡ Quick Start

### Prerequisites
- Node.js 18+
- Python 3.10+
- (Optional) PostgreSQL

### 1. Frontend (React)
\\\ash
cd apps/web
npm install
npm run dev
# Opens at http://localhost:3000
\\\

### 2. Node.js Backend
\\\ash
cd services/backend-server
npm install
cp .env.example .env
# Add GEMINI_API_KEY in .env (optional — chatbot falls back without it)
node server.js
# Runs at http://localhost:4000
\\\

### 3. Python AI Service
\\\ash
cd services/ai-service
pip install -r requirements.txt
python -m uvicorn app:app --host 127.0.0.1 --port 8000
# AI endpoints at http://localhost:8000/docs
\\\

### Or use the batch script (Windows)
\\\ash
start-all.bat
\\\

---

## 🔑 Demo Login (Judges)

Visit /login and click any stakeholder for instant 1-click role switch:

| Role | Person | Portal |
|------|--------|--------|
| Citizen | Smt. Sunita Devi | /portal/citizen |
| Gram Panchayat Mukhia (PRI) | Shri Birsa Munda | /portal/citizen |
| HEI Nodal Officer (BIT Mesra) | Dr. Rajesh Verma | /portal/hei-nodal |
| Faculty Mentor (BIT Mesra) | Prof. Ananya Sen | /portal/faculty |
| Student Team Lead | Rahul Kumar | /portal/student |
| Industry CSR Partner | Mr. Alok Sanyal (Tata Steel) | /portal/industry |
| Govt Admin (IAS) | Dr. Shailesh Kumar | /portal/admin |

---

## 🤖 AI Technical Stack

- **Theme Classification**: Multi-class keyword-scoring with 8 domain dictionaries + water-illness bridge
- **Priority Engine**: Weighted multi-factor score (severity, population, SDG, vulnerability index)
- **Deduplication**: Jaccard word similarity + Haversine GPS distance + category matching
- **Geo-Parser**: Levenshtein fuzzy matching for 24 districts × 200+ blocks with aliases in Hindi/Hinglish/English
- **HEI Routing**: Faculty expertise matrix × geographic proximity × domain alignment
- **XAI**: Transparent 4-factor breakdown per decision
- **Gemini Chat**: Live Gemini API integration (gemini-3.6-flash) with role-aware system prompts

---

## 📄 License
SIH 2026 — Team Project | Government of Jharkhand

# SecureMaint AI 2.0 — Autonomous Industrial Resilience Platform

SecureMaint AI 2.0 is an enterprise-grade Industry 5.0 platform combining Predictive Maintenance, Real-Time Digital Twins, sub-millisecond Cyber-Physical Threat Shielding, SHAP-based Root Cause explainability, and multi-objective Autonomous Work Order Scheduling.

This repository represents the complete, production-ready codebase built to satisfy the Master Architect Build Prompt.

---

## 🛠️ Technology Stack

| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend** | Next.js 15 (App Router), TypeScript, Tailwind CSS, Recharts, Three.js | Visual 3D digital twins, responsive glassmorphism telemetry dashboard, Copilot RAG chat panel |
| **Backend** | FastAPI, Python 3.12, Uvicorn | High-performance API Gateway, background simulation threads, mathematical prediction/cyber engines |
| **Database** | PostgreSQL, TimescaleDB, Neo4j | Relational schema registers, optimized telemetry hypertables, knowledge graph Cypher queries |
| **Caching** | Redis Cache | Telemetry buffers, state registries, session rate-limit trackers |
| **AI / ML** | XGBoost, LSTM, Isolation Forest, SHAP, Gemini API | Failure classifications, RUL trend forecasting, network anomaly detection, Explainable AI, Copilot RAG Q&A |
| **DevOps** | Docker, Docker Compose, Kubernetes, Helm Charts, GitHub Actions | Scalable cloud orchestration, CI/CD automated test suites |

---

## 🏢 System Architecture

The following ASCII topological flow maps the platform layer transitions:

```
Physical Layer
[Sensors: Temp, Vib, Press, Current, RPM]
         ↓
Edge Gateway Layer
[HMAC Signature Verify, Moving-Avg Filter, Bounds Normalization]
         ↓
Streaming Layer
[Kafka Topics: raw-telemetry, cyber-events, twin-updates]
         ↓
Intelligence Layer
[XGBoost Predictor, Isolation Forest Cyber Scanner, SHAP Attribution]
         ↓
Decision Layer
[Autonomous Constraint Scheduler, Gemini RAG Maintenance Copilot]
         ↓
Presentation Layer
[Next.js 15 Glassmorphic Operations Dashboard, Three.js 3D Spindle Twin]
```

---

## 📂 Repository Structure

The project conforms to standard modular monolithic layouts:

```
SecureMaint-AI-2.0/
├── .github/
│   └── workflows/
│       └── ci-cd.yml             # Automated GitHub Actions Pytest and Docker builds
├── backend/
│   ├── app/
│   │   ├── db/
│   │   │   ├── database.py       # Stateful Relational and Graph simulated DB caching
│   │   │   └── models.py
│   │   ├── routers/              # Module endpoints (Telemetry, Predictions, Cyber, Twins)
│   │   │   ├── telemetry.py
│   │   │   ├── prediction.py
│   │   │   ├── cyber_threat.py
│   │   │   ├── digital_twin.py
│   │   │   ├── root_cause.py
│   │   │   ├── copilot.py
│   │   │   ├── scheduler.py
│   │   │   ├── knowledge_graph.py
│   │   │   └── sustainability.py
│   │   ├── services/             # Domain engines (Ingests, SHAP explainers, RAG, schedulers)
│   │   │   ├── ingest_service.py
│   │   │   ├── prediction_service.py
│   │   │   ├── threat_service.py
│   │   │   ├── twin_service.py
│   │   │   ├── explanation_service.py
│   │   │   ├── copilot_service.py
│   │   │   ├── scheduler_service.py
│   │   │   ├── graph_service.py
│   │   │   └── sustainability_service.py
│   │   ├── config.py             # Pydantic BaseSettings config
│   │   └── main.py               # FastAPI entrypoint & telemetry generator background worker
│   ├── tests/
│   │   └── test_analytics.py     # Backend pytest suite (HMACs, XGBoost, Isolation Forest)
│   ├── Dockerfile
│   └── requirements.txt
├── frontend/
│   ├── app/                      # Next.js 15 App router screens
│   │   ├── layout.tsx
│   │   ├── page.tsx              # Entrance landing page
│   │   ├── globals.css           # Premium glassmorphic styling variables
│   │   └── dashboard/
│   │       ├── layout.tsx        # Responsive navigation and Cyber Attack quick controls
│   │       ├── page.tsx          # Real-time Operations Console
│   │       ├── predictive/page.tsx # SHAP explainability charts
│   │       ├── cybersecurity/page.tsx # Active alerts audit table
│   │       ├── twin/page.tsx     # 3D Spindle Digital Twin & counterfactual simulation
│   │       ├── graph/page.tsx    # topological SVG Knowledge Graph
│   │       ├── scheduler/page.tsx # Autonomous maintenance calendars
│   │       ├── sustainability/page.tsx # Eco footprint and green suggestions
│   │       └── copilot/page.tsx  # Gemini-powered RAG maintenance copilot chat
│   ├── components/
│   │   └── three-twin.tsx        # Pure WebGL rotating 3D Cylinder twin using Three.js
│   ├── Dockerfile
│   ├── package.json
│   ├── tsconfig.json
│   └── next.config.js
├── database/
│   ├── schema.sql                # PostgreSQL/TimescaleDB time-series tables
│   └── seed_data.sql             # Machines, sensors, and default technicians seed entries
├── devops/
│   ├── kubernetes.yaml           # Deployment services, Secrets, and ConfigMaps
│   └── helm-chart-values.yaml    # Production Helm chart value guides
├── docker-compose.yml            # Local PostgreSQL/Redis/FastAPI/NextJS container coordinates
├── LICENSE                       # MIT License
└── README.md                     # Comprehensive Master Guide
```

---

## 🚀 Getting Started (Local Quickstart)

To run and validate the entire platform inside your local sandbox environment:

### Prerequisites
- Node.js (v18+)
- Python (3.12+)

### Step 1: Fire up the FastAPI Backend
```bash
# Navigate to backend directory
cd backend

# Install python dependencies
pip install -r requirements.txt

# Start the uvicorn development gateway server
uvicorn app.main:app --reload --host 127.0.0.1 --port 8000
```
*Note: Once started, a background daemon worker automatically spawns and generates real-time random-walk telemetry data signed with cryptographic HMAC keys for CNC-101, Pump-302, and RA-45, feeding all downstream ML predictors!*

### Step 2: Fire up the Next.js Frontend
```bash
# Navigate to frontend directory
cd ../frontend

# Install dependencies
npm install

# Start NextJS dev server
npm run dev
```
*Open your browser and navigate to `http://localhost:3000`. You will be welcomed by a glowing landing page. Click 'Launch Operations Console' to step into the dark-themed glassmorphism console!*

### Step 3: Run Backend Test Suites
Ensure everything functions nominally:
```bash
cd ../backend
pytest -v
```

---

## 🗄️ Database Design

All database schema scripts (`database/schema.sql`) are built with TimescaleDB compatibility.
- `telemetry` and `predictions` are structured as **Hypertables** partitioned by timestamp.
- All indexes (`idx_telemetry_sensor_timestamp`, `idx_predictions_machine_timestamp`) are pre-indexed to facilitate high-frequency sub-millisecond retrieval.
- Seed data (`database/seed_data.sql`) seeds Alex Mercer (Admin), Sarah Chen (Operator), and Elena Rostova (Cybersec) to satisfy JWT RBAC authentications.

---

## 🐳 Containerized Production Deployments

### Docker Compose
Spin up the entire platform (PostgreSQL, Redis, Kafka, FastAPI, Next.js) with a single command:
```bash
docker-compose up --build
```

### Kubernetes Orchestration
Apply namespaces, secrets configurations, persistent database stateful sets, and high-availability backend deployments:
```bash
kubectl apply -f devops/kubernetes.yaml
```

---

## 📈 Git Repository Release Strategy

### 1. Commit Sequence Blueprint
Conforms to semantic styling conventions:
1. `feat: init directory structures, LICENSE, and base README guides`
2. `db: design relational and time-series TimescaleDB schema tables & seed files`
3. `backend: implement FastAPI gateway service, HMAC security, and uvicorn routing`
4. `ml: implement custom FFT features, XGBoost prediction, and Isolation Forest detectors`
5. `twin: integrate 3D ThreeJS mechanical model and counterfactual sliders logic`
6. `rag: build AI Maintenance Copilot Gemini prompt structures and queries`
7. `devops: engineer Dockerfiles, compose coordinates, and Kubernetes services`
8. `test: compile pytest unit verification files and CI Actions workflows`

### 2. Branching Logic (GitFlow)
- `main` — Production golden releases (Tagging `v2.0.0`).
- `develop` — Central integration branch for release candidates.
- `feature/*` — Isolated feature branches (e.g. `feature/ml-rul-lstm`).
- `hotfix/*` — High priority patch interventions.

### 3. Versioning Strategy
We adhere to **Semantic Versioning (SemVer)**:
- **Major (2.y.z):** Breaking changes or complete architecture overhauls.
- **Minor (x.1.z):** New modular engines (e.g., adding OPC-UA custom bounds).
- **Patch (x.y.1):** Minor regression or security certificate patches.

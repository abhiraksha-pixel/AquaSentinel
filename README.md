# AquaSentinel
### AI-Powered Groundwater Crisis Intelligence for India

**FOOBAR Hackathon 2026 | Sustainability Domain**

> "Groundwater is invisible. That is why the crisis is invisible. AquaSentinel makes it visible — before the last well runs dry."

---

## Overview

AquaSentinel is an AI-powered groundwater monitoring and crisis intelligence platform designed to address India's growing groundwater depletion and contamination challenges.

The platform brings groundwater information, predictive analytics, contamination monitoring, and decision-support tools into one unified system.

It follows a three-layer approach:

**SENSE → ANALYZE → ACT**

- **SENSE:** Collects and organizes groundwater information from different sources.
- **ANALYZE:** Uses machine learning models to forecast groundwater depletion and assess contamination risks.
- **ACT:** Provides alerts, interactive dashboards, and policy simulation tools to support informed decisions.

AquaSentinel aims to make groundwater information more accessible to farmers, local authorities, and policymakers.

---

## The Problem

Groundwater is one of India's most important water resources, supporting agriculture, industries, and everyday household consumption.

However, increasing extraction, changing rainfall patterns, and groundwater contamination are creating serious challenges.

Some of the major concerns highlighted by the project include:

| Statistic | Reality |
|---|---|
| 21 major cities | Projected to face severe groundwater shortages |
| 700M+ farmers | Require better groundwater information |
| 450 km³ | Groundwater lost between 2002 and 2021 |
| Fluoride (9%) | Wells exceeding safe limits |
| Arsenic (3.35%) | Wells exceeding safe limits |

Groundwater information from satellite observations, borewell records, and rainfall datasets is often scattered across different sources.

AquaSentinel aims to connect these information sources and transform them into useful insights.

---

## The Solution

AquaSentinel provides an integrated groundwater intelligence system through three major layers.

### 1. SENSE – Data Collection

- Collects and organizes groundwater information.
- Supports groundwater data analysis across Indian states.
- Uses environmental and groundwater-related datasets.
- Provides a centralized platform for groundwater information.

### 2. ANALYZE – AI and Machine Learning

- Uses an LSTM model for groundwater depletion forecasting.
- Forecasts groundwater depletion up to six months ahead.
- Uses XGBoost to assess contamination risk.
- Analyzes historical groundwater trends.
- Identifies regions requiring attention.

### 3. ACT – Decision Support

- Provides early groundwater depletion alerts.
- Displays groundwater information through interactive dashboards.
- Helps users understand contamination risks.
- Includes a policy simulator for evaluating water-management interventions.
- Supports informed decisions by farmers and local authorities.

---

## Key Features

### Interactive India Groundwater Dashboard

- Interactive map of India.
- State-wise groundwater information.
- Groundwater depth and depletion-rate visualization.
- Groundwater risk-level representation.
- State-specific information panels.

### AI-Based Groundwater Forecasting

- LSTM-based groundwater depletion forecasting.
- Six-month forecast visualization.
- Historical groundwater trend analysis.
- Predictive insights for groundwater monitoring.

### Contamination Risk Monitoring

- Tracks groundwater contamination indicators.
- Includes fluoride, arsenic, and iron.
- Provides contamination-related alerts.
- Uses XGBoost for contamination risk scoring.

### Alert Management

- Active groundwater alerts.
- Critical and high-priority alert categories.
- Contamination-specific notifications.
- Early depletion alerts for eligible premium users.

### Policy Simulation

- Simulates possible groundwater-management interventions.
- Evaluates measures such as check dams and drip irrigation.
- Helps estimate the potential impact of different interventions.
- Supports planning and decision-making.

### User Authentication

- User registration and login.
- JWT-based authentication.
- Logout functionality.
- Premium user support.

### Multi-Language Support

The platform supports:

- English
- Hindi
- Kannada

### Responsive Interface

- Interactive dashboard.
- Data visualization components.
- Responsive frontend design.
- Accessible groundwater information.

---

## System Architecture

AquaSentinel follows a full-stack architecture consisting of a frontend, backend, database, caching layer, and machine learning components.

```text
                 USER
                   |
                   v
          REACT FRONTEND
       Dashboard / Maps / Charts
                   |
                   v
             FASTAPI
             BACKEND
                   |
        +----------+----------+
        |          |          |
        v          v          v
   PostgreSQL    Redis     AI / ML
    + PostGIS     Cache     Models
        |                     |
        |               +-----+------+
        |               |            |
        |               v            v
        |              LSTM        XGBoost
        |               |            |
        +---------------+------------+
                        |
                        v
              GROUNDWATER INSIGHTS
                        |
                        v
             ALERTS AND FORECASTS
```

---

## Machine Learning Components

### LSTM – Groundwater Forecasting

Long Short-Term Memory (LSTM) is a recurrent neural network architecture suitable for sequential and time-series data.

In AquaSentinel, the LSTM model is intended to forecast groundwater depletion trends using historical groundwater information.

**Purpose:**
- Analyze historical groundwater trends.
- Identify changes in groundwater levels.
- Forecast depletion up to six months ahead.

### XGBoost – Contamination Risk Assessment

XGBoost is a gradient-boosting machine learning algorithm.

In AquaSentinel, it is used to assess groundwater contamination risk across states.

**Purpose:**
- Analyze contamination-related information.
- Estimate contamination risk.
- Support risk-based groundwater monitoring.

---

## Technology Stack

| Layer | Technology |
|---|---|
| Programming Language | Python |
| Backend Framework | FastAPI |
| Frontend Framework | React.js |
| Frontend Styling | Tailwind CSS |
| Mapping | Leaflet.js |
| Data Visualization | Recharts |
| Machine Learning | TensorFlow, Scikit-learn |
| Forecasting Model | LSTM |
| Risk Assessment Model | XGBoost |
| Database | PostgreSQL, PostGIS |
| Caching | Redis |
| Authentication | JWT |
| Containerization | Docker |
| Deployment | Render |

---

## API Endpoints

The backend provides API endpoints for groundwater information, alerts, forecasting, and policy simulation.

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/groundwater/all` | Retrieves all state groundwater readings |
| GET | `/api/groundwater/{state}` | Retrieves individual state details and contamination information |
| GET | `/api/groundwater/stats` | Retrieves national groundwater statistics |
| GET | `/api/alerts/active` | Retrieves active critical and high-priority alerts |
| GET | `/api/alerts/contamination` | Retrieves contamination-specific alerts |
| GET | `/api/forecast/{state}` | Retrieves the six-month depletion forecast |
| POST | `/api/simulator/run` | Runs a policy intervention simulation |

---

## Project Structure

```text
AquaSentinel/
│
├── backend/
│   ├── main.py
│   │
│   ├── routes/
│   │   ├── groundwater.py
│   │   ├── alerts.py
│   │   ├── forecast.py
│   │   └── simulator.py
│   │
│   ├── models/
│   │   └── schemas.py
│   │
│   ├── db/
│   │   ├── database.py
│   │   └── seed.py
│   │
│   ├── cache/
│   │   └── redis_client.py
│   │
│   └── requirements.txt
│
├── frontend/
│   └── src/
│       ├── pages/
│       │   ├── AuthPage.jsx
│       │   ├── Dashboard.jsx
│       │   └── PremiumPage.jsx
│       │
│       ├── components/
│       │   ├── IndiaMap.jsx
│       │   ├── ForecastChart.jsx
│       │   ├── AlertsTicker.jsx
│       │   └── StateDetailPanel.jsx
│       │
│       └── services/
│           └── api.js
│
├── ml/
│
├── docker-compose.yml
├── .env.example
├── .gitignore
├── LICENSE
└── README.md
```

---

## Installation and Setup

### Prerequisites

Make sure the following tools are installed:

- Python 3.11 or above
- Node.js 20 or above
- npm
- Docker Desktop
- Git

### Step 1 – Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

Navigate into the project directory:

```bash
cd AquaSentinel
```

### Step 2 – Configure Environment Variables

Create your local environment file:

```bash
cp .env.example .env
```

On Windows PowerShell, use:

```powershell
Copy-Item .env.example .env
```

Update the `.env` file with the required configuration and your own NASA Earthdata credentials if the relevant data integration is enabled.

**Important:** Never upload your actual `.env` file or private credentials to GitHub.

### Step 3 – Start the Application Using Docker

Make sure Docker Desktop is running.

Execute:

```bash
docker compose up --build
```

Docker Compose starts the configured services:

- PostgreSQL with PostGIS
- Redis
- FastAPI backend
- React frontend

### Step 4 – Access the Application

After the services start successfully, access the application through:

| Component | Local URL |
|---|---|
| Frontend | http://localhost:5173 |
| Backend API | http://localhost:8000 |
| API Documentation | http://localhost:8000/docs |

### Step 5 – Stop the Application

To stop all running services:

```bash
docker compose down
```

To stop the services and remove the stored PostgreSQL volume:

```bash
docker compose down -v
```

**Warning:** The second command deletes the persisted database volume and its data.

---

## Running Without Docker

### Backend Setup

Navigate to the backend directory:

```bash
cd backend
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Start the FastAPI server:

```bash
uvicorn main:app --reload --port 8000
```

### Frontend Setup

Open another terminal:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Start the frontend development server:

```bash
npm run dev
```

The frontend and backend must be configured to communicate with each other.

---

## Environment Configuration

The `.env.example` file provides the following configuration variables:

| Variable | Purpose |
|---|---|
| `DATABASE_URL` | PostgreSQL database connection |
| `REDIS_URL` | Redis cache connection |
| `NASA_USERNAME` | NASA Earthdata username |
| `NASA_PASSWORD` | NASA Earthdata password |
| `VITE_API_URL` | Backend API URL used by the frontend |

Use your own credentials and configuration values when setting up the application.

---

## Impact and Applications

AquaSentinel is designed to support different groups involved in groundwater management.

| Target Audience | Potential Benefit |
|---|---|
| Farmers | Early groundwater depletion alerts and crop advisory |
| Panchayats | Groundwater monitoring and contamination information |
| Urban Authorities | Monitoring groundwater depletion in at-risk cities |
| District Collectors | Policy simulation and intervention planning |

### Sustainable Development Goals

AquaSentinel aligns with the following United Nations Sustainable Development Goals:

- **SDG 6 – Clean Water and Sanitation:** Supports groundwater monitoring and contamination awareness.
- **SDG 2 – Zero Hunger:** Supports better crop and water-management decisions.
- **SDG 13 – Climate Action:** Addresses groundwater depletion and environmental sustainability.
- **SDG 11 – Sustainable Cities and Communities:** Supports sustainable urban water-resource planning.

---

## Future Enhancements

Potential improvements include:

- Integration with additional real-time groundwater data sources.
- Improved forecasting accuracy through expanded historical datasets.
- More detailed district-level groundwater analysis.
- Mobile application for farmers.
- SMS and WhatsApp-based groundwater alerts.
- Additional regional language support.
- Improved contamination prediction using more comprehensive datasets.
- Advanced policy simulation with additional intervention scenarios.
- Integration with more satellite and environmental datasets.

---

## Important Notes

- The project is designed as a groundwater intelligence and decision-support platform.
- Forecasts and risk scores depend on the quality and availability of input datasets.
- The `.env.example` file contains placeholder credentials; provide your own values where required.
- Never commit private credentials or actual environment files.
- The Docker configuration uses PostgreSQL with PostGIS and Redis.
- The project README and deployment configuration should be kept consistent as the application evolves.

---

## Author

**Abhi Raksha**  
B.Tech – Electronics and Computer Science (AIML Specialization)  
Christ University

Contributed to the development of AquaSentinel, an AI-powered groundwater intelligence platform focused on monitoring groundwater depletion, predicting future water levels, and identifying contamination risks.

Interested in Artificial Intelligence, Machine Learning, Full-Stack Development, and sustainable technology solutions.

**Connect with me:**
- LinkedIn: www.linkedin.com/in/abhi-raksha-9b3b80369/
- Email: abhiraksha06@gmail.com

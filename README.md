# 🧑‍⚕️ Clinical Research Data Integration & Query API

A demo project that simulates how research informatics teams (like CB2) can support clinical and biomedical research by:

* Ingesting **synthetic patient datasets** into a relational database
* Providing a **FastAPI backend** to query patient demographics, conditions, and lab results
* Generating **summary visualizations** and **PDF/CSV research reports**
* Packaging the system with Docker for cloud-native deployment

⚠️ **Note:** This project uses **synthetic healthcare data** (Synthea) and does **not contain real patient information**.

---

## 📂 Project Architecture

```mermaid
flowchart TD
    A[Synthetic Data (Synthea CSVs)] --> B[ETL Pipeline (Python)]
    B --> C[PostgreSQL/MariaDB Database]
    C --> D[FastAPI Backend]
    D --> E[Researchers / API Clients]
    D --> F[Reports & Visualizations]
```

---

## 🛠️ Tech Stack

* **Python 3.10+**
* **FastAPI** – API framework
* **SQLAlchemy** – ORM for database models
* **PostgreSQL / MariaDB** – Research data storage
* **Matplotlib / Plotly** – Visualizations
* **ReportLab** – PDF reporting
* **Docker & Docker Compose** – Deployment ready

---

## ⚡ Features

* 🔄 **ETL Pipeline**: Extract, Transform, Load synthetic patient data
* 📦 **Database Schema**: Patients, Conditions, Observations
* 🌐 **REST API**: Query patients, conditions, lab results with filters
* 🔐 **Auth**: Simple Bearer token authentication
* 📊 **Reports**: Disease distributions, lab result summaries, PDF/CSV exports
* ☁️ **Cloud Ready**: Dockerized deployment

---

## 🚀 Quick Start

### 1. Clone Repo

```bash
git clone https://github.com/vkrishna-1/clinical-research-api.git
cd clinical-research-api
```

### 2. Run with Docker (recommended)

```bash
docker-compose up --build
```

### 3. Access API Docs

Open: [http://localhost:8000/docs](http://localhost:8000/docs)

---

## 📖 API Endpoints

### Patients

* `GET /patients/` → list all patients
* `GET /patients/{id}` → patient details (demographics + conditions + labs)

### Conditions

* `GET /conditions/` → filter patients by condition (e.g., diabetes)

### Observations

* `GET /observations/summary` → lab test summaries (HbA1c, BP, etc.)

### Research Query

* `POST /query/` → run custom filter (example: patients with HbA1c > 7.5)

---

## 📊 Example Outputs

### API Docs Screenshot

*(Insert screenshot of FastAPI Swagger UI later)*

### Disease Distribution

*(Insert bar chart image later)*

### PDF Report

*(Insert sample report screenshot later)*

---

## 🧩 Project Structure

```
clinical-research-api/
│── app/
│   ├── main.py          # FastAPI entrypoint
│   ├── models.py        # SQLAlchemy models
│   ├── schemas.py       # Pydantic schemas
│   ├── crud.py          # DB operations
│   ├── routers/         # API routes
│   │   ├── patients.py
│   │   ├── conditions.py
│   │   └── observations.py
│── etl.py               # ETL pipeline
│── report.py            # PDF/CSV reporting
│── requirements.txt     # Python deps
│── Dockerfile
│── docker-compose.yml
│── README.md
```

---

## 📑 Sample Research Use Case

1. A clinical researcher uploads new patient datasets (synthetic in this demo).
2. ETL pipeline processes and loads them into the research DB.
3. Researcher queries patients by condition (e.g., diabetes) and labs (e.g., HbA1c).
4. API generates filtered results and produces a **research-ready report**.

---

## 🔒 Security & Compliance

* Token-based API authentication
* Clear separation of ETL, storage, and access layers
* Uses only **synthetic, HIPAA-safe data**

---

## 🙌 Acknowledgments

* [Synthea Synthetic Patient Data](https://synthetichealth.github.io/synthea/)
* FastAPI, SQLAlchemy, MariaDB

---

## 📬 Contact

Created by **Vamsi Krishna**
Graduate, Information Sciences Department @ \University of Arizona
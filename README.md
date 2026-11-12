# ⚡ DocFusion — Multi-Format Document Intelligence & Visualization Platform

<div align="center">

[![React](https://img.shields.io/badge/React-18.3-61DAFB.svg?style=for-the-badge&logo=react)](https://react.dev)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.111-009688.svg?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.5-3178C6.svg?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org)
[![Python](https://img.shields.io/badge/Python-3.11+-3776AB.svg?style=for-the-badge&logo=python)](https://python.org)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-3.4-38B2AC.svg?style=for-the-badge&logo=tailwind-css)](https://tailwindcss.com)
[![SQLite](https://img.shields.io/badge/SQLite-SQLAlchemy-003B57.svg?style=for-the-badge&logo=sqlite)](https://sqlite.org)
[![License](https://img.shields.io/badge/License-MIT-purple.svg?style=for-the-badge)](LICENSE)
[![Author](https://img.shields.io/badge/Author-SparkSidd-orange.svg?style=for-the-badge&logo=github)](https://github.com/SparkSidd)

**Unified Document Intelligence, Automated Chart Synthesis, and Conversational Grounded Analysis.**  
*Prompt-to-Chart Synthesis · Multi-Format File Parsing (PDF, DOCX, CSV, XLSX) · Real-Time Visual Q&A · Fact-Checking Engine*

[Overview](#-overview) • [Architecture](#-system-architecture) • [Features](#-key-capabilities) • [Tech Stack](#-technical-stack) • [Quick Start](#-quick-start)

</div>

---

## 📌 Overview

DocFusion is an enterprise document intelligence and analytical dashboard that fuses automated tabular data extraction with LLM reasoning. Rather than reading static reports or manually writing data visualization scripts, users upload complex multi-page files (PDF, DOCX, Excel, CSV) and interact through an intelligent prompt-to-chart visualization pipeline.

---

## 🚀 Key Capabilities

- **📄 Universal Document Ingestion**: Seamless parser pipeline for `.pdf`, `.docx`, `.xlsx`, `.csv`, and `.txt` files.
- **📊 Prompt-to-Chart Engine**: Converts natural language prompts into reactive Chart.js / Recharts visualizations automatically.
- **🔍 Grounded Document Q&A**: Context-aware retrieval engine extracting verbatim citations and verifying claims against raw text.
- **🛡️ JWT Authentication & Session Isolation**: Secure multi-user document workspaces with RBAC boundaries.
- **📈 Analytical Data Profiling**: Automatically computes skewness, statistical correlations, missing value heatmaps, and outlier flags upon upload.

---

## 🏗️ System Architecture

```mermaid
graph TD
    User([Client / Analyst]) <-->|REST API + JWT| FE[React 18 + Vite SPA]
    FE <-->|Async HTTP Requests| BE[FastAPI REST Engine]
    
    subgraph Data Pipeline
        BE --> Parser[Multi-Format Parser: PDF/DOCX/XLSX/CSV]
        Parser --> Storage[(SQLite / docviz.db)]
        Parser --> Profiler[Statistical Data Profiler]
    end
    
    subgraph LLM & Viz Engine
        BE --> PromptEngine[Prompt-to-Chart Generator]
        BE --> QA[Grounded Document Q&A & Fact-Check]
        PromptEngine --> ChartSpec[Chart.js / Vega Specifications]
    end
```

---

## 🛠️ Technical Stack

| Category | Technology |
| :--- | :--- |
| **Frontend** | React 18, TypeScript 5.5, Vite, Tailwind CSS, TanStack Query, Zustand |
| **Backend** | Python 3.11+, FastAPI (Async), Pydantic v2, Uvicorn |
| **ORM & Storage** | SQLAlchemy, SQLite (`docviz.db`), Multi-part file upload streaming |
| **Data & Plotting** | Pandas, NumPy, Matplotlib, Recharts |
| **Security** | OAuth2 with Password Flow, JWT bearer tokens, bcrypt hashing |

---

## ⚡ Quick Start

### 1. Clone & Setup Backend
```bash
cd DocFusion/backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000
```

### 2. Frontend Setup
```bash
cd ../frontend
npm install
npm run dev
```

Navigate to `http://localhost:5173`. Use demo credentials or register a local tenant.

---

## 📄 License
This project is open-source under the MIT License.

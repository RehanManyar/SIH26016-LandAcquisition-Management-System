# 🏛️ LRVS — Real-Time National Land Acquisition & Management System

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Render-46E3B7?style=for-the-badge&logo=render&logoColor=white)](https://sih-26016-app.onrender.com/login)
[![Health Status](https://img.shields.io/badge/Status-Live%20%26%20Verified-brightgreen?style=for-the-badge)](https://sih-26016-app.onrender.com/health)
[![Node.js](https://img.shields.io/badge/Node.js-22.x-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-4.x-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB Atlas](https://img.shields.io/badge/MongoDB%20Atlas-M0%20Free-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/atlas)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

> **Smart India Hackathon (SIH) — Problem Statement SIH26016**  
> **Developed by: Team BLAZE | Rehan Manyar**

An AI and Blockchain powered unified digital governance platform designed to digitize, streamline, and secure the complete national land acquisition lifecycle — from initial project proposal and OCR document scrutiny to multi-tier administrative approvals, statutory compensation disbursement, and physical possession tracking.

---

## 🌐 Live Prototype & Deployment

The application is deployed on **Render Free Web Service** connected to a **MongoDB Atlas Cloud Database**:

* **🚀 Live Application (Login):** **[https://sih-26016-app.onrender.com/login](https://sih-26016-app.onrender.com/login)**
* **🩺 Live Health Check:** **[https://sih-26016-app.onrender.com/health](https://sih-26016-app.onrender.com/health)**
* **📊 API Status Check:** **[https://sih-26016-app.onrender.com/api/health](https://sih-26016-app.onrender.com/api/health)**

---

## 🔑 Evaluator & Demo Accounts

The live system comes pre-seeded with 8 specialized administrative roles and realistic demo cases (including the Golden Demo Case **LA-2026-0003**: Greenfield Expressway, Nashik).

> **Universal Demo Password:** `Pass@1234`  
*(Tip: On the live login page, you can also click the quick one-tap autofill buttons at the bottom of the sign-in form)*

| Role | User ID | Name / Designation | Department / Jurisdiction |
|---|---|---|---|
| **Super Admin** | `SUPER-001` | System Administrator | National Land Portal HQ (Full System Access) |
| **Central Authority** | `CENTRAL-001` | Dr. Alok Verma, Joint Secretary | Ministry of Land Resources & Highways |
| **State Authority** | `STATE-001` | Sunita Patil, IAS, Principal Secretary | Revenue & Forest Department, Maharashtra |
| **District Authority** | `DIST-001` | Jalaj Sharma, IAS, District Collector | Collectorate Office, Nashik District |
| **Verification Officer** | `VERIF-001` | Manoj Kumar, Scrutiny Officer | Land Record Scrutiny & Data Verification |
| **Project Officer** | `PROJ-001` | Pravin Sharma, Executive Engineer | Acquiring Body (NHAI / MSRDC / PWD) |
| **Finance Officer** | `FIN-001` | Rajesh Mehta, Chief Accounts Officer | Treasury & Direct Bank Compensation |
| **Land Owner (Citizen)** | `LAND-001` | Ramesh Patil (Survey No. 142/8) | Sinnar, Nashik |

---

## 🎯 Problem Statement (SIH26016)

The traditional land acquisition process in India suffers from severe bottlenecks:
* Fragmented paper documentation across Talathi, Tehsildar, and Collectorate offices.
* Lengthy manual scrutiny of 7/12 extracts, property cards, and title deeds.
* Opaque multi-level approval hierarchies causing years of project delays.
* Disputes over compensation computation, solatium, and ownership shares.
* Lack of real-time visibility for project authorities and affected land owners.
* Vulnerability of paper audit trails to tampering and litigation.

**LRVS Solution:** A centralized, transparent, role-based platform integrating OCR-based automated document parsing, immutable blockchain timestamping, GIS land parcel visualization, and automated statutory RFCTLARR Act compensation workflows.

---

## ✨ Key Capabilities & Modules

1. **Role-Based Portals & Dashboards**
   - Distinct, tailored dashboard interfaces for Central Ministries, State Secretariats, District Collectors, Scrutiny Officers, Finance Officers, and Landowners.
2. **End-to-End Acquisition Lifecycle Workflow**
   - Proposal creation &rarr; AI OCR document upload &rarr; Scrutiny & discrepancy correction &rarr; Section 11 Gazette Notification &rarr; Section 23 Award declaration &rarr; Statutory compensation computation (Market value + 100% Solatium + 12% interest) &rarr; Sandbox Direct Bank Transfer &rarr; Panchnama & Handover &rarr; Rehabilitation & Resettlement (R&R) &rarr; Final Case Closure.
3. **GIS & Geospatial Land Mapping**
   - Interactive GIS land mapping powered by Leaflet.js with village/district boundary GeoJSON overlays and survey plot coordinates.
4. **AI-Assisted Document Processing (Prototype Engine)**
   - Automatic extraction of survey numbers, owner names, cultivable/uncultivable areas, and shares with confidence scores and verification flagging.
5. **Blockchain Audit Trail & Immutability**
   - Cryptographic SHA-256 state and document hashing anchored with smart contracts (`LandRecord.sol`, `Approval.sol`, `Compensation.sol`) with resilient mock fallback for zero-gas prototype evaluation.
6. **Citizen Land Owner Portal**
   - Dedicated portal for affected farmers to view acquisition notifications, survey measurements, award amounts, bank disbursement receipts, and submit grievance/rehabilitation requests.
7. **Production-Ready Security & Resilience**
   - HTTP-only secure cookie authentication, JWT tokens, RBAC authorization middleware, Rate Limiting, Helmet CSP security headers, non-blocking auto-reconnecting MongoDB client, and graceful uptime probes.

---

## 🛠️ Technology Stack

| Layer | Technologies |
|---|---|
| **Runtime & Backend** | **Node.js** (v20+ / v22+), **Express.js** (v4.21) |
| **View Engine & Frontend** | **EJS** with `express-ejs-layouts`, **Tailwind CSS** (CDN), **Vanilla JS** |
| **Database & ODM** | **MongoDB Atlas** (M0 Free Tier), **Mongoose** (v8.8) |
| **Security & Auth** | **JWT** (`jsonwebtoken`), **bcryptjs**, `cookie-parser`, **Helmet**, `express-rate-limit` |
| **Document Processing & Uploads** | **Multer**, File Type Validation, Local decoupled storage provider facade |
| **Geospatial (GIS)** | **Leaflet.js**, GeoJSON boundaries (India States, Maharashtra, Nashik District/Villages) |
| **Blockchain Integration** | **ethers.js** (v6), Solidity Smart Contracts (`contracts/`), Synthetic Mock Provider |
| **Testing & QA** | **Jest** (v29), **Supertest**, `mongodb-memory-server` (48 Passing Automated Unit/Integration Tests) |
| **Hosting & Cloud** | **Render** (Free Web Service), **Cloudflare SSL**, **UptimeRobot** 24/7 keep-alive monitor |

---

## 📂 Repository Structure

```text
SIH26016-LandAcquisition-Management-System/
├── App/
│   ├── backend/
│   │   ├── scripts/               # Database seeding and E2E simulation scripts
│   │   │   ├── seed_demo_full.js  # Seeds 8 evaluation users and 5 canonical cases
│   │   │   └── seed.js
│   │   ├── src/
│   │   │   ├── controllers/       # Auth, Land, Approval, Compensation, Verification, Web
│   │   │   ├── middleware/        # JWT auth, role RBAC, upload validation, error handler
│   │   │   ├── models/            # Mongoose Schemas (User, LandRecord, Document, Approval, etc.)
│   │   │   ├── public/            # CSS styles, GIS scripts, GeoJSON boundary files
│   │   │   ├── routes/            # REST API & EJS browser web routes
│   │   │   ├── services/          # Business logic, blockchain service, AI adapter, audit
│   │   │   ├── storage/           # Decoupled Local & S3 Storage providers
│   │   │   ├── utils/             # Constants, hash helpers, winston logger, response formatters
│   │   │   ├── views/             # Responsive EJS views (Dashboards, Land, Approvals, Compensation)
│   │   │   └── app.js             # Express application entry point (0.0.0.0 binding)
│   │   ├── tests/                 # Jest test suites (Health, Auth, Land, Document, Blockchain)
│   │   ├── .env.example           # Production environment variables template
│   │   └── package.json
│   ├── blockchain/                # Solidity smart contracts & deployment scripts
│   │   ├── contracts/             # LandRecord.sol, Approval.sol, Compensation.sol
│   │   └── services/
│   ├── ai-service/                # Python OCR microservice specification
│   └── docker-compose.yml
├── render.yaml                    # Infrastructure as Code: 1-Click Render Blueprint
├── .gitignore                     # Git rules protecting secrets and uploads
└── README.md
```

---

## 💻 Local Development Setup

### 1. Prerequisites
* **Node.js** v18+ (Node v20 or v22 recommended)
* **npm** v9+
* **MongoDB** (Local instance or MongoDB Atlas connection URI)

### 2. Clone the Repository
```bash
git clone https://github.com/RehanManyar/SIH26016-LandAcquisition-Management-System.git
cd SIH26016-LandAcquisition-Management-System
```

### 3. Install Backend Dependencies
```bash
cd App/backend
npm install
```

### 4. Configure Environment Variables
Copy `.env.example` to `.env`:
```bash
cp .env.example .env
```

Ensure the key variables are configured:
```env
PORT=9000
NODE_ENV=development
MONGO_URI=mongodb://127.0.0.1:27017/sih26016
JWT_SECRET=lrvs-team-blaze-dev-secret-key-2026
JWT_EXPIRES_IN=7d
BLOCKCHAIN_MOCK=true
CORS_ORIGIN=*
UPLOAD_DIR=uploads
DOCUMENT_STORAGE_PROVIDER=local
DOCUMENT_STORAGE_PATH=storage/documents
```

### 5. Seed Demonstration Data
Seed all 8 evaluation users and demonstration cases into your database:
```bash
node scripts/seed_demo_full.js
```

### 6. Run the Application
```bash
# Start in development mode with nodemon
npm run dev

# Or start in standard production mode
npm start
```
Open **[http://localhost:9000/login](http://localhost:9000/login)** in your browser.

### 7. Run Automated Tests
```bash
npm test
```
All **48 test cases across 5 test suites** run in-memory and pass without external dependencies.

---

## 📡 Key REST API Endpoints

| Method | Endpoint | Access | Purpose |
|---|---|---|---|
| `GET` | `/health` | Public | System and database health status |
| `GET` | `/api/health` | Public | JSON health status probe |
| `POST` | `/api/auth/login` | Public | Authenticate user & issue JWT |
| `POST` | `/api/auth/logout` | Authenticated | Clear session cookie |
| `GET` | `/api/land/requests` | All Roles | Fetch paginated land acquisition cases |
| `POST` | `/api/land` | Project / District Officer | Create new land acquisition proposal |
| `GET` | `/api/land/:requestId` | All Roles | Get complete case details & document links |
| `POST` | `/api/land/:requestId/submit` | Project Officer | Submit draft case for scrutiny |
| `GET` | `/api/land/map` | Officer Roles | GeoJSON land parcel features for GIS map |
| `POST` | `/api/documents/upload` | Officer Roles | Upload land deeds, 7/12 extracts, and maps |
| `GET` | `/api/verification/queue` | Verification Officer | Scrutiny workbench queue |
| `POST` | `/api/approvals/:approvalId/action` | Authority Roles | Level 1 / Level 2 / Level 3 approval action |
| `POST` | `/api/compensation/calculate` | Finance Officer | Compute statutory valuation & solatium |

---

## ☁️ Deployment on Render

This repository includes a native [render.yaml](render.yaml) Blueprint for zero-friction deployment:

1. Fork or push this repository to GitHub.
2. In [Render Dashboard](https://dashboard.render.com/), click **New +** &rarr; **Blueprint** and select this repository.
3. Render automatically detects the configuration:
   * **Root Directory:** `App/backend`
   * **Build Command:** `npm install`
   * **Start Command:** `npm start`
   * **Plan:** `Free`
4. Supply your `MONGO_URI` (MongoDB Atlas connection string).
5. Ensure `0.0.0.0/0` is allowed in MongoDB Atlas Network Access.
6. Deploy! Render will build and deploy the web service in under 2 minutes.

---

## 👥 Team & Authors

* **Author:** Rehan Manyar ([@RehanManyar](https://github.com/RehanManyar))
* **Team:** Team BLAZE
* **Hackathon:** Smart India Hackathon (SIH)
* **Problem Statement:** SIH26016 — Real-Time National Land Acquisition & Management System

---

## 📜 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

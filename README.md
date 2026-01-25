# NexLogica 🚚 Intelligent Logistics & Supply Chain Platform

> "Visibility. Trust. Optimization."

NexLogica is a **full-stack, enterprise-grade logistics and supply chain management platform** engineered for real-world deployment at scale. It combines real-time fleet tracking, blockchain-based escrow payments, AI-driven optimization, and role-based operational dashboards into a unified system.

Built with production discipline, NexLogica is designed to serve as the core infrastructure for a commercial logistics SaaS, not a prototype.

## 🚧 Project Status

| Area | Status | Notes |
| :--- | :--- | :--- |
| **Public Demo** | Coming Soon | Current focus: system hardening, documentation, and production readiness. |
| **Authentication & RBAC** | ✅ Complete | |
| **Real-time tracking** | ✅ Complete | |
| **Blockchain escrow** | ✅ Complete | |
| **Input validation** | ✅ Complete | |
| **Logging & monitoring** | ✅ Complete | |
| **Test coverage** | ⚠️ Expanding | Increasing unit and integration test coverage. |
| **Smart contract audit** | ⚠️ Planned | Formal security audit for smart contracts. |
| **Load testing** | ⚠️ Pending | Performance testing under high load. |

---

## 🎯 Problem & Solution

Modern logistics systems fail when visibility, trust, and coordination break down. NexLogica addresses this by delivering a platform that ensures **reliability, transparency, and scalability** for logistics operators, fleet managers, drivers, and enterprises.

**Key Solutions Delivered:**

*   **End-to-end shipment visibility:** Track every stage of the shipment lifecycle.
*   **Real-time fleet intelligence:** High-frequency GPS telemetry and live vehicle maps.
*   **Trustless payment settlement:** Automated, secure payments via blockchain escrow.
*   **Operational insights:** Data-powered analytics for better decision-making.
*   **Role-specific workflows:** Frictionless, tailored experiences for Admins, Managers, and Drivers.

## ✨ Core Capabilities

### 📡 Real-Time Fleet & Shipment Tracking

*   High-frequency GPS telemetry
*   Live vehicle maps with status indicators
*   Shipment lifecycle tracking from creation to delivery
*   Route history & playback analytics

### 🔐 Blockchain-Based Escrow Payments

*   Trustless shipment escrow using smart contracts
*   Pickup & delivery confirmations recorded on-chain
*   Automatic payment release on delivery
*   Immutable audit trail for all transactions

**Blockchain Escrow Flow:**
1.  Shipment created with defined price.
2.  Sender deposits funds into escrow contract.
3.  Driver confirms pickup (on-chain).
4.  Driver confirms delivery with proof.
5.  Smart contract releases payment.
6.  Transaction permanently recorded.

This removes manual disputes, delays, and trust assumptions.

### 🤖 AI-Driven Intelligence

*   Route optimization for cost & time efficiency
*   Demand surge forecasting (LSTM-ready)
*   Delay risk detection & alerts
*   Driver performance analytics

### 🧑‍💼 Role-Based Operations

*   **Admin:** System health, fleet oversight, sustainability metrics.
*   **Manager:** Shipment planning, driver allocation, optimization.
*   **Driver:** Mobile-first delivery workflow (PWA).

### 🌱 Sustainability Intelligence

*   CO₂ emissions tracking
*   Electric vs diesel fleet comparison
*   Route efficiency impact
*   Green logistics metrics (tokenization planned)

---

## 🧠 System Architecture

The platform follows a service-oriented, stateless architecture with clear separation of concerns and production-ready patterns.

### High-Level Flow

```mermaid
graph TD
    A[React Frontend (Web + PWA)] --> B(REST API & WebSocket Gateway);
    B --> C(Core Services Layer);
    C --> D(MongoDB + Redis + Polygon Blockchain);
    C --> E(AI Service);
    C --> F(Blockchain Service);
```

### Platform Modules

| Module | Purpose |
| :--- | :--- |
| **Authentication** | Secure access & role control |
| **Fleet Management** | Vehicle telemetry & status |
| **Shipment Engine** | Lifecycle & assignment |
| **GPS Service** | Real-time tracking & analytics |
| **Blockchain Service** | Escrow & audit |
| **AI Service** | Optimization & forecasting |
| **Notifications** | In-app alerts |
| **Simulation Engine** | Demo & testing workloads |

### Repository Structure

```
NexLogica/
├── server/            # Express backend
├── client_new/        # React frontend (Vite)
├── blockchain/        # Smart contracts
├── ai-engine/         # AI/ML services
├── automation/        # CI/CD & health checks
├── scripts/           # Utilities
└── docs/              # Technical documentation
```

---

## 🛠️ Technology Stack

### Backend

*   **Runtime:** Node.js 18, Express.js
*   **Database:** MongoDB (Mongoose), Redis (caching & real-time state)
*   **Real-time:** Socket.IO
*   **Security:** JWT + bcrypt, Helmet, CORS, Rate Limiting
*   **Payments:** Stripe
*   **Logging:** Winston & Morgan

### Frontend (Web & PWA)

*   **Framework:** React 18 + Vite
*   **State Management:** Redux Toolkit
*   **Styling:** TailwindCSS
*   **Mapping:** Leaflet
*   **Analytics:** Recharts
*   **UI/UX:** Framer Motion, React Hook Form
*   **Real-time:** Socket.IO Client
*   **Localization:** i18next (i18n)
*   **PWA Features:** Installable on Android & iOS, Offline-tolerant workflows, Background GPS tracking, Camera & signature capture for proof of delivery.

### Blockchain

*   **Language:** Solidity (0.8.x)
*   **Development:** Hardhat, ethers.js
*   **Network:** Polygon Amoy Testnet

### AI / ML

*   **Framework:** Python (Flask – planned)
*   **Models:** LSTM demand forecasting, Route optimization algorithms

---

## 🔐 Security Model

The platform is built with a security-first approach:

*   **Authentication:** JWT authentication (30-day expiry).
*   **Authorization:** Role-based access control (RBAC) middleware.
*   **Data Security:** Bcrypt password hashing (cost factor 12).
*   **API Protection:** Rate limiting (auth & general APIs), Input validation on all endpoints.
*   **File Handling:** Secure file upload handling.
*   **Secrets:** Environment-based secret management.
*   **Blockchain Integration:** Blockchain transaction verification before DB updates.

## 🚀 Getting Started

### ⚙️ Environment Configuration

You will need to set up environment variables for the backend. Create a `.env` file in the `server/` directory:

```bash
# Backend (.env)
MONGODB_URI=mongodb://localhost:27017/logichain360
PORT=5000
JWT_SECRET=your_secret
CONTRACT_ADDRESS=0x...
ALCHEMY_AMOY_URL=https://polygon-amoy.g.alchemy.com/v2/KEY
PRIVATE_KEY=0x...
CORS_ORIGIN=http://localhost:4028
```

The frontend runs on Vite dev server at port `4028` and is configured to proxy API requests to the backend.

### Quick Start

Follow these steps to get the platform running locally:

**1. Backend**
```bash
cd server
npm install
npm run dev
```

**2. Frontend**
```bash
cd client_new
npm install
npm run dev
```

**3. Blockchain (Smart Contracts)**
```bash
cd blockchain
npx hardhat compile
npx hardhat run scripts/deploy.js --network amoy
```

---

## 🧪 Testing & Observability

*   Backend smoke tests
*   Smart contract tests (Hardhat + Chai)
*   Structured logging (Winston)
*   HTTP request logging (Morgan)
*   Health-check endpoints

## 🔮 Roadmap

### Platform Hardening
*   Expanded automated testing
*   Load & stress testing
*   Smart contract audits

### Intelligence Layer
*   Advanced ML forecasting
*   Predictive maintenance
*   Dynamic pricing models

### Expansion
*   Multi-chain blockchain support
*   Native mobile apps
*   IoT & cold-chain integrations
*   BI dashboards & exports

---

## 📞 Contact

**GitHub:** @RyanKeshary  
**Email:** [ryankeshary@gmail.com](mailto:ryankeshary@gmail.com)

---

<a href="#-table-of-contents">⬆️ Back to Top</a>

# 🐾 Pet-Woft MVP - Architecture Showcase

> **Enterprise-Grade Veterinary Management System** <br> *Full-Stack Application with Advanced Security & Modern Architecture*

![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white) ![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB) ![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) ![Express.js](https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB)

---

## 📑 Table of Contents

* [🎯 Overview](#overview)
* [🏛️ System Architecture](#system-architecture)
* [🎨 Design Patterns](#design-patterns)
* [🔐 Security Implementation](#security)
* [💻 Technology Stack](#stack)
* [✨ Key Features](#features)
* [💾 Database Design](#database)
* [📷 System Screenshots](#screenshots)
* [🤔 Why This Architecture?](#why)
* [📞 Contact](#contact)

---

## <a id="overview"></a>🎯 Overview

Pet-Woft MVP is a **production-ready veterinary management system** built from scratch, demonstrating expertise in:

* ✅ **Full-Stack Development** (React 19 + Node.js + PostgreSQL)
* ✅ **Enterprise Security** (2FA + Argon2 + RBAC + 10 security layers)
* ✅ **Scalable Architecture** (MVC + Service Layer + Repository Pattern)
* ✅ **Design Patterns** (7 classic patterns implemented)
* ✅ **Third-Party Integrations** (MercadoPago, Google Gemini AI, Email)
* ✅ **Modern Frontend** (TypeScript + React Compiler + Vite)
* ✅ **Database Optimization** (Triggers, Views, Indexes, PL/pgSQL)

> **Note:** This repository showcases the architecture, design decisions, and documentation. The complete source code is private to protect intellectual property.

---

### <a id="system-architecture"></a>🏛️ System Architecture

### High-Level Architecture

<img width="1066" height="844" alt="image" src="https://github.com/user-attachments/assets/a82fb975-a8df-4314-9899-99d2071d283a" />


### Layered Architecture


```text
┌──────────────────────────────────────────────────────────────┐
│               Presentation Layer (React + TS)                │
│   Components  |  Pages  |  Hooks  |  Context  |  Router      │
└──────────────────────────────┬───────────────────────────────┘
                               ↓
┌──────────────────────────────┴───────────────────────────────┐
│                   API Layer (Controllers)                    │
│     HTTP Request Handling  |  Validation  |  Responses       │
└──────────────────────────────┬───────────────────────────────┘
                               ↓
┌──────────────────────────────┴───────────────────────────────┐
│               Business Logic Layer (Services)                │
│    AuthService  |  CitaService  |  PagoService  |  etc.      │
└──────────────────────────────┬───────────────────────────────┘
                               ↓
┌──────────────────────────────┴───────────────────────────────┐
│           Data Access Layer (Models/Repositories)            │
│      Usuario  |  Paciente  |  Cita  |  Pago  |  etc.         │
└──────────────────────────────┬───────────────────────────────┘
                               ↓
┌──────────────────────────────┴───────────────────────────────┐
│                  Database Layer (PostgreSQL)                 │
│    Tables  |  Triggers  |  Views  |  Functions  |  Indexes   │
└──────────────────────────────────────────────────────────────┘
```

---

### <a id="design-patterns"></a>🎨 Design Patterns

#### 1. MVC (Model-View-Controller)
**Purpose:** Separation of concerns for maintainability and scalability.

<img width="718" height="590" alt="image" src="https://github.com/user-attachments/assets/8ae5e597-2f55-40c8-b51c-abf71aed9fc4" />

**Benefits:**
* ✅ Clear separation of responsibilities
* ✅ Easy to test each layer independently
* ✅ Reusable business logic

---

#### 2. Singleton Pattern
**Purpose:** Single shared instance of services.

<img width="719" height="268" alt="image" src="https://github.com/user-attachments/assets/aa4dd6c8-b2cf-48bb-930d-12890accc2aa" />

**Benefits:**
* ✅ Consistent state across application
* ✅ Memory efficient
* ✅ Easy dependency injection

---

#### 3. Middleware Pattern (Chain of Responsibility)
**Purpose:** Composable request processing pipeline.

<img width="717" height="294" alt="image" src="https://github.com/user-attachments/assets/18a10c6b-1ce3-486e-988b-00a7a452fa42" />

**Benefits:**
* ✅ Reusable middleware components
* ✅ Easy to add/remove functionality
* ✅ Clear request flow

---

#### 4. Factory Pattern
**Purpose:** Centralized object creation with configuration.

<img width="719" height="621" alt="image" src="https://github.com/user-attachments/assets/fe461834-446f-404d-a9a9-8256d6465d34" />

**Benefits:**
* ✅ Encapsulates complex creation logic
* ✅ Centralized configuration
* ✅ Easy to test and mock

---

#### 5. Strategy Pattern
**Purpose:** Interchangeable algorithms/behaviors.

<img width="722" height="515" alt="image" src="https://github.com/user-attachments/assets/f429acf1-5483-4c95-89e0-ef8881721ed2" />

**Benefits:**
* ✅ Easy to switch between strategies
* ✅ Testable without external dependencies
* ✅ Clean separation of concerns

---

#### 6. Observer Pattern
**Purpose:** Event-driven architecture for decoupling.

<img width="720" height="481" alt="image" src="https://github.com/user-attachments/assets/cce30533-2389-4149-961b-69ee55489af3" />

**Benefits:**
* ✅ Decoupled systems
* ✅ Asynchronous processing
* ✅ Scalable architecture

---

#### 7. Repository Pattern
**Purpose:** Abstract data access layer.

<img width="723" height="655" alt="image" src="https://github.com/user-attachments/assets/c52ae7e7-7d94-4010-8c48-2913a11988ea" />

**Benefits:**
* ✅ Database abstraction
* ✅ Easy to switch databases
* ✅ Centralized queries
* ✅ Testable with mocks

---

### <a id="security"></a>🔐 Security Implementation (10 Layers)

#### Defense in Depth Strategy

```text
Layer 10: Logging & Monitoring (Morgan)
Layer 9:  SQL Injection Prevention (Parameterized Queries)
Layer 8:  CORS (Whitelist Origins)
Layer 7:  Helmet.js (8+ Security Headers)
Layer 6:  Input Validation (express-validator)
Layer 5:  Rate Limiting (100 req/15min) + Account Lockout
Layer 4:  RBAC (4 Hierarchical Roles)
Layer 3:  JWT + Refresh Tokens (7d/30d)
Layer 2:  Argon2 Password Hashing (64 MB memory)
Layer 1:  Mandatory 2FA (TOTP/Google Authenticator)
```

---

#### 🔑 Layer 1: Mandatory 2FA (TOTP)
**Why 2FA is Mandatory:**
* ✅ Protects against password theft
* ✅ Requires physical device access
* ✅ Industry standard (banking, enterprise)
* ✅ Compliance with security regulations

**Implementation:**

<img width="725" height="422" alt="image" src="https://github.com/user-attachments/assets/ad48ab09-a7b9-499a-8362-7900936bb256" />

**Authentication Flow:**

```text
1. User enters credentials
2. System validates password (Argon2)
3. If first login → Generate QR code
4. User scans QR in Google Authenticator
5. User enters 6-digit code
6. System validates TOTP code
7. If valid → Activate 2FA + Generate JWT
8. Future logins require 2FA code
```

---

#### 🔒 Layer 2: Argon2 Password Hashing
**Why Argon2 > bcrypt:**

| Feature | Argon2id | bcrypt |
| :--- | :--- | :--- |
| GPU Resistance | ✅ Excellent (64 MB RAM) | ⚠️ Moderate |
| ASIC Resistance | ✅ Excellent | ⚠️ Low |
| Memory Cost | 64 MB (configurable) | ~4 KB (fixed) |
| PHC Winner 2015 | ✅ Yes | ❌ No |
| OWASP Recommendation | ✅ First choice | ⚠️ Second choice |

**Configuration:**

<img width="726" height="165" alt="image" src="https://github.com/user-attachments/assets/c992516e-3196-4562-bbbd-008bb217a76d" />

**Hash Format**

<img width="723" height="187" alt="image" src="https://github.com/user-attachments/assets/b52e5cb4-fc92-43c2-9dfe-d58fbae01224" />

---

#### 🎫 Layer 3: JWT + Refresh Tokens
**Dual Token Strategy:**

<img width="723" height="324" alt="image" src="https://github.com/user-attachments/assets/39548fba-09b0-4f50-a59c-87764be7013f" />

**Benefits:**
* ✅ Short access token = less risk if compromised
* ✅ Long refresh token = better UX
* ✅ Separate secrets = double security layer
* ✅ Granular revocation possible

---

#### 👥 Layer 4: RBAC (Role-Based Access Control)
**Hierarchical Roles:**

<img width="726" height="117" alt="image" src="https://github.com/user-attachments/assets/f7a99dad-92cf-4be9-9b10-96a19ddda63d" />

**Implementation:**

<img width="726" height="372" alt="image" src="https://github.com/user-attachments/assets/aee758cb-36be-4f93-bbec-84e46d4c2bed" />

**Database Constraint:**

<img width="723" height="118" alt="image" src="https://github.com/user-attachments/assets/681ade53-8201-473e-ad85-54e7679441b1" />

---

#### 🚦 Layer 5: Rate Limiting + Account Lockout
**HTTP Rate Limiting:**

<img width="723" height="141" alt="image" src="https://github.com/user-attachments/assets/d90d29a7-ec60-4daf-aebf-1d9ea41ddedc" />

**Database-Level Lockout:**

<img width="720" height="401" alt="image" src="https://github.com/user-attachments/assets/9e3b011c-d73e-43a1-baf7-d89635faa126" />

---

#### ✅ Layer 6: Input Validation
**Comprehensive Validation:**

<img width="724" height="272" alt="image" src="https://github.com/user-attachments/assets/d9dae6a8-e6a5-45f6-8308-79141a44cf27" />


**8 Validators Implemented:**
* authValidators
* usuarioValidators
* pacienteValidators
* citaValidators
* inventarioValidators
* pagoValidators
* staffValidators
* validationMiddleware

---

#### 🛡️ Layers 7-10: Additional Security
**Layer 7: Helmet.js**
* Content-Security-Policy
* X-Frame-Options: DENY
* Strict-Transport-Security
* 8+ security headers

**Layer 8: CORS**
* Whitelist origins
* Credentials support
* Controlled methods/headers

**Layer 9: SQL Injection Prevention**
* Parameterized queries (100%)
* No string concatenation
* Database constraints

**Layer 10: Logging**
* Morgan (HTTP logs)
* Error tracking
* Audit trail

---

#### 🎯 OWASP Top 10 Mitigation

| Vulnerability | Mitigation | Status |
| :--- | :--- | :---: |
| A01: Broken Access Control | RBAC + JWT + 2FA | ✅ |
| A02: Cryptographic Failures | Argon2 + HTTPS | ✅ |
| A03: Injection | Parameterized queries | ✅ |
| A04: Insecure Design | Defense in Depth | ✅ |
| A05: Security Misconfiguration | Helmet + CORS | ✅ |
| A06: Vulnerable Components | Updated dependencies | ✅ |
| A07: Authentication Failures | 2FA + Rate limiting | ✅ |
| A08: Software Integrity | Input validation | ✅ |
| A09: Logging Failures | Morgan + monitoring | ✅ |
| A10: SSRF | Input validation | ✅ |

**Result: 10/10 vulnerabilities mitigated ✅**
---

## <a id="stack"></a>💻 Technology Stack

#### Backend
* **Runtime:** Node.js 18+
* **Framework:** Express.js 5.1.0
* **Language:** JavaScript (CommonJS)
* **Database:** PostgreSQL 14+
* **ORM/Query:** Native `pg` driver with connection pooling

#### Frontend
* **Framework:** React 19.2.0
* **Language:** TypeScript 5.9.3
* **Build Tool:** Vite 7.2.4
* **Optimization:** React Compiler (babel-plugin-react-compiler)
* **Styling:** Tailwind CSS 4.1.17
* **Routing:** React Router DOM 7.9.6
* **HTTP Client:** Axios 1.13.2
* **Charts:** Recharts 3.5.1, Chart.js 4.5.1
* **Icons:** Lucide React 0.554.0

#### Security
* **Password Hashing:** Argon2 0.44.0
* **JWT:** jsonwebtoken 9.0.2
* **2FA:** speakeasy 2.0.0
* **QR Codes:** qrcode 1.5.4
* **Security Headers:** helmet 8.1.0
* **Rate Limiting:** express-rate-limit 8.2.1
* **CORS:** cors 2.8.5
* **Validation:** express-validator 7.3.1

#### Third-Party Integrations
* **Payments:** mercadopago 2.11.0
* **AI/ML:** @google/generative-ai 0.24.1 (Gemini)
* **Email:** nodemailer 7.0.11
* **Reports:** exceljs 4.4.0
* **Cron Jobs:** node-cron 4.2.1

#### DevOps
* **Logging:** morgan 1.10.1
* **Environment:** dotenv 17.2.3
* **Testing:** jest 30.2.0, supertest 7.1.4
---

## <a id="features"></a>✨ Key Features

#### 🏥 Medical Management
* ✅ Patient (pet) registration with complete medical history
* ✅ Appointment scheduling with calendar integration
* ✅ Treatment records with prescriptions
* ✅ Automated appointment reminders via email
* ✅ Follow-up control notifications

#### 💼 Business Operations
* ✅ Real-time analytics dashboard with KPIs
* ✅ Inventory management with low-stock alerts
* ✅ Sales tracking and reporting
* ✅ Excel report generation
* ✅ AI-powered business insights (Google Gemini)

#### 💳 Payment Processing
* ✅ MercadoPago integration (test & production modes)
* ✅ Webhook handling for async payment confirmation
* ✅ Payment status tracking (Pending/Approved/Rejected/Refunded)
* ✅ Complete transaction traceability

#### 👥 User Management
* ✅ 4 hierarchical roles (Manager, Veterinarian, Receptionist, Client)
* ✅ Mandatory 2FA for all users
* ✅ Staff management (only by Manager)
* ✅ Client self-registration
* ✅ Activity logging and audit trail

#### 🤖 Automation
* ✅ Cron jobs for scheduled tasks
* ✅ Automated email notifications with HTML templates
* ✅ Low-stock inventory alerts
* ✅ Appointment reminders (24h before)
* ✅ Follow-up control notifications
---

## <a id="database"></a>💾 Database Design

#### Schema Overview
**13 Relational Tables:**

1. `rol` - System roles
2. `usuarios` - Users with 2FA
3. `pacientes` - Pets/patients
4. `tipo_servicio` - Service categories
5. `servicio` - Veterinary services
6. `citas` - Appointments
7. `cita_servicio` - Appointment-service relationship (N:M)
8. `tratamientos` - Medical treatments
9. `producto` - Inventory
10. `venta` - Product sales
11. `detalle_venta` - Sale details
12. `salida_insumo` - Supplies used in appointments
13. `pago` - Payments with MercadoPago integration

#### Advanced Features
**Triggers:**

<img width="721" height="275" alt="image" src="https://github.com/user-attachments/assets/cf78b433-5758-450d-976f-29ad056f1973" />

**Materialized Views:**

<img width="723" height="282" alt="image" src="https://github.com/user-attachments/assets/04653a73-9f45-40ee-a0cb-448b16a66bcc" />

**Strategic Indexes:**

<img width="721" height="357" alt="image" src="https://github.com/user-attachments/assets/05e3de70-dc28-4472-8a34-c8d63d2e0d83" />

---

### <a id="screenshots"></a>📷 System Screenshots

**Dashboard Analytics**
* ![Dashboard](link_a_tu_imagen) *Real-time KPIs, charts, and AI-powered insights*

**Appointment Management**
* ![Appointments](link_a_tu_imagen) *Calendar view with drag-and-drop scheduling*

**2FA Setup**
* ![2FA](link_a_tu_imagen) *Mandatory 2FA setup with Google Authenticator*

**Payment Integration**
* ![Payments](link_a_tu_imagen) *MercadoPago integration with webhook handling*

**Inventory Management**
* ![Inventory](link_a_tu_imagen) *Inventory tracking with automated alerts*

**Medical Records**
* ![Medical](link_a_tu_imagen) *Complete patient medical history and treatments*

---

### <a id="why"></a>🤔 Why This Architecture?

#### Scalability
* **Service Layer Pattern:** Easy to add new features without touching existing code
* **Repository Pattern:** Can switch databases without changing business logic
* **Microservices-Ready:** Services are independent and can be extracted

#### Maintainability
* **MVC Architecture:** Clear separation of concerns
* **TypeScript:** Type safety prevents runtime errors
* **Clean Code:** Meaningful names, small functions, DRY principle

#### Security
* **Defense in Depth:** 10 layers of security
* **OWASP Compliance:** Mitigates all Top 10 vulnerabilities
* **Modern Algorithms:** Argon2, TOTP, JWT

#### Performance
* **React Compiler:** Automatic optimization of re-renders
* **Vite:** Ultra-fast HMR and build times
* **Connection Pooling:** Efficient database connections
* **Strategic Indexes:** Optimized query performance
* **Caching:** Gemini AI responses cached to reduce costs

#### Developer Experience
* **TypeScript:** IntelliSense and type checking
* **ESLint:** Code quality enforcement
* **Hot Module Replacement:** Instant feedback during development
* **Structured Logging:** Easy debugging
---

### 📊 Project Metrics

* **Backend:** 15 services, 12 controllers, 9 models, 4 middlewares
* **Frontend:** 62 components, 23 pages, 9 custom hooks
* **Database:** 13 tables, 3 triggers, 3 views, 4 functions, 15+ indexes
* **Security:** 10 layers, 8 validators, 2FA mandatory
* **Integrations:** 3 external APIs (MercadoPago, Gemini, Email)
* **Patterns:** 4 architectural + 7 design patterns
* **SOLID:** All 5 principles applied
* **OWASP:** 10/10 vulnerabilities mitigated

---

### 🎓 What I Learned

#### Technical Skills
* ✅ Full-stack development with modern technologies
* ✅ Enterprise-level security implementation
* ✅ Database design and optimization
* ✅ Third-party API integration
* ✅ Design patterns in practice
* ✅ SOLID principles application
* ✅ TypeScript for type safety
* ✅ Performance optimization

#### Soft Skills
* ✅ Problem-solving (debugging webhooks, async flows)
* ✅ Self-learning (React Compiler, Argon2, 2FA)
* ✅ Attention to detail (security, validation, edge cases)
* ✅ Architectural thinking (scalability, maintainability)
* ✅ Project management (Scrum methodology)

---

### 🚀 Future Enhancements

* [ ] Real-time notifications with WebSockets
* [ ] Mobile app (React Native)
* [ ] Advanced analytics with ML predictions
* [ ] Multi-clinic support (SaaS)
* [ ] Telemedicine integration
* [ ] Automated testing (unit, integration, e2e)
* [ ] CI/CD pipeline (GitHub Actions)
* [ ] Docker containerization
* [ ] Kubernetes orchestration
* [ ] Monitoring with Grafana/Prometheus

---

### <a id="contact"></a>📞 Contact

<div align="center">

**Yordan Loayza**
*Full-Stack Developer | Security Enthusiast | Architecture Advocate*

<a href="mailto:yordanloayzaf@gmail.com">
  <img src="https://img.shields.io/badge/Gmail-Contact_Me-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
</a>
<a href="https://linkedin.com/in/yordan-camilo">
  <img src="https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
</a>
<a href="https://github.com/Yordan-Loayza">
  <img src="https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
</a>

</div>

---

### 📄 License

This architecture showcase is for portfolio purposes. The complete source code is proprietary.

---

### ⭐ Acknowledgments

<div align="center">

*Built with passion for clean code, security, and scalable architecture.*

| Category | Technologies |
| :--- | :--- |
| **Stack** | React, Node.js, PostgreSQL, TypeScript, Vite, Tailwind |
| **Patterns** | MVC, Singleton, Factory, Strategy, Observer, Repository |
| **Security** | Argon2, JWT, 2FA/TOTP, RBAC, Helmet, Rate Limiting |

<br>

**⚡ Built with enterprise-grade security and modern architecture ⚡**

</div>

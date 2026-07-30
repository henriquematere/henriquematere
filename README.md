<div align="center">

# Henrique Matere

### 💻 Full-Stack Developer · Internal systems, PWAs & process automation

**I build the systems that replace spreadsheets, paper and manual process, from the data model to production deployment.**

<a href="https://hemaco.com.br"><img src="https://img.shields.io/badge/Portfolio-hemaco.com.br-6C2BD9?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Portfolio" /></a>
<a href="https://www.linkedin.com/in/henriquematere/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
<a href="mailto:contato@hemaco.com.br"><img src="https://img.shields.io/badge/E--mail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="E-mail" /></a>

</div>

---

## 👋 About me

I am a full-stack developer, graduated in **Systems Analysis and Development (IFMS, Brazil)**. I work on development and process automation at **Gala IBB**, and I run my own projects under the **[Hemaco IT](https://hemaco.com.br)** brand: internal systems, Python automations and web dashboards for companies still running on spreadsheets, paper and manual process.

What I like is solving a **real business problem**. I take a messy operation and hand back a system that is organized, traceable and live in production. I am currently going deeper into **automation with AI and agents**.

The same shape repeats across most of what I ship: an installable client that keeps working without network, a lean API, a separate worker for anything that must not block a request, and versioned deploys to my own VPS.

---

## 📊 Activity

<div align="center">

<img src="https://raw.githubusercontent.com/henriquematere/henriquematere/main/assets/streak.svg" alt="Contribution streak" width="495" />

</div>

---

## 🛠️ Tech Stack

**Frontend**

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)

**Backend**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Fastify](https://img.shields.io/badge/Fastify-000000?style=for-the-badge&logo=fastify&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)

**Data**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Drizzle](https://img.shields.io/badge/Drizzle-C5F74F?style=for-the-badge&logo=drizzle&logoColor=black)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white)

**Infra & Tooling**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![nginx](https://img.shields.io/badge/nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

**Mobile & Automation**

![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=for-the-badge&logo=selenium&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

---

## 🚀 Selected Projects

> These systems run for clients and for internal use, and they live in **private repositories** for confidentiality. That is why this profile has no open code. Private does not mean opaque: I walk through the architecture, the technical decisions and the code itself on request. Case studies at **[hemaco.com.br](https://hemaco.com.br)**.

**✅ Safety and compliance checklist system** `in production for ~1 year, in daily use`
Three role levels with a guard against privilege escalation, a full audit trail (logins, edits, deletions, password resets), feature flags, and a maintenance mode that returns 503 to everyone except the master account. Field photo upload handling EXIF and HEIC, reports in PDF, CSV and Excel, installable as a PWA.
Operations: deploys run from GitHub Actions with the test suite gating them, a healthcheck after the systemd restart, and a concurrency group so two production deploys never overlap. Scheduled e-mail dispatch is protected by a database lock against double sending, backed by a watchdog and a backlog resend. Replacing an in-memory O(N) history scan with SQL pagination, eager loading and indexes fixed the main performance problem.
`Flask` · `SQLAlchemy` · `PostgreSQL` · `GitHub Actions` · `systemd` · `pytest` · `ruff`

**🍽️ Multi-tenant tab and order system for bars and events**
Multi-tenant, with database access scoped per tenant and covered by integration tests. The kitchen display streams over SSE for real time updates, orders route to preparation stations, and a schema-level constraint enforces one open order per table instead of trusting application code to do it.
`Next.js` · `TypeScript` · `Prisma` · `PostgreSQL` · `Auth.js` · `vitest`

**🧾 Offline-first POS**
Checkout that keeps selling with the internet down. Offline state in IndexedDB through Dexie, and sync as an append-only log that is idempotent by UUID, with the final state derived from the log instead of resolved by overwrite. HMAC token issued at login so the app keeps working offline afterwards. Monorepo, deployed by GitHub Actions over SSH with Docker Compose behind nginx.
`React + Vite` · `Fastify` · `node:sqlite` · `Dexie` · `Docker`

**📣 WhatsApp offer automation for a pharmacy**
Web and worker split into separate processes: Gunicorn behind nginx for the panel, and a worker with a dynamic scheduler for the automation itself. Send queue with retry and backoff, persistent automation state (running or paused, last success, last error), an endpoint to re-drive failed dispatches, a health endpoint, login lockout, CSRF on every mutating route, soft delete and an admin audit trail.
`Flask` · `Python` · `WPPConnect` · `Gunicorn`

**📐 Floor plan editor**
Two engines carry the work: one derives walls from room geometry, the other validates rules such as window presence, setback, built area and overlap. Pure SVG canvas with pan, zoom and drag, undo and redo on the state store, and export to PNG and PDF.
`Next.js` · `React` · `SVG` · `Zustand + zundo` · `dnd-kit` · `Prisma`

**💰 Household finance and investment tracker**
Self-hosted and multi-user, mobile-first PWA with offline support. Pulls B3 quotes from brapi.dev and CDI/SELIC rates from the Brazilian Central Bank API, so it tracks investments and not only expenses. Versioned migrations are the only accepted path to a production schema change.
`Next.js` · `TypeScript` · `Drizzle` · `PostgreSQL` · `Auth.js` · `Serwist`

**🗓️ Clinic scheduling**
The secretary controls the slots and each practitioner sees only their own schedule, on their phone. The scope is deliberately narrow: it is a scheduling system, and it stores no diagnosis and no clinical record.
`Flask` · `Flask-Login` · `Tailwind`

---

<div align="center">

**[hemaco.com.br](https://hemaco.com.br)** · **[LinkedIn](https://www.linkedin.com/in/henriquematere/)** · **[contato@hemaco.com.br](mailto:contato@hemaco.com.br)**

</div>

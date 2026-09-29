# HRMS Lean V1

<!-- repository-profile:start -->
## Repository profile

**Purpose:** A React/Express implementation of HRMS Lean V1 covering employees, departments, attendance, leave, payroll, and role-based dashboards.

**Core contents:** React frontend; Express backend; Prisma/PostgreSQL persistence; JWT authentication; documentation and frontend/backend test commands.

**Current status:** The repository appears closely related to `HRMS-NEW`, but it has a smaller root workspace and fewer root-level verification tools. It should not be assumed to be the canonical or newest copy until histories and unique changes are compared.

**Recommended next milestone:** Compare it with `HRMS-NEW` and `IntelliHRM`; label it as canonical, historical, or experimental and preserve any unique work before consolidation.
<!-- repository-profile:end -->

Lean, production-ready HRMS MVP built with:

- React
- Express
- Prisma
- PostgreSQL
- JWT authentication

## Project Structure

- `backend/` Express API, Prisma schema, seed script
- `frontend/` React app for HRMS workflows
- `docs/` architecture and planning documents

## Setup & Local Development

Follow these steps to get the project running locally:

### 1. Initial Installation
Install all dependencies for both frontend and backend using npm workspaces:
```powershell
npm install
```

### 2. Environment Configuration
Create `.env` files for both modules from their respective examples.

**Backend:** `backend/.env` (Update with **PostgreSQL URL**, `JWT_SECRET`, and VAPID keys)
**Frontend:** `frontend/.env` (Ensure `VITE_API_BASE_URL` points to your backend)

### 3. Database & Prisma Setup
Ensure your PostgreSQL server is running, then initialize the database:

```powershell
# Run migrations to create tables
npm --workspace backend run prisma:migrate

# Seed essential data (Roles, Departments, and Leave Types)
npm --workspace backend run prisma:seed
```

### 4. Running the Application
You can start both frontend and backend simultaneously from the root:

```powershell
# Start both in dev mode
npm run dev:backend
npm run dev:frontend
```
Alternatively, go into each directory and run `npm run dev`.

## Implemented Lean V1 Modules

- Auth: login, logout, current user
- Departments
- Employees
- Attendance
- Leave types, balances, requests, approval
- Payroll
- Role-based dashboards

## Notes

- Leave balances must exist for employees before leave approval can succeed.
- V1 uses role-based access in code and does not include refresh tokens, audit logs, or permissions.
- Payroll is intentionally simple in V1: one monthly record per employee.

## Repository family

This repository is a related HRMS variant. For the recommended primary portfolio implementation, start with [HRMS-NEW](https://github.com/vaishnavsawant1994-stack/HRMS-NEW). Preserve and compare any unique changes here before consolidation or archival.

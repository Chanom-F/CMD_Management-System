# 02 System Design

## Architecture

Use a modular monolith for MVP.

Frontend:
- Next.js
- TypeScript
- Responsive web UI

Backend:
- NestJS
- TypeScript
- REST API

Initial data:
- Google Sheets API

File storage:
- Google Drive API

Future:
- PostgreSQL

## Architectural Layers

Frontend
→ API Client
→ NestJS Controller
→ Application Service
→ Domain/Business Logic
→ Repository Interface
→ Repository Implementation

Example:

CandidateController
→ CandidateService
→ CandidateRepository
→ GoogleSheetsCandidateRepository

Later:

CandidateService
→ CandidateRepository
→ PostgresCandidateRepository

## Rules

1. Controllers contain request/response concerns only.
2. Business rules belong in services/domain layer.
3. Google API calls belong in infrastructure/adapters.
4. Do not import Google Sheets API directly into business services.
5. Do not expose Google credentials to frontend.
6. Use stable entity IDs.
7. Use DTO validation.
8. Keep repository interfaces storage-agnostic.
9. Centralize error handling.
10. Centralize authorization.

## Suggested Backend Modules

- auth
- users
- employees
- candidates
- candidate-files
- clients
- projects
- project-members
- project-statuses
- outsource-positions
- candidate-applications
- application-statuses
- audit
- dashboard
- integrations/google

## Suggested Frontend Areas

/app
  /dashboard
  /candidates
  /employees
  /projects
  /outsourcing
  /clients
  /settings
  /users
  /reports

## Authentication

Preferred for internal use:
- Google Workspace OAuth / Google Identity

The exact OAuth configuration shall be documented separately and must not be hard-coded.

## Authorization

Implement RBAC.

Initial roles:
- Super Admin
- Admin
- HR / Recruiter
- Project Manager
- Manager
- Viewer

Permission examples:
- candidate.read
- candidate.create
- candidate.update
- candidate.delete
- candidate.file.upload
- project.read
- project.create
- project.update
- project.member.manage
- outsourcing.read
- outsourcing.position.manage
- outsourcing.application.manage
- master.manage
- user.manage
- audit.read

Do not rely solely on frontend hiding buttons. Backend must enforce permissions.

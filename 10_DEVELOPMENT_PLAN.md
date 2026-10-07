# 10 Development Plan

## Phase 0 — Discovery

Codex must:
1. Inspect repository.
2. Detect existing stack.
3. Detect package manager.
4. Identify existing conventions.
5. Identify environment configuration.
6. Produce implementation plan.
7. Do not make code changes until plan is reviewed.

## Phase 1 — Foundation

Implement:
- Next.js app structure
- NestJS app structure
- Shared types where appropriate
- Environment config
- Authentication skeleton
- RBAC
- Layout/navigation
- Error handling
- Logging
- Google API integration abstraction
- Repository interfaces
- Google Sheets repository
- Google Drive file service
- Basic test setup

Acceptance:
- User can authenticate.
- Unauthorized endpoints are blocked.
- Google integration credentials are server-side.
- Build/lint/tests pass.

## Phase 2 — Candidate

Implement:
- Candidate CRUD
- Search/filter
- Status
- Candidate detail
- File upload
- Drive folder/file handling
- Application history view

Acceptance:
- Create/edit/view candidate.
- Upload and view Resume.
- Candidate data is persisted to Google Sheets.
- File metadata is persisted.
- No direct frontend Google API access.

## Phase 3 — Employee and Project

Implement:
- Employee CRUD
- Project CRUD
- Project status
- Project members
- Multiple project membership
- Allocation

Acceptance:
- Same employee can belong to multiple projects.
- Add/remove member works.
- Status changes are logged.

## Phase 4 — Outsourcing

Implement:
- Client
- Position
- Candidate application
- Configurable statuses
- Kanban
- Drag/drop status
- Application history

Acceptance:
- Candidate can be submitted to multiple positions.
- Moving a card changes application status.
- History is recorded.
- Position can be closed/reopened.

## Phase 5 — Dashboard

Implement:
- KPI cards
- Project status summary
- Candidate summary
- Outsourcing pipeline summary
- Resource allocation summary

## Phase 6 — Hardening

- Validation
- Permission review
- Error handling
- Performance review
- Accessibility
- Security review
- Backup/recovery procedure
- Test coverage
- User acceptance test

## Phase 7 — PostgreSQL Migration (Future)

Create PostgreSQL repository implementation.

Do not change:
- Domain model
- API contract
- Frontend behavior
- Business services

Migration approach:
1. Freeze schema.
2. Create PostgreSQL schema.
3. Build migration/import script.
4. Validate record counts.
5. Validate relationships.
6. Run parallel verification.
7. Switch repository implementation.
8. Keep Drive integration unchanged.

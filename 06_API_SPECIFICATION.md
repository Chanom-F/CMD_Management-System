# 06 API Specification

Base path:
`/api/v1`

## Candidates

GET /candidates
GET /candidates/:id
POST /candidates
PATCH /candidates/:id
DELETE /candidates/:id
PATCH /candidates/:id/status
GET /candidates/:id/files
POST /candidates/:id/files
DELETE /candidates/:id/files/:fileId
GET /candidates/:id/applications

## Employees

GET /employees
GET /employees/:id
POST /employees
PATCH /employees/:id
PATCH /employees/:id/status

## Clients

GET /clients
GET /clients/:id
POST /clients
PATCH /clients/:id

## Projects

GET /projects
GET /projects/:id
POST /projects
PATCH /projects/:id
PATCH /projects/:id/status
GET /projects/:id/members
POST /projects/:id/members
DELETE /projects/:id/members/:memberId

## Outsource Positions

GET /outsource-positions
GET /outsource-positions/:id
POST /outsource-positions
PATCH /outsource-positions/:id
PATCH /outsource-positions/:id/status
GET /outsource-positions/:id/applications

## Applications

GET /applications
GET /applications/:id
POST /applications
PATCH /applications/:id
PATCH /applications/:id/status
GET /applications/:id/history

## Dashboard

GET /dashboard/summary
GET /dashboard/candidates
GET /dashboard/projects
GET /dashboard/outourcing

## API Rules

- Validate all DTOs.
- Authenticate all protected endpoints.
- Authorize by permission.
- Never expose Google access tokens.
- Return consistent error format.
- Use pagination for list endpoints.
- Support search/filter query parameters.
- Do not expose internal Google Sheet row numbers as IDs.

# 11 Acceptance Criteria

## General

- All protected functionality requires authentication.
- RBAC is enforced server-side.
- Stable IDs are used.
- Important mutations are auditable.
- No secrets are committed to source control.
- Application builds successfully.
- Tests pass.
- Lint passes.

## Candidate

- User can create candidate.
- User can edit candidate.
- User can search/filter candidate.
- User can change candidate profile status.
- User can upload Resume.
- Resume is stored in Google Drive.
- CandidateFile stores Drive file ID.
- User can view/download authorized file.
- Candidate can have multiple applications.

## Project

- Admin can create project.
- Admin can change project status.
- Admin can add/remove employees.
- Employee can belong to multiple projects.
- Project membership changes are audited.

## Outsourcing

- User can create client.
- User can create position.
- User can attach candidate to position.
- Candidate can be attached to multiple positions.
- Application status can be changed.
- Kanban drag/drop works.
- Status history is recorded.
- Position can be closed.

## Future Database Readiness

- Business services do not depend directly on Google Sheets.
- Repository interface exists.
- Google Sheets implementation is replaceable.
- No frontend component depends on Google Sheets schema.
- Entity IDs are independent from sheet row numbers.

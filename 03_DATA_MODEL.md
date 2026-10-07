# 03 Data Model

## Core Entities

users
employees
clients
candidates
candidate_files
projects
project_members
project_statuses
outsource_positions
application_statuses
candidate_applications
application_status_history
audit_logs

## Relationships

Employee 1:N ProjectMember
Project 1:N ProjectMember
Client 1:N Project
Client 1:N OutsourcePosition
Candidate 1:N CandidateFile
Candidate 1:N CandidateApplication
OutsourcePosition 1:N CandidateApplication
CandidateApplication 1:N ApplicationStatusHistory
Project 1:N ProjectStatusHistory (recommended)
Any important entity 1:N AuditLog

## Important Rules

1. Candidate is a master entity.
2. CandidateApplication is the relationship between Candidate and OutsourcePosition.
3. Candidate status is NOT the same as Application status.
4. ProjectMember is the relationship between Employee and Project.
5. Employee may have many ProjectMember records.
6. A Candidate may have many Applications.
7. A Position may have many Candidates.
8. Client may have many Projects and Positions.
9. Statuses must be configurable.
10. Every entity uses a stable unique ID.

## ID Convention

Examples:
- CAND-000001
- EMP-000001
- CLI-000001
- PRJ-000001
- POS-000001
- APP-000001

The ID must not be based on name.

## Google Sheets MVP Tabs

1. Users
2. Employees
3. Clients
4. Candidates
5. CandidateFiles
6. Projects
7. ProjectMembers
8. ProjectStatuses
9. OutsourcePositions
10. ApplicationStatuses
11. CandidateApplications
12. ApplicationStatusHistory
13. AuditLogs
14. SystemConfig

Each sheet has a header row and stable column names. Do not rename columns casually after implementation.

## Migration Principle

Google Sheets is an implementation detail.

The domain model must remain compatible with PostgreSQL.

Do not use spreadsheet row number as entity ID.

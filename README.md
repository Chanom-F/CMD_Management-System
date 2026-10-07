# CODEMONDAY Management Platform

Version: 1.0
Status: MVP Specification
Purpose: Internal management platform for Candidate, Employee, Project, Resource Allocation, Client and Outsourcing Pipeline management.

## Core Architecture Principle

Initial persistence:
- Google Sheets: structured business data
- Google Drive: Resume and document storage

Future persistence:
- PostgreSQL

The application MUST use a backend service/repository abstraction. Frontend MUST NOT access Google Sheets directly. Business logic MUST NOT depend directly on Google Sheets APIs.

Target architecture:

Next.js Frontend
→ NestJS Backend
→ Domain/Application Services
→ Repository Interfaces
→ Google Sheets Repository (MVP)
→ Google Drive File Service

Later:
→ PostgreSQL Repository

## MVP Scope

1. Authentication and RBAC
2. Candidate Database
3. Candidate file management via Google Drive
4. Employee master
5. Internal Project Management
6. Project member/resource allocation
7. Client master
8. Outsourcing Position Management
9. Candidate-to-Position Application Pipeline
10. Kanban/drag-and-drop status management
11. Status history and audit log
12. Basic management dashboard

Do not add unrelated features without approval.

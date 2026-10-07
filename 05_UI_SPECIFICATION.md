# 05 UI Specification

## Global Layout

Left sidebar:
- Dashboard
- Candidates
- Employees
- Projects
- Outsourcing
- Clients
- Reports
- Settings

Top bar:
- Search
- Notifications (future)
- User menu

Use a clean modern business UI. Avoid overly decorative visual styles.

## Candidate List

Required:
- Search
- Filters
- Sort
- Pagination
- Create Candidate
- Open Candidate Detail

Suggested filters:
- Position
- Status
- Availability
- Owner
- Salary range
- Last updated

## Candidate Detail

Sections:
1. Basic Information
2. Professional Information
3. Recruitment Information
4. Documents
5. Application History
6. Activity/Audit History

Actions:
- Edit
- Upload Resume
- Add Document
- Change Status
- Submit to Position

## Project List

Table/card view:
- Project name
- Client
- Status
- Owner
- Start date
- End date
- Member count

Actions:
- Create
- Edit
- Open

## Project Detail

Header:
- Project name
- Client
- Status
- Owner
- Dates

Members section:
- Available employees
- Assigned members

Use drag-and-drop or clear Add/Remove controls.

Show allocation percentage if enabled.

## Outsourcing Kanban

Board:
- Position selector
- Client
- Search candidate
- Filter

Columns:
- Configurable application statuses

Candidate card:
- Candidate name
- Position
- Current/expected salary where permitted
- Owner
- Last updated
- Interview date if applicable

Click card opens application detail.

Drag-and-drop must show a confirmation only where the transition is sensitive or irreversible.

## Responsive

Desktop-first because this is an internal management platform.
Tablet support is required.
Mobile can be basic for MVP.

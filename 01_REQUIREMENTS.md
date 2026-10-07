# 01 Requirements

## 1. Candidate Database

The system shall allow authorized users to:
- Create candidate profiles
- Edit candidate profiles
- View candidate details
- Search and filter candidates
- Track current salary
- Track expected salary
- Track latest update date
- Track profile owner
- Track candidate availability/profile status
- Attach one or more documents
- View/download candidate documents
- Maintain important status history

Candidate fields:
- candidate_id
- first_name
- last_name
- nickname
- phone
- email
- position
- current_salary
- expected_salary
- availability
- profile_status
- last_updated_at
- owner_user_id
- remark
- created_at
- created_by
- updated_at
- updated_by

The initial required business status may be "Open" / "Closed", but the implementation must support configurable status master data.

## 2. Candidate Documents

Documents are stored in Google Drive.

Minimum document metadata:
- file_id
- candidate_id
- file_name
- mime_type
- google_drive_file_id
- google_drive_url
- document_type
- uploaded_by
- uploaded_at

Recommended document types:
- Resume
- Portfolio
- Certificate
- Other

## 3. Employee

Admin can maintain employee records used for project assignment.

Minimum fields:
- employee_id
- employee_code
- name
- nickname
- email
- job_title
- department
- employment_status
- skills
- active_flag

## 4. Internal Project Management

Authorized users can:
- Create project
- Edit project
- Change project status
- Archive project
- View project details
- Add/remove members
- Assign one employee to multiple projects
- Search/filter projects

Project fields:
- project_id
- project_code
- project_name
- client_id
- description
- start_date
- end_date
- project_status_id
- project_owner_id
- remark
- created_at
- updated_at

Project member allocation:
- project_member_id
- project_id
- employee_id
- allocation_percent (optional but recommended)
- allocation_start_date
- allocation_end_date
- role_in_project
- status

Employee MUST be allowed to belong to more than one project.

## 5. Project Status

Statuses are configurable by Admin.

Example defaults:
- Planning
- Development
- Testing
- UAT
- Go Live
- Maintenance
- Completed
- On Hold
- Cancelled

Admin can add/edit/reorder/deactivate statuses.

Do not hard-code business status logic into UI components.

## 6. Client

Client master is required because outsourcing positions and projects belong to clients.

Minimum fields:
- client_id
- client_code
- client_name
- status
- contact_name
- contact_email
- contact_phone
- remark

## 7. Outsourcing Position

Authorized users can:
- Create position
- Edit position
- Close position
- Reopen position
- View position
- Assign candidates
- View candidate pipeline

Minimum fields:
- position_id
- position_code
- client_id
- position_title
- required_headcount
- salary_range
- required_skills
- job_description
- open_date
- target_start_date
- position_status
- owner_user_id
- remark

## 8. Candidate Application

A candidate may be submitted to multiple positions and clients.

This MUST be modeled as a separate entity.

Minimum fields:
- application_id
- candidate_id
- position_id
- application_status_id
- submitted_at
- interview_date
- result
- owner_user_id
- remark
- created_at
- updated_at

Example pipeline:
- New
- Submitted to Client
- Client Reviewing
- Interview
- Second Interview
- Offer
- Selected
- Rejected
- Withdrawn
- Closed

Statuses must be configurable.

## 9. Kanban

Outsourcing candidate pipeline shall be displayed as a Kanban board.

Each column represents a configurable application status.

Users with permission can drag a candidate card from one status to another.

Every status change must create history:
- application_id
- old_status
- new_status
- changed_by
- changed_at
- remark

## 10. Dashboard

Initial dashboard:
- Total candidates
- Available candidates
- Active projects
- Employees assigned to projects
- Employees with no active project
- Open outsourcing positions
- Candidate applications by stage
- Selected candidates
- Rejected candidates
- Projects by status

Dashboard is management-oriented, not a detailed BI system.

## 11. Audit Log

Important mutations must be logged:
- Create
- Update
- Delete/archive
- Status change
- Assignment change
- File upload/delete

Minimum:
- audit_id
- entity_type
- entity_id
- action
- before_value
- after_value
- changed_by
- changed_at

Do not store sensitive file contents in audit logs.

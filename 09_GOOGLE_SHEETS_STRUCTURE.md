# 09 Google Sheets Structure

Workbook name:
CODEMONDAY_Management_MVP

## Users

user_id | email | name | role_id | status | created_at | updated_at

## Employees

employee_id | employee_code | name | nickname | email | job_title | department | employment_status | skills | active_flag | created_at | updated_at

## Clients

client_id | client_code | client_name | status | contact_name | contact_email | contact_phone | remark | created_at | updated_at

## Candidates

candidate_id | first_name | last_name | nickname | phone | email | position | current_salary | expected_salary | availability | profile_status_id | owner_user_id | remark | created_at | created_by | updated_at | updated_by

## CandidateFiles

candidate_file_id | candidate_id | document_type | file_name | mime_type | google_drive_file_id | google_drive_url | size_bytes | uploaded_by | uploaded_at | status

## Projects

project_id | project_code | project_name | client_id | description | start_date | end_date | project_status_id | project_owner_id | remark | created_at | updated_at

## ProjectMembers

project_member_id | project_id | employee_id | allocation_percent | allocation_start_date | allocation_end_date | role_in_project | status | created_at | updated_at

## ProjectStatuses

project_status_id | status_name | display_order | active_flag | created_at | updated_at

## OutsourcePositions

position_id | position_code | client_id | position_title | required_headcount | salary_range | required_skills | job_description | open_date | target_start_date | position_status | owner_user_id | remark | created_at | updated_at

## ApplicationStatuses

application_status_id | status_name | display_order | active_flag | created_at | updated_at

## CandidateApplications

application_id | candidate_id | position_id | application_status_id | submitted_at | interview_date | result | owner_user_id | remark | created_at | updated_at

## ApplicationStatusHistory

history_id | application_id | old_status_id | new_status_id | changed_by | changed_at | remark

## AuditLogs

audit_id | entity_type | entity_id | action | before_value | after_value | changed_by | changed_at

## SystemConfig

config_key | config_value | description | updated_at

## Spreadsheet Rules

- Header row is immutable after implementation.
- Never use row number as primary key.
- Never store passwords.
- Never store Google credentials.
- Dates use ISO format where possible.
- Numeric fields remain numeric.
- Do not merge cells.
- Do not insert decorative rows into data tabs.

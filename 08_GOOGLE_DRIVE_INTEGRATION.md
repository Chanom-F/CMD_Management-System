# 08 Google Drive Integration

## Purpose

Use Google Drive for Candidate documents.

Recommended:
Google Workspace Shared Drive rather than an employee's personal My Drive.

## Folder Structure

/CODEMONDAY Management
  /Candidates
    /CAND-000001
    /CAND-000002
  /Projects
  /Outsourcing

Candidate folder can contain:
- Resume
- Portfolio
- Certificate
- Other

## File Flow

Frontend
→ Backend upload endpoint
→ Validate type/size
→ Google Drive API
→ Shared Drive candidate folder
→ Save Google Drive file ID and metadata to CandidateFiles

## Security

- Google credentials remain server-side.
- Do not expose service account/private credentials to browser.
- Do not store file binary in Google Sheets.
- Store only metadata and Drive file ID in Google Sheets.
- Use least privilege.
- Do not make all files public.
- Respect organizational Google Workspace permissions.

## File Metadata

candidate_file_id
candidate_id
document_type
file_name
mime_type
google_drive_file_id
google_drive_url
size_bytes
uploaded_by
uploaded_at
status

## Future

Drive can remain as production document storage even after PostgreSQL migration.

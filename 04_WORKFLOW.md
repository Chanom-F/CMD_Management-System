# 04 Workflow

## Candidate

Create Candidate
→ Active/Available
→ Candidate may be submitted to one or more positions
→ Candidate profile can later be closed/inactivated

Candidate status and application status are independent.

## Internal Project

Create Project
→ Planning
→ Development
→ Testing
→ UAT
→ Go Live
→ Maintenance
→ Completed

Admin can configure statuses.

## Project Assignment

Select Project
→ Open employee selector
→ Search employees
→ Add employee
→ Set role/allocation if applicable
→ Save

Employee may appear in multiple projects.

Remove assignment:
Project
→ Member
→ Remove
→ Confirm
→ Create audit record

## Outsourcing

Create Client
→ Create Position
→ Add/search Candidate
→ Create CandidateApplication
→ New
→ Submitted to Client
→ Client Reviewing
→ Interview
→ Result/Offer/Selected/Rejected

Drag-and-drop changes status.

Every transition creates history.

## Status Transition

Drag card
→ Frontend asks backend to change status
→ Backend validates permission
→ Backend validates target status
→ Save application
→ Append status history
→ Append audit log
→ Return updated card

Do not update Google Sheets directly from the browser.

## File Upload

Candidate
→ Upload Resume
→ Backend validates file
→ Upload to designated Google Drive folder
→ Save file metadata to CandidateFiles
→ Return file reference

File types and size limits must be configurable.

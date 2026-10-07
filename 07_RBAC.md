# 07 RBAC

## Roles

### Super Admin
Full system access.

### Admin
- Manage users
- Manage employees
- Manage clients
- Manage statuses/master data
- Manage projects
- Manage candidates
- Manage outsourcing
- View audit logs

### HR / Recruiter
- Candidate CRUD
- Candidate file management
- Client/position viewing
- Candidate application management
- Outsourcing pipeline management

### Project Manager
- View candidates as permitted
- View projects
- Manage assigned project members
- Update project status where permitted

### Manager
- View dashboard
- View projects
- View resource allocation
- View candidate/outsource summary as permitted

### Viewer
Read-only access.

## Security

Backend permission checks are mandatory.

Sensitive candidate information must not be exposed to roles that do not have permission.

Google Drive permissions should align with organizational access but application authorization remains the primary business authorization layer.

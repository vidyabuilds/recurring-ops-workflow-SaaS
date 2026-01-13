# ERD — MVP v1 Data Model

## Diagram
- [View full-size ERD](../assets/erd-mvp-v1.png)
  
![ERD — MVP v1](/docs/assets/erd-mvp-v1.png)

## Notes (design intent)
- Multi-tenancy is enforced via `workspace_id` (Workflows) and `Membership`.
- `Workflow` is the hub: defines recurrence + definition of done.
- `AssignmentRule` stores round-robin state (rotation list + index) per workflow.
- `ReminderConfig` is optional for drafts; created on publish with MVP defaults.
- `TaskInstance` is the atomic unit for metrics (due_at, status, completion time).
- `TaskCompletion` is 0..1 per task instance to support completion + guardrails (reopen).

## Minimal API surface (MVP v1)
### Workspace / Members
- POST /workspaces
- POST /workspaces/{id}/members
- GET /workspaces/{id}

### Workflows
- POST /workflows
- GET /workflows?workspace_id=
- GET /workflows/{id}
- PATCH /workflows/{id}
- POST /workflows/{id}/publish

### Tasks
- GET /tasks/my?workspace_id=&bucket=due_today|upcoming|overdue
- GET /tasks/{task_instance_id}
- POST /tasks/{task_instance_id}/complete
- POST /tasks/{task_instance_id}/reopen

### Dashboard (MVP-lite)
- GET /dashboard?workspace_id=
- GET /tasks/overdue?workspace_id=
- POST /tasks/{task_instance_id}/nudge

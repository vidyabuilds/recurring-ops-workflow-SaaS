# MVP Scope v1 — Recurring Ops Workflow SaaS

## MVP Goal
Ship the smallest product that reliably executes recurring work with clear ownership and reminders, and demonstrates measurable reduction in overdue tasks.

## Outcome & Success Metrics
**Desired outcome:** Reduce overdue recurring tasks by **40% in 30 days** (post-adoption).  
**North Star:** On-time completion rate (%)  
**Primary MVP metric:** % tasks overdue (due date + 24h grace)  
**Leading indicators:**
- Median time-to-complete (created → completed)
- Reminder engagement rate (% reminders that lead to task opened within 24h)

## MVP v1 Bundle (Must-have)
1) **Recurring workflows**
- Create workflow (name, description/definition of done)
- Set recurrence (daily/weekly/monthly) + start date
- Optional: due time

2) **Ownership & assignment**
- Invite members to a workspace
- Round-robin assignment across selected members
- Preview upcoming assignments (next 1–2 weeks)

3) **Member execution**
- “My Tasks” inbox (Due Today / Upcoming / Overdue)
- Task details page (definition of done)
- Mark task complete
- Completion history (basic)

4) **Reminders (MVP default schedule)**
- Configure reminders (default on)
- Reminders triggered before due / on due / overdue

5) **Basic visibility (MVP-lite, recommended)**
- Dashboard: on-time completion rate + overdue count + simple trend

## Out of Scope (v1)
- Weighted rotation (fairness scoring)
- Swap requests
- Evidence required (photo/link/file uploads)
- Complete → Verify approvals
- Escalation rules (overdue → notify admin/manager)
- Slack/Teams integrations, webhooks, public API
- Billing, SSO/SCIM, advanced RBAC

## Screens (v1)
**Admin**
1. Workspace setup (create workspace + invite members)
2. Workflow create/edit
3. Workflow preview (upcoming assignments)
4. Dashboard (basic)
5. Workflow list (manage workflows)

**Member**
6. My Tasks (Due Today / Upcoming / Overdue)
7. Task details
8. Completion confirmation / history view (simple)

## Data Model (v1 entities)
- **Workspace** (id, name, created_by)
- **User** (id, email, name)
- **Membership** (workspace_id, user_id, role: admin/member)
- **Workflow** (id, workspace_id, name, description, recurrence_rule, start_date, due_time)
- **AssignmentRule** (workflow_id, type: round_robin, members_in_rotation)
- **TaskInstance** (id, workflow_id, due_at, assignee_user_id, status: open/completed/overdue)
- **TaskCompletion** (task_instance_id, completed_at, completed_by)

## Analytics / Events (MVP)

Admin
- `workflow_create_started`
- `workflow_published`
- `tasks_generated`
- `reminders_configured`

Member
- `my_tasks_viewed`
- `task_opened`
- `task_completed`

Admin monitoring
- `dashboard_viewed`
- `overdue_list_viewed`
- `nudge_sent`

## Acceptance Criteria (v1)
**Admin setup**
- Admin can publish a workflow end-to-end in **<3 minutes** (happy path)
- System generates task instances and assignments for next 1–2 weeks

**Member completion**
- Member can find “Due Today” in **<10 seconds**
- Member can complete a task in **<60 seconds** with 0 critical confusion

**Reliability**
- Overdue status updates correctly (based on due_at + grace)
- Completion history is visible and accurate

## Validation Plan
**Usability test (5 users):**
- Admin journey: create → assign → reminders → publish
- Member journey: My Tasks → open → complete  
**Pilot (7–14 days):**
- Run MVP v1 bundle with 1 household/team
- Success: ≥20% reduction in overdue rate vs baseline week

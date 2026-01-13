# Core User Journeys — Recurring Ops Workflow SaaS

## Journey 1: Admin creates a recurring workflow (Happy Path)

**Goal:** Admin sets up a recurring workflow that auto-generates tasks with owners and reminders.

1. Admin creates a workspace (Household/Team) and invites members
2. Admin selects a template (e.g., “Roommate chores”) or creates a new workflow
3. Admin defines workflow details:
   - Workflow name
   - Description / definition of “done”
   - Recurrence (daily/weekly/monthly) + start date
   - Due time / grace period (optional)
4. Admin chooses assignment rule:
   - Round-robin rotation across selected members
5. System generates upcoming task instances (preview next 1–2 weeks)
6. Admin enables reminders:
   - Before due / due / overdue (MVP: default schedule)
7. Admin publishes/activates the workflow
8. Members receive tasks in “My Tasks” and reminders according to schedule

**Success criteria (MVP):**

- Time-to-first-workflow < 3 minutes for Admin
- Admin can preview next assignments without confusion

---

## Journey 2: Member completes assigned work (Happy Path)

**Goal:** Member sees assigned tasks, completes them quickly, and stays on track.

1. Member opens the app and lands on “My Tasks”
2. Member sees tasks grouped by:
   - Due today / Upcoming / Overdue
3. Member opens a task to view details (what “done” means)
4. Member marks task as complete
5. System records completion time and updates history
6. Member sees confirmation and next assigned tasks

**Success criteria (MVP):**

- Member finds “Due today” in < 10 seconds
- Member completes a task in < 60 seconds with no confusion

---

## Journey 3: Admin monitors and intervenes (MVP-lite)

**Goal:** Admin can see what’s overdue and take action.

1. Admin opens dashboard
2. Admin identifies:
   - Overdue tasks
   - On-time completion rate trend
3. Admin pings assignee (manual for MVP) or adjusts future assignments

**Success criteria (MVP-lite):**

- Admin answers “what’s overdue?” in < 60 seconds

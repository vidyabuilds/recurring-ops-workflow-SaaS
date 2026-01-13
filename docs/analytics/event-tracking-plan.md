# Analytics & Event Tracking Plan — MVP v1

## Goals
Instrument the MVP so we can measure:
- On-time completion rate (North Star)
- Overdue rate (primary MVP metric)
- Time-to-first-workflow (Admin activation)
- Member engagement with tasks and reminders
- Operational visibility usage (dashboard + overdue list)

## Metric Definitions
**On-time completion rate (%)**  
= (# tasks completed on/before due date) / (total tasks due) * 100

**Overdue rate (%)**  
= (# tasks not completed by due date + 24h grace) / (total tasks due) * 100

**Median time-to-complete**  
= median(completed_at - created_at) for task instances

**Reminder engagement rate (%)**  
= (% reminders that lead to task opened within 24h)

**Accidental completion rate (%)** (guardrail)  
= (# tasks reopened/undone within 5 minutes) / (# tasks completed) * 100

## Event Naming Conventions
- snake_case
- include workspace_id and user_id on all events
- include entity ids (workflow_id, task_instance_id) where relevant

## Event Schema (MVP)
Each event should include:
- `event_name`
- `timestamp`
- `workspace_id`
- `user_id`
- `role` (admin/member)
- `platform` (web)
- `session_id` (optional)

## Admin Events
### 1) workflow_create_started
**When:** Admin clicks “Create workflow” or selects a template  
**Properties:**
- `source` (template|blank)
- `template_name` (if template)

**Why:** Measures funnel entry / intent

### 2) workflow_published
**When:** Admin publishes/activates a workflow  
**Properties:**
- `workflow_id`
- `recurrence` (daily|weekly|monthly)
- `due_time_set` (true/false)
- `members_in_rotation_count 

**Why:** Primary activation event for Admin

### 3) tasks_generated
**When:** System generates task instances after publish  
**Properties:**
- `workflow_id`
- `task_instances_generated_count`
- `preview_window_days` (e.g., 7/14)

**Why:** Confirms core engine is working

### 4) reminders_configured
**When:** Admin enables reminders (or accepts default schedule)  
**Properties:**
- `workflow_id`
- `schedule_type` (default|custom)
- `pre_due_hours` (e.g., 24)
- `same_day_time` (e.g., 09:00)
- `overdue_hours` (e.g., 24)

**Why:** Links reminders to overdue reduction

## Member Events
### 5) my_tasks_viewed
**When:** Member opens My Tasks page  
**Properties:**
- `due_today_count`
- `overdue_count`
- `upcoming_count`

**Why:** Measures engagement and task load

### 6) task_opened
**When:** Member opens a task instance  
**Properties:**
- `task_instance_id`
- `workflow_id`
- `task_status` (open|overdue)

**Why:** Helps compute reminder engagement (opened after reminder)

### 7) task_completed
**When:** Member marks task complete  
**Properties:**
- `task_instance_id`
- `workflow_id`
- `task_status_before` (open|overdue)
- `completion_method` (button)

**Why:** Core conversion event

### 8) task_reopened (guardrail)
**When:** Member undoes completion / reopens  
**Properties:**
- `task_instance_id`
- `workflow_id`
- `minutes_since_completion`

**Why:** Accidental completion rate

## Admin Monitoring Events (MVP-lite)
### 9) dashboard_viewed
**When:** Admin opens dashboard  
**Properties:**
- `overdue_count`
- `on_time_rate` (optional if computed client-side)

**Why:** Measures visibility usage

### 10) overdue_list_viewed
**When:** Admin opens overdue tasks list  
**Properties:**
- `filter_workflow_id` (optional)
- `overdue_count`

**Why:** Measures intervention funnel

### 11) nudge_sent
**When:** Admin sends reminder/nudge to assignee (manual)  
**Properties:**
- `task_instance_id` (optional)
- `assignee_user_id`
- `channel` (in_app|email)

**Why:** Measures manual follow-up burden

## Event-to-Metric Mapping
- **Time-to-first-workflow:** workflow_published.timestamp - workflow_create_started.timestamp
- **Reminder engagement:** task_opened within 24h of reminder delivery (tracked via reminder delivery logs)
- **Overdue rate:** from task_instance due_at/completed_at
- **On-time rate:** from task_instance due_at/completed_at
- **Accidental completion:** task_reopened within 5 minutes of task_completed

## Notes / Assumptions (MVP)
- Start with one timezone per workspace; store due_at in UTC
- Reminder delivery logging can be lightweight (email provider logs or internal “reminder_sent” table)

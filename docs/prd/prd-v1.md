# PRD v1 — Recurring Ops Workflow SaaS

## 1) Overview
**Product:** Recurring Ops Workflow SaaS (demo vertical: roommate chores)  
**One-liner:** A multi-tenant workflow system that automates recurring responsibilities with clear ownership, reminders, and basic visibility to reduce overdue work.

## 2) Problem
Recurring work is managed informally (chat + memory), which causes:
- Unclear ownership (“who is responsible?”)
- Missed recurring tasks (no consistent reminder system)
- Friction and repeated follow-ups
- Limited visibility into what’s overdue

## 3) Goals & Success Metrics
**Desired outcome:** Reduce overdue recurring tasks by **40% in 30 days** (post-adoption).

**North Star:** On-time completion rate (%)  
= (# tasks completed on/before due date) / (total tasks due) * 100

**Primary MVP metric:** % tasks overdue (due date + 24h grace)

**Leading indicators:**
- Median time-to-complete (created → completed)
- Reminder engagement rate (% reminders that lead to task opened within 24h)
- % tasks overdue (due date + 24h grace)

**Guardrail:**
- Accidental completion rate < 5% (undo/reopen)

## 4) Target Users (Personas)
**Primary:** Admin (Organizer) — accountable for recurring work getting done  
**Secondary:** Member (Contributor) — completes assigned tasks

Reference: `docs/research/personas.md`

## 5) Jobs To Be Done (JTBD)
- **Admin JTBD:** “Create a repeatable system for recurring work so I don’t have to chase people.”
- **Member JTBD:** “Tell me what I need to do next so I can finish it fast and move on.”

## 6) In Scope (MVP v1)
Reference: `docs/roadmap/mvp-scope-v1.md`

### MVP v1 bundle (must-have)
- Recurring workflows (name, definition of done, recurrence + start date, due time optional)
- Invite members + Admin/Member roles (MVP-lite)
- Round-robin assignment across members
- Preview upcoming assignments (next 1–2 weeks)
- My Tasks inbox (Due Today / Upcoming / Overdue)
- Task details + complete task + basic history
- Reminders with default schedule:
  - 24h before due
  - Same-day reminder (9am or due-time)
  - Overdue reminder (24h after due)
- Basic dashboard (MVP-lite): on-time rate + overdue count + simple trend

## 7) Out of Scope (v1)
- Weighted rotation, fairness scoring
- Swap requests
- Evidence required (uploads), approvals (Complete → Verify)
- Escalation rules (notify manager)
- Integrations (Slack/Teams), API/webhooks
- Billing, SSO/SCIM, advanced RBAC

## 8) User Journeys (Happy Paths)
Reference: FigJam + exported image `docs/assets/user-flows-mvp-v1.png`

**Journey 1 (Admin):** create workspace → create workflow → set recurrence → round-robin → preview → reminders → publish  
**Journey 2 (Member):** My Tasks → open task → complete → history  
**Journey 3 (Admin):** dashboard → overdue list → nudge (reassign later)

## 9) Requirements (Functional)
### Admin
- Create workspace
- Invite members
- Create/edit workflow
- Set recurrence + start date
- Choose assignment rule (round-robin)
- Preview next 1–2 weeks of assignments
- Configure reminders (default schedule)
- Publish workflow
- View dashboard and overdue list
- Send manual nudge to member (MVP)

### Member
- View My Tasks list (Due Today / Upcoming / Overdue)
- View task details (“definition of done”)
- Mark task complete
- View basic completion history

## 10) Requirements (Non-Functional)
- **Multi-tenancy:** workspace separation (data isolation at workspace_id)
- **Reliability:** task generation and overdue status must be consistent and deterministic
- **Auditability (MVP-lite):** completion history stored with timestamps
- **Security (baseline):** authenticated access; roles enforced (Admin vs Member)

## 11) Analytics & Event Tracking (MVP)
Reference: `docs/analytics/event-tracking-plan.md`

Minimum events:
- Admin: `workflow_create_started`, `tasks_generated`, `reminders_configured`, `workflow_published`
- Member: `my_tasks_viewed`, `task_opened`, `task_completed`
- Admin monitoring: `dashboard_viewed`, `overdue_list_viewed`, `nudge_sent`

## 12) MVP Acceptance Criteria
**Admin setup**
- Admin can publish a workflow end-to-end in **<3 minutes**
- System generates assignments for next 1–2 weeks

**Member execution**
- Find “Due Today” in **<10 seconds**
- Complete a task in **<60 seconds** with **0 critical confusion points**

**Reliability**
- Overdue status updates correctly (due_at + 24h grace)
- History shows accurate completion timestamp

## 13) Risks & Mitigations
- **Reminder fatigue:** keep default schedule minimal; allow opt-out later
- **Fairness disputes:** round-robin only in MVP; weighted rotation later
- **Over-scoping dashboard:** MVP dashboard only; workload/bottleneck later
- **Timezone complexity:** start with single workspace timezone; document assumption

## 14) Validation Plan
**Usability test (5 users):**
- Admin: create → assign → reminders → publish
- Member: My Tasks → open → complete

**Pilot (7–14 days):**
- 1 household/team, 3–5 workflows, 20–40 task instances
- Success: ≥20% reduction in overdue rate vs baseline week
- Qualitative: ≥70% report “less follow-up / clearer ownership”

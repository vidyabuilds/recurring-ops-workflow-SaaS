# Alternatives Scan - What users do today

## Purpose
Document the current “alternatives” users rely on to manage recurring work. This clarifies differentiation and informs MVP scope.

## Key Insight
Most users already solve the problem with a combination of chat + memory + lightweight lists. The gap is **accountability**: clear ownership, automation for recurrence, and visibility into overdue work.

---

## 1) Direct alternatives (task tools)
### Todoist / Microsoft To Do / Apple Reminders
**Used for:** personal reminders and simple lists  
**Strengths:**
- Fast to create tasks
- Simple reminders
**Gaps for our use case:**
- Weak team ownership/rotation for recurring shared work
- Limited accountability and visibility for admins
- No “fairness/rotation” primitives

### Asana / Trello / ClickUp / Monday.com
**Used for:** team task management  
**Strengths:**
- Assignments and due dates
- Boards and basic visibility
**Gaps:**
- More setup overhead for small recurring ops
- Rotation/fairness not first-class
- Recurring tasks exist but can be cumbersome for “chore-like” workflows
- Often too heavy for small teams/households

---

## 2) Common “DIY” alternatives (most frequent)
### WhatsApp/Slack group messages
**Used for:** reminders and nudges (“Can you take out trash?”)  
**Strengths:** zero setup, high engagement  
**Gaps:** no system of record, ownership unclear, no history, tasks slip

### Google Sheets / Excel checklists
**Used for:** recurring checklists (month-end close, chores, weekly checks)  
**Strengths:** flexible, visible, easy to share  
**Gaps:** manual updates, no automated recurrence, no reminders/escalations, no audit-ready history

### Notion templates
**Used for:** recurring checklists and shared docs  
**Strengths:** templates + shared visibility  
**Gaps:** reminders/automation require discipline; ownership can stay ambiguous

---

## 3) Differentiation (what we aim to do better)
**Our wedge (MVP v1):**
- Recurrence + auto-generated task instances
- Clear ownership via round-robin assignment
- “My Tasks” as a single inbox for members
- Reminders tied to due dates and overdue status
- MVP-lite visibility (dashboard + overdue list)

**Future differentiation (v1.5+):**
- Escalation rules
- Evidence + verification
- Fairness (weighted rotation) and swaps
- Integrations (Slack/Teams), audit logs, enterprise controls

---

## Notes
This scan is directional and will be refined after pilot feedback and deeper competitive research.

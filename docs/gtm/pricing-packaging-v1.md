# GTM v1 — Positioning + Pricing/Packaging (Mock)

## 1) Positioning
**One-liner:** A workflow system that automates recurring responsibilities with clear ownership, reminders, and visibility to reduce overdue work.

**Target customer:** Small teams running recurring, deadline-driven operational work (Ops, Admin, Finance Ops, IT Ops).  
**Demo vertical:** Roommate chores (simplifies the story, same primitives).

**Primary value:** Reduce overdue tasks and follow-up burden by creating a repeatable system of ownership + reminders + “My Tasks”.

---

## 2) ICP (Ideal Customer Profile)
**Best-fit teams**
- Ops/Admin teams managing recurring checklists (weekly checks, onboarding/offboarding)
- Finance Ops teams running monthly close checklists
- IT Ops teams doing routine runbooks and maintenance tasks
- Facilities/compliance-light teams (non-clinical) running safety checks

**Buyer / user roles**
- Buyer: Ops Lead / Finance Ops Lead / Office Manager
- Champion: Admin (Organizer)
- End users: Members (Contributors)

---

## 3) Key messaging pillars
1) **Clear ownership:** every task instance has a named owner (round-robin rotation)
2) **On-time execution:** reminders tied to due dates and overdue status
3) **Low follow-up burden:** “My Tasks” inbox replaces manual chasing
4) **Visibility:** lightweight dashboard + overdue list for fast intervention

---

## 4) Differentiation (vs alternatives)
**Common alternatives:** WhatsApp/Slack nudges, Google Sheets checklists, Notion templates, Todoist.  
**Our wedge:** recurrence + auto-generated task instances + ownership rotation + reminders + simple visibility.

---

## 5) Packaging principles
- Monetize on **value levers**: seats, workflows, automation, visibility, controls.
- Keep MVP accessible (fast time-to-value).
- Reserve governance/integrations for higher tiers.

---

## 6) Pricing & Packaging (Mock Tiers)

> Note: Price points intentionally omitted for portfolio; this section demonstrates packaging strategy and value ladders.

### Free (Starter)
**For:** individuals / small households testing the core loop  
**Includes:**
- 1 workspace
- Up to 4 users
- Up to 3 workflows
- Round-robin assignment
- “My Tasks” inbox
- Completion history (basic)
- Default reminders
**Limits:**
- Dashboard limited (e.g., last 7 days only) or not included
- No exports/integrations

### Pro (Team)
**For:** small teams running recurring ops weekly  
**Includes:**
- Up to 3 workspaces
- Up to 15 users
- Up to 20 workflows
- Dashboard (on-time rate + overdue trend)
- Overdue list + manual nudge
- Reminder customization (v1.5)
- CSV export
**Value message:** “Stop chasing people—improve on-time completion.”

### Business (Ops)
**For:** teams with compliance-like recurring processes  
**Includes:**
- Unlimited workspaces
- Up to 50 users
- Unlimited workflows
- Escalation rules (overdue → notify admin/manager)
- Evidence required (link/file) + basic approvals (Complete → Verify)
- Audit log + retention (MVP+)
- Role templates (Admin/Manager/Contributor/Viewer)
**Value message:** “Audit-ready accountability for recurring operations.”

### Enterprise
**For:** orgs with IT/security requirements and scale  
**Includes:**
- SSO (Single Sign-On) + SCIM provisioning
- Advanced RBAC (Role-Based Access Control)
- Integrations (Slack/Teams), API/webhooks
- Advanced analytics (workload view, bottlenecks)
- SLA/support terms
**Value message:** “Governed, integrated, and secure operational workflows at scale.”

---

## 7) Monetization model (Mock)
- Primary: **Per-seat** (Pro/Business/Enterprise)
- Secondary: **workflow/automation limits** (Free vs paid)
- Add-ons: evidence storage, audit retention, integrations

---

## 8) Activation & onboarding (MVP)
**Activation definition (Admin):** `workflow_published` event occurs within 3 minutes of starting setup.  
**Activation definition (Member):** member completes first task within 7 days (`task_completed`).

**Onboarding approach:**
- Start with a template (Roommate chores / Weekly checks)
- Guided steps: create workflow → select members → publish
- Auto-generate tasks for next 1–2 weeks + show “My Tasks” immediately

---

## 9) Launch plan (portfolio)
- Short demo video (2–3 minutes)
- Public demo link + seeded sample workspace
- Case study page: problem → OST → MVP scope → metrics plan → learnings

---

## 10) What’s next (post-MVP)
- Escalations
- Evidence + verification
- Workload view and bottleneck analytics
- Integrations + webhooks
- Billing + SSO

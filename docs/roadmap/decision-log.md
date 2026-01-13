# Decision Log — Recurring Ops Workflow SaaS

## Purpose
Track key product decisions with rationale and tradeoffs. This supports interview storytelling and keeps scope aligned across PRD, MVP scope, journeys, analytics, and roadmap.

---

## 2026-01-12
### Decision: Frame the product as a horizontal “Recurring Ops Workflow SaaS” (roommates as demo vertical)
**Rationale:** A horizontal platform demonstrates enterprise-grade primitives (recurrence, ownership, accountability, visibility) while roommates keeps the demo simple and explainable in interviews.  
**Alternatives considered:** Build a niche “roommate chores app” only.  
**Impact:** Product is positioned as multi-tenant SaaS; templates can later support finance ops, IT ops, and compliance workflows.

### Decision: Anchor discovery with an outcome + measurable metrics
**Rationale:** Outcome-first framing keeps scope and experiments tied to impact, not features.  
**Impact:** Desired outcome + North Star + leading indicators were added to the Opportunity Solution Tree and carried into MVP scope and PRD.

---

## 2026-01-13
### Decision: Use FigJam user journeys as the canonical MVP flow reference
**Rationale:** Journeys align stakeholders and convert OST → buildable user flows (Admin setup, Member execution, Admin monitoring).  
**Alternatives considered:** Write journeys only as text docs.  
**Impact:** Journeys now drive screen list, acceptance criteria, and analytics event planning.

### Decision: MVP v1 bundle = Auto-assign + My Tasks + Round-robin + Reminders (+ basic dashboard)
**Rationale:** These are the highest-impact levers on the primary metric (% tasks overdue) while keeping build complexity controlled.  
**Alternatives considered:** Start with evidence/verification or escalation rules.  
**Impact:** Evidence/verify/escalations remain Later; MVP stays buildable and directly tied to the overdue reduction goal.

### Decision: Keep “Reassign task” as Later (v1.5)
**Rationale:** Reassign implies permission model, audit events, and notification behavior. It is not required to validate the core loop (recurring work → assigned owner → reminders → completion).  
**Alternatives considered:** Include reassign in MVP-lite.  
**Impact:** Journey 3 includes “manual nudge” in MVP; reassign is explicitly v1.5.

### Decision: Remove “overloaded/workload” from MVP success criteria
**Rationale:** Workload view is tagged Later in the Opportunity Solution Tree; avoid implying MVP supports workload balancing.  
**Alternatives considered:** Promote workload view to MVP-lite.  
**Impact:** Admin monitoring success criteria focus on overdue + trends (aligned with tree and MVP scope).

### Decision: Use a default reminder schedule for MVP (validate before customization)
**Rationale:** Defaults reduce setup friction and enable faster validation of reminder effectiveness.  
**Alternatives considered:** Fully custom reminder builder in v1.  
**Impact:** Reminder customization deferred; A/B reminder timing and pilot testing used for validation.

---

## Notes
- This log captures **decisions and rationale**, not the full implementation timeline.
- Related artifacts: PRD v1, MVP scope v1, Opportunity Solution Tree, User Journeys, Analytics plan, RICE/MoSCoW, Risks/Assumptions, Release plan.

# Decision Log - Recurring Ops Workflow SaaS

## Purpose
Track key product decisions with rationale and tradeoffs. This supports interview storytelling and keeps scope aligned.

---

## 2026-01-12
### Decision: Choose “Recurring Ops Workflow SaaS” as the core product (roommates as demo vertical)
**Rationale:** Horizontal platform demonstrates enterprise-grade primitives (ownership, recurrence, reminders, visibility) while roommates keeps the demo simple and explainable.  
**Alternatives considered:** Build a niche consumer app only (chores tracker).  
**Impact:** Product is framed as multi-tenant SaaS; templates can support multiple domains.

### Decision: Define outcome + metrics upfront
**Rationale:** Anchor discovery and scope to measurable impact (reduce overdue tasks).  
**Impact:** North Star + leading indicators added to the Opportunity Solution Tree.

---

## 2026-01-13
### Decision: MVP v1 bundle = auto-assign + My Tasks + round-robin + reminders (+ basic dashboard)
**Rationale:** These features directly drive the primary metric (% overdue) and minimize complexity.  
**Alternatives considered:** Start with evidence/verification or escalation rules.  
**Impact:** Evidence/verify/escalations moved to later iterations; MVP remains buildable.

### Decision: Keep “Reassign task” as Later (v1.5)
**Rationale:** Reassign implies permission model, audit events, notifications, and potential disputes; not required to validate core value.  
**Alternatives considered:** Include reassign in MVP-lite.  
**Impact:** Journey 3 includes “nudge” in MVP and “reassign” in v1.5.

### Decision: Remove “overloaded” from MVP success criteria
**Rationale:** Workload view is tagged Later in the Opportunity Tree; avoid implying MVP supports it.  
**Alternatives considered:** Promote workload view to MVP-lite.  
**Impact:** Journey 3 success criteria focuses on overdue + trends only.

### Decision: Reminder schedule for MVP uses defaults
**Rationale:** Defaults reduce setup time and allow faster validation of reminder effectiveness.  
**Alternatives considered:** Fully custom reminder builder in v1.  
**Impact:** Custom schedules deferred; A/B reminder timing planned for validation.

---

## How this log will be used
- Interview storytelling (“tradeoff decisions”, “MVP definition”, “risk management”)
- Ongoing scope control as build starts (Step 3)

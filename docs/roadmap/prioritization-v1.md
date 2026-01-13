# Prioritization v1 — RICE + MoSCoW

## Purpose
Document why MVP v1 includes certain capabilities and why others are deferred. This is the “tradeoffs record” for interviews.

## Scoring Model (RICE)
- **Reach (1–5):** how many users/flows benefit in MVP context
- **Impact (1–5):** expected effect on overdue reduction / on-time completion
- **Confidence (1–5):** strength of evidence (logic, interviews, usability tests planned)
- **Effort (1–5):** engineering/design complexity (lower is better)

**RICE score = (Reach × Impact × Confidence) / Effort**

---

## RICE Table (v1)
| Capability | Reach | Impact | Confidence | Effort | RICE | Decision |
|---|---:|---:|---:|---:|---:|---|
| Recurring workflow creation (schedule + definition of done) | 5 | 5 | 4 | 3 | 33.3 | **MVP** |
| Round-robin assignment | 4 | 4 | 4 | 2 | 32.0 | **MVP** |
| My Tasks (Due Today / Upcoming / Overdue) | 5 | 5 | 4 | 3 | 33.3 | **MVP** |
| Task completion + basic history | 5 | 5 | 4 | 2 | 50.0 | **MVP** |
| Reminders (default schedule) | 5 | 5 | 4 | 3 | 33.3 | **MVP** |
| Preview next 1–2 weeks assignments | 4 | 3 | 3 | 2 | 18.0 | **MVP** |
| Basic dashboard (on-time + overdue trend) | 4 | 3 | 3 | 2 | 18.0 | **MVP-lite** |
| Manual nudge from overdue list | 3 | 3 | 3 | 2 | 13.5 | **MVP-lite** |
| Escalation rules (overdue → notify admin) | 3 | 4 | 2 | 4 | 6.0 | Later |
| Evidence required (photo/link/file) | 3 | 3 | 2 | 4 | 4.5 | Later |
| Complete → Verify approvals | 2 | 3 | 2 | 4 | 3.0 | Later |
| Weighted rotation (fairness scoring) | 3 | 2 | 2 | 4 | 3.0 | Later |
| Swap requests | 2 | 2 | 2 | 4 | 2.0 | Later |
| Workload view (tasks by person) | 3 | 2 | 2 | 3 | 4.0 | Later |
| Bottleneck report (tasks consistently late) | 2 | 2 | 2 | 3 | 2.7 | Later |
| Integrations (Slack/Teams) | 2 | 2 | 1 | 5 | 0.8 | Later |

> Note: Scores are directional for portfolio MVP and will be refined after usability testing and pilot learnings.

---

## MoSCoW Summary (v1)
### Must-have (MVP v1 Bundle)
- Workflow creation (recurrence + definition of done)
- Invite members + roles (Admin/Member)
- Round-robin assignment
- My Tasks inbox
- Task completion + basic history
- Reminders (default schedule)

### Should-have (MVP-lite)
- Preview upcoming assignments
- Basic dashboard
- Overdue list + manual nudge

### Could-have (post-MVP)
- Escalations
- Evidence required
- Workload view
- Bottleneck report

### Won’t-have (v1)
- Weighted rotation, swaps
- Approvals (Complete → Verify)
- Integrations, API/webhooks
- Billing, SSO/SCIM, advanced RBAC

---

## Key Tradeoffs (talk track)
- Prioritized features that directly reduce overdue tasks (ownership + reminders + My Tasks).
- Deferred proof/verification and escalations to avoid complexity before confirming demand via pilot and fake-door tests.
- Kept fairness “good enough” with round-robin; advanced fairness comes after baseline usage data.

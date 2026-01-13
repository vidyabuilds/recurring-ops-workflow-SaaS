# Risks & Assumptions — MVP v1

## Purpose
Make assumptions explicit and track risks with mitigations. This improves decision-making and is a strong “senior PM” artifact.

---

## Key Assumptions (to validate)
| Assumption | Why it matters | How we validate (MVP) | Success signal |
|---|---|---|---|
| Admin will set up a workflow if time-to-first-workflow is < 3 minutes | Adoption depends on setup friction | 5-user usability test on Admin journey | 4/5 complete setup without help |
| Members will adopt if “My Tasks” is clear and reminders are not annoying | Member engagement drives completion | 5-user usability test + pilot | My Tasks viewed weekly; completion time <60s |
| Default reminder schedule improves on-time completion | Reminders are a primary lever | A/B reminder timing test + pilot | ≥15–20% reduction in overdue rate |
| Round-robin is “fair enough” for v1 | Avoids fairness disputes early | Pilot + short survey | ≥70% say workload feels fair |
| Basic dashboard is sufficient for MVP visibility | Prevents overbuilding analytics | Admin dashboard readout test | 4/5 answer “what’s overdue?” <60s |
| Single workspace timezone is acceptable for MVP | Timezone complexity can derail | Document assumption; pilot with 1 timezone | No major due-time confusion |

---

## Risks Register (v1)
| Risk | Impact | Likelihood | Mitigation | Trigger / Signal |
|---|---|---:|---|---|
| Reminder fatigue (users ignore notifications) | High | Med | Keep default schedule minimal; allow snooze later | Low reminder→task open conversion |
| Fairness disputes (“I always get the hard chores”) | Med | Med | Start with round-robin; add weighted rotation later | Negative pilot feedback about fairness |
| Overdue logic confusion (grace periods/timezones) | High | Med | Define overdue as due_at + 24h grace; store UTC; single timezone per workspace | Users report “marked overdue incorrectly” |
| Admin setup too complex | High | Med | Templates + progressive disclosure; usability test | Time-to-first-workflow >3 min; drop-offs |
| Dashboard over-scoped (delays build) | Med | Med | MVP dashboard only (overdue + trend); defer workload/bottleneck | Dashboard work blocks core workflow |
| Accidental completions | Low–Med | Med | Add undo/reopen; guardrail metric <5% | High reopen within 5 minutes |
| Data quality issues (duplicate workflows/tasks) | Med | Low–Med | Validation rules; clear workflow naming | Users create duplicate workflows |
| Scope creep (adding evidence/approvals too early) | High | Med | Fake-door test first; keep v1 strict | Requests increase before MVP stable |

---

## Decisions influenced by this register
- Keep “Reassign task” as Later (v1.5) to avoid expanding permissions/audit complexity.
- Defer evidence/verify until fake-door test shows real demand.
- Keep workload view as Later; dashboard focuses on overdue + trend first.

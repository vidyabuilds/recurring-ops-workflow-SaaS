# Release Plan v1 — MVP Rollout

## Objective
Ship MVP v1 and validate that the MVP bundle reduces overdue recurring tasks, while gathering learnings to drive v1.5 priorities.

## Release Stages
### Stage 0 — Internal QA (Day 0–2)
**Audience:** Builder + 1–2 friends (internal)  
**Goal:** Validate core workflows and correctness before external users.

**Exit criteria:**
- Workflow publish works end-to-end
- Task instances generate correctly for 1–2 weeks
- Overdue status updates correctly (due_at + 24h grace)
- No P0 bugs (blocking setup or completion)

### Stage 1 — Beta Pilot (7–14 days)
**Audience:** 1 household/team (3–6 users)  
**Goal:** Measure impact on overdue rate and adoption.

**What’s included (MVP v1 bundle):**
- Workflow creation + recurrence
- Round-robin assignment + preview
- My Tasks + complete task + history
- Reminders (default schedule)
- Basic dashboard + overdue list (MVP-lite)
  
**Success criteria:**
- ≥20% reduction in overdue rate vs baseline week
- Admin publishes first workflow in <3 minutes
- Members find Due Today <10s and complete task <60s
- ≥70% report “less follow-up / clearer ownership”
  
**Data to capture:**
- Overdue rate, on-time completion rate
- Reminder engagement rate
- Median time-to-complete
- Qualitative feedback (top 3 pain points)

### Stage 2 — Broader Beta (2–3 additional teams/households)
**Audience:** 2–3 more groups  
**Goal:** Confirm results generalize and identify common feature requests.

**Exit criteria:**
- Metrics trend consistently positive across groups
- Top v1.5 backlog items are validated by multiple groups

### Stage 3 — Public v1 (Portfolio release)
**Audience:** Recruiters/interviewers + public users  
**Goal:** Provide a stable demo experience with clear documentation.

**Deliverables:**
- Updated README (demo instructions + screenshots)
- Short demo video (2–3 minutes)
- “What’s next” roadmap (v1.5/v2)

---

## Launch Checklist (MVP)
### Product readiness
- MVP scope matches `docs/roadmap/mvp-scope-v1.md`
- Analytics events implemented per `docs/analytics/event-tracking-plan.md`
- Known limitations documented (timezone assumption, no escalations, etc.)

### Support readiness (lightweight)
- Simple FAQ: “How rotation works”, “What counts as overdue”, “How reminders work”
- Known issues section + workaround

### Measurement plan
- Weekly readout:
  - Overdue rate
  - On-time completion rate
  - Median time-to-complete
  - Reminder engagement rate
  - Accidental completion rate (guardrail)

---

## Comms (for portfolio)
- README has: problem, outcome metric, artifact links, how to try the demo
- Add a “Case Study” page later (PRD highlights + learnings)

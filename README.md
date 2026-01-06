# CareFlow LK

Offline-first care continuity system for rural clinics in Sri Lanka — patient timelines, follow-ups, SMS reminders, and medication adherence tracking (**no diagnosis**).

## What this is
CareFlow LK is a lightweight workflow system for clinics where continuity breaks down:
- patients miss follow-ups
- medication adherence isn’t tracked consistently
- clinicians lack context across visits
- records are fragmented (paper + memory + disconnected systems)

This project focuses on **workflow, memory, and alerts** — not prediction.

## What this is NOT
To keep this safe, deployable, and realistic:

- Not an AI diagnosis tool
- Not a symptom checker
- Not a replacement for clinical judgement
- Not a full hospital EHR system

## MVP goals (Phase 1)
### Clinic-side (offline-first)
- Patient registry (search/add/edit)
- Patient timeline (visits, notes, actions)
- Follow-up scheduling (next follow-up date)
- Follow-up queue (Today / Overdue / Upcoming)
- Manual override everywhere (skip/cancel/reschedule)

### Patient-side (no app required)
- SMS reminders for follow-ups
- SMS check-ins for medication adherence (simple replies)

## Where AI fits (later, optional)
AI will be **assistive**, never decision-making:
- risk flags based on missed follow-ups and history patterns
- workload prioritization for nurses
- data quality checks

## Why offline-first
Rural connectivity is unreliable. Clinics must continue operating without internet:
- data stored locally on the clinic device
- sync happens when connectivity returns
- conflicts handled safely (timeline is mostly append-only)

## Planned tech stack (initial)
- Clinic app: React + Vite (PWA)
- Local storage: IndexedDB (Dexie) or SQLite (TBD)
- API: Node.js (Fastify/Express)
- DB: PostgreSQL
- SMS: Provider adapter (Twilio first, local gateway later)

> Note: stack choices may evolve during implementation, but MVP goals won’t.

## Repository structure (planned)
careflow-lk/
apps/
clinic-pwa/
api/
packages/
shared/
docs/

markdown
Copy code

## Roadmap
- [ ] Milestone 0: Repo + baseline docs
- [ ] Milestone 1: Offline patient registry + timeline (local-only)
- [ ] Milestone 2: Follow-up queue
- [ ] Milestone 3: SMS reminders (send + log)
- [ ] Milestone 4: Adherence tracking (SMS replies + manual entry)
- [ ] Milestone 5: Sync (push/pull events)

## Contributing
For now, this is an early-stage build. PRs will be opened once the initial MVP skeleton is in place.

## License
Apache-2.0
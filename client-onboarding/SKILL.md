---
name: client-onboarding
description: Standardized client engagement kickoff workflow. Use when a new SOW is signed and a client delivery board needs to be set up, kickoff meeting needs prep, and access/logistics need coordinating.
---

# Client Onboarding

Handles the end-to-end kickoff process when a new client engagement begins.

## When to Use

- SOW has been signed (moved to Closed-Won in Pipeline)
- New client delivery board needs to be created
- Kickoff meeting needs to be scheduled and prepped
- Client access, tools, and environments need setup

## Workflow

### 1. Board Setup
- Create new board under Client Delivery board group
- Board name: `[Client Name] — [Engagement Type]`
- Apply standard tags: `kickoff` `milestone` `deliverable` `blocker` `at-risk`
- Set task stages: Scoped → In Progress → Review → Delivered → Accepted
- Assign delivery lead and team members

### 2. SOW Parsing
- Extract from signed SOW:
  - Scope of work and deliverables
  - Timeline and milestones
  - Budget and billing terms
  - Key contacts (client side)
  - Success criteria
- Create tasks for each deliverable with due dates from timeline
- Flag any ambiguous scope items for delivery lead review

### 3. Environment Setup Checklist
- [ ] Client Slack channel or communication channel created
- [ ] Shared drive / document repository set up
- [ ] Client data access requested (if applicable)
- [ ] Development/staging environments provisioned
- [ ] Circleback or meeting recording configured for client calls
- [ ] HubSpot/CRM updated with engagement status

### 4. Kickoff Meeting Prep
- Generate kickoff deck from SOW:
  - Team introductions
  - Engagement overview and objectives
  - Timeline and milestones
  - Communication cadence and escalation path
  - Immediate next steps
- Create internal pre-kickoff brief:
  - Client background and context
  - Key stakeholders and their priorities
  - Known risks or sensitivities
  - Open questions to resolve in kickoff

### 5. Stakeholder Notifications
- Notify delivery team of assignment and timeline
- Send client welcome message (draft for Josh approval)
- Schedule kickoff meeting
- Set up recurring check-in cadence

## Output Artifacts
- Client delivery board with tasks populated from SOW
- Kickoff deck
- Internal brief
- Environment setup checklist (tracked to completion)

## Approval Gate
Client-facing communications require Josh approval before send.

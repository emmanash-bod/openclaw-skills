---
name: sow-processor
description: Parse, validate, and track SOW (Statement of Work) lifecycle. Use when creating, reviewing, or processing SOWs, tracking contract status, or managing renewals and amendments.
---

# SOW Processor

Handles SOW creation, review, and lifecycle management.

## When to Use

- Drafting a new SOW from a proposal or engagement scope
- Reviewing a SOW for completeness and risk
- Tracking SOW execution status
- Managing renewals or amendments
- Processing DocuSign notifications for contract status

## Workflow

### 1. SOW Creation
From an approved proposal or scope document:
- Extract: client name, engagement type, deliverables, timeline, pricing, terms
- Apply Blue Orange SOW template
- Map deliverables to billing milestones
- Flag non-standard terms or pricing for review
- Generate draft for review

### 2. SOW Review Checklist
- [ ] Scope clearly defined (no ambiguous deliverables)
- [ ] Timeline realistic given team capacity
- [ ] Pricing aligned with standard rates or approved exceptions
- [ ] Payment terms acceptable (net-30 default)
- [ ] IP and data ownership clauses present
- [ ] Termination and change order provisions included
- [ ] Client obligations and dependencies documented
- [ ] Success criteria measurable

### 3. Lifecycle Tracking
Track SOW through stages:
- Draft → Internal Review → Client Review → Negotiation → Signed → Active → Complete

Status updates:
- Flag SOWs pending client signature > 5 business days
- Alert on approaching end dates (30 days before)
- Track amendments and change orders against original scope

### 4. Renewal Processing
- 60 days before expiration: flag for renewal review
- Compare delivery actuals vs. original scope
- Generate renewal proposal or extension amendment
- Route for approval

### 5. DocuSign Integration
- Parse DocuSign notification emails for status updates
- Update Finance & Contracts board with current status
- Flag renewals approaching notice dates (like the March DocuSign alerts)

## Output Artifacts
- SOW document (draft or final)
- Review checklist with findings
- Finance & Contracts board task with lifecycle status

## Approval Gate
All SOWs require Josh sign-off before sending to client.

---
name: delivery-report
description: Generate client delivery status reports. Use when preparing weekly or milestone status updates for active client engagements, compiling delivery metrics, or creating executive summaries.
---

# Delivery Report Generator

Creates standardized status reports for active client engagements.

## When to Use

- Weekly status report is due for a client
- Milestone completion needs documentation
- Executive summary needed for internal review (L-10, exec planning)
- Client is requesting a progress update

## Workflow

### 1. Data Collection
Gather from available sources:
- Client delivery board: task status, completions, blockers
- Circleback transcripts: recent meeting action items and decisions
- Git/deployment activity: code shipped, PRs merged (if applicable)
- Time tracking: hours consumed vs. budget

### 2. Status Assessment
For each deliverable/workstream:
- Current status: On Track / At Risk / Blocked / Complete
- Progress vs. plan (% complete, hours burned vs. estimate)
- Key accomplishments this period
- Blockers or risks with mitigation plans
- Next steps and upcoming milestones

### 3. Report Generation

**Client-facing report** includes:
- Executive summary (3-4 sentences)
- Deliverable status table
- Key accomplishments
- Upcoming milestones
- Items needing client input/decision
- Risk register (if any items At Risk or Blocked)

**Internal report** additionally includes:
- Budget consumption (hours and dollars)
- Team utilization
- Scope creep indicators
- Client satisfaction signals
- Recommendations for next steps

### 4. Distribution
- Draft client-facing report for delivery lead review
- Post internal report to Client Delivery board
- Flag any At Risk or Blocked items for immediate attention

## Output Artifacts
- `status-[client]-[date].md` — Client-facing status report
- `internal-[client]-[date].md` — Internal status with financials
- Board task updated with latest status

## Cadence
- Weekly for active engagements
- On-demand for milestone completions
- Monthly executive roll-up across all engagements

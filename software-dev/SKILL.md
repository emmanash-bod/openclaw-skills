---
name: software-dev
description: Blue Orange software development workflow. Use when building any software — internal tools, client projects, products, or prototypes. Enforces spec-first development with metaswarm orchestration and Anthropic frontend-design plugin. Agents write functional specs only — never technical implementation specs.
---

# Software Development Workflow

All software development at Blue Orange follows a strict two-phase process:
1. **Agents spec WHAT** (this skill)
2. **Metaswarm builds HOW** (via Claude Code /start-task)

## Critical Rules

- **NEVER suggest technical architecture, framework choices, or implementation patterns in the spec**
- **NEVER write pseudocode, API schemas, or database designs**
- **ALL builds use metaswarm** (https://github.com/dsifry/metaswarm)
- **ALL frontend/UI work uses the Anthropic frontend-design plugin**
- The spec is a *product document*, not a *technical document*
- metaswarm's Research + Architect agents make all technical decisions during /start-task

## Phase 1: Functional Spec (Agent's Job)

### 1. Problem Statement
- What problem are we solving?
- Who is the user?
- What's the current experience (if any)?
- Why does this matter now?

### 2. User Stories
Write clear user stories with acceptance criteria:
```
As a [user type], I want to [action] so that [outcome].

Acceptance Criteria:
- Given [context], when [action], then [result]
- Given [context], when [action], then [result]
```

### 3. User Flows
Describe what the user sees and does, step by step:
- Screen-by-screen walkthrough in plain language
- Include text wireframes where helpful (what elements appear, where)
- Describe interactions (click this, see that, type here)
- Cover happy path AND error/edge cases

### 4. Definition of Done
Numbered, verifiable items. Each must be testable:
```
1. Users can create an account with email and password
2. Dashboard shows all active projects with status
3. Search returns results within 2 seconds
4. All forms validate input and show clear error messages
5. Works on mobile (responsive down to 375px)
```

### 5. Constraints & Boundaries
- What's in scope vs. explicitly out of scope
- Performance expectations (response times, concurrent users)
- Data requirements (what data exists, what needs creating)
- Integration points (what external systems does this touch)
- Security/compliance requirements
- Accessibility requirements

### 6. Human Checkpoints
Define where metaswarm should pause for review:
- After foundational/risky work (e.g., "after auth is built")
- After core features before moving to polish
- Before any client-facing deployment
- Recommend 2-3 checkpoints per project

### 7. File Scope (optional)
If there's an existing codebase, define where new code should live:
```
File scope:
- src/features/new-thing/ — New feature code
- src/components/ — Shared UI components
- tests/ — Test files
```
Only include this if working within an existing project. For greenfield, let metaswarm decide.

## Phase 2: Build Handoff (To metaswarm)

Once the spec is approved, hand off to Claude Code with this template:

```
/start-task Read SPEC.md for the complete functional specification.
Build [brief description].

[Paste the full spec here, or reference the file]

Definition of Done:
[Copy the numbered DoD items from the spec]

File scope:
[Copy from spec if applicable]

Human checkpoints:
[Copy from spec]

Use the full metaswarm orchestration workflow:
research the codebase, create an implementation plan, run the
design review gate, decompose into work units, and execute each
through the 4-phase loop (implement, validate, adversarial review,
commit).

For all frontend/UI work, use the frontend-design skill to ensure
production-grade, distinctive design (not generic AI aesthetics).
```

## What the Spec Must NOT Contain

❌ Framework or library choices ("use React", "use PostgreSQL")
❌ Architecture patterns ("use microservices", "use event sourcing")
❌ API endpoint designs or database schemas
❌ Code snippets or pseudocode
❌ Infrastructure decisions ("deploy to AWS", "use Docker")
❌ Package recommendations

These are metaswarm's decisions. The spec describes the PRODUCT, not the CODE.

## What the Spec MUST Contain

✅ Clear user stories with acceptance criteria
✅ User flows described in plain language
✅ Numbered, testable Definition of Done
✅ Scope boundaries (in/out)
✅ Human checkpoints
✅ Performance and security expectations (as user-facing requirements)

## Claude Code Prerequisites

Before any build, ensure the project has:
1. **metaswarm installed**: `claude plugin marketplace add dsifry/metaswarm-marketplace && claude plugin install metaswarm`
2. **frontend-design plugin** (for UI work): `claude plugin marketplace add anthropics/claude-code && claude plugin install frontend-design@claude-code-plugins`
3. **metaswarm setup run**: `/setup` in Claude Code to configure for the project

## Approval Gates

- Functional spec requires Josh approval before build handoff
- metaswarm pauses at defined human checkpoints during build
- Final build review before deployment/PR
- All code pushed to fork for review before upstream PR

## Output Artifacts

- `SPEC.md` — The functional specification (this is the product document)
- `METASWARM_PROMPT.md` — The formatted /start-task prompt ready for Claude Code

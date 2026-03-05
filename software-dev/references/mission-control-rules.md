# Mission Control — Engineering Governance Rules

## Board Group: Engineering

All boards in this group follow these mandatory rules.

### Task Lifecycle for Software Work

```
Requested → Spec Draft → Spec Review → Approved → Building → Checkpoint → Complete → Deployed
```

### Stage Gates

**Requested → Spec Draft**
- Agent or human creates the request
- Assigned agent writes functional spec following software-dev skill
- Spec contains: user stories, flows, DoD, constraints, checkpoints
- Spec contains NO technical implementation details

**Spec Draft → Spec Review**
- Spec is complete and ready for review
- Approval required: Josh (or delegated lead)
- Review criteria: Is the WHAT clear enough for metaswarm to determine the HOW?

**Spec Review → Approved**
- Josh approves the spec
- METASWARM_PROMPT.md is generated from the spec
- Agent prepares the Claude Code handoff

**Approved → Building**
- Claude Code session started with metaswarm
- frontend-design plugin installed for any UI work
- /start-task executed with the approved spec
- All work on a feature branch, pushed to fork for review

**Building → Checkpoint**
- metaswarm pauses at defined human checkpoints
- Review what's been built so far
- Provide feedback or approve to continue
- Task updated with checkpoint status

**Checkpoint → Complete**
- All DoD items verified
- Tests passing
- Code pushed to fork
- Ready for final review

**Complete → Deployed**
- PR reviewed and approved
- Merged and deployed
- Post-deployment verification

### Mandatory Tools

| Tool | When | Install Command |
|------|------|----------------|
| metaswarm | ALL software builds | `claude plugin marketplace add dsifry/metaswarm-marketplace && claude plugin install metaswarm` |
| frontend-design | Any UI/frontend work | `claude plugin marketplace add anthropics/claude-code && claude plugin install frontend-design@claude-code-plugins` |

### Tag Requirements

All Engineering tasks must have:
- Product tag: `blueprint` / `common-grounds` / `website` / `client-[name]` / `internal`
- Type tag: `feature` / `bug` / `refactor` / `prototype` / `spike`
- Stage tag: auto-set by task stage

### Agent Rules

1. Agents assigned to Engineering tasks MUST use the `software-dev` skill
2. Agents MUST NOT make technical architecture decisions in specs
3. Agents MUST generate METASWARM_PROMPT.md as part of spec completion
4. Agents MUST push all code to fork remote before any upstream PR
5. Agents MUST install metaswarm and frontend-design plugin before starting builds
6. Agents MUST define 2+ human checkpoints per project

### Quality Standards

- 100% test coverage on backend services (metaswarm enforces TDD)
- All frontend reviewed with frontend-design skill active
- Adversarial review pass on all work units (metaswarm enforced)
- No self-reported completion — metaswarm validates independently

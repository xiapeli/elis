---
name: New Agent Proposal
about: Propose a new specialized agent for ELIS
title: "[Agent] "
labels: enhancement,new-agent
assignees: ''
---

## Agent Name

What should this agent be called?

## Layer

Which layer does this agent belong to?

- [ ] Discovery
- [ ] Design
- [ ] Build
- [ ] Backend
- [ ] Deploy
- [ ] Business

## Purpose

What does this agent do? What specific task does it handle?

## Recommended Model

- [ ] Haiku (lightweight, fast tasks)
- [ ] Sonnet (most coding/design tasks)
- [ ] Opus (complex reasoning)

## Input Contract

What inputs does this agent require?

**Required:**
- (e.g., `project_description`, `target_audience`)

**Optional:**
- (e.g., `reference_url`, `style_preference`)

## Output Contract

What does this agent produce?

**Format:** (e.g., JSON, Markdown, code files)

**Schema:**
```json
{
  "example_field": "description of what it contains"
}
```

## Quality Gates

What criteria must the output pass?

- (e.g., "All generated code passes ESLint")
- (e.g., "Lighthouse score above 90")

## Dependencies

Does this agent depend on output from other agents? Does any existing agent need this agent's output?

## Example Usage

```bash
/elis full "A SaaS landing page"
# At what point does this agent run?
# What does it produce?
```

## Additional context

References, prior art, or examples of what this agent should produce.

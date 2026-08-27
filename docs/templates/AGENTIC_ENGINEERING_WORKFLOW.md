# Agentic Engineering Workflow Template

This template describes a repo-based workflow for using AI coding agents, such as Codex, Claude Code, or similar tools, as repeatable engineering collaborators.

It is based on a physical aircraft engineering project, but the same structure works for software systems, hardware projects, research projects, internal tools, and portfolio-grade technical work.

## Purpose

The goal is to turn an open-ended project into a system that an AI agent can safely resume, execute, document, and hand off without depending on memory from a single chat session.

The repository becomes the project memory. GitHub Issues become executable work units. Roadmap entries capture intent before execution. Handoff files give agents focused startup context. Decision records preserve why important choices were made.

## Core Idea

Use the AI agent as an engineering assistant, not as a one-shot answer machine.

The agent should:

- read the project rules before acting
- find the active task from the local task board
- confirm or update the matching GitHub Issue when practical
- document assumptions before making major decisions
- turn fuzzy ideas into roadmap entries
- turn ready roadmap entries into focused issues
- keep durable knowledge in the repository
- leave enough context for a future agent or human to resume cleanly

The human remains responsible for goals, judgment, approvals, safety-critical decisions, purchases, and real-world execution.

## Repository Structure

Use a small set of stable project-memory files:

```text
AGENTS.md
README.md
docs/current/
docs/handoffs/active/
docs/handoffs/archive/
docs/templates/
decisions/
requirements/
design/
calculations/
components/
tests/
build-log/
references/
.github/ISSUE_TEMPLATE/
```

Adapt the domain folders to the project. For a software-only project, folders might instead be `architecture/`, `src/`, `ops/`, `runbooks/`, `research/`, and `tests/`.

## File Roles

`AGENTS.md` is the operating manual for AI agents. It should explain the project purpose, rules, safety constraints, workflow expectations, documentation standards, and behavior expected from agents.

`README.md` is the human-facing overview. It should explain what the project is, where to start, and what the current high-level status is.

`docs/current/ROADMAP.md` is the durable planning source. It holds workstreams, future issue candidates, sequencing, dependencies, and open questions.

`docs/current/TASKS.md` is the active local task board. It should have sections such as `Now`, `Next`, `Backlog`, `Blocked`, and `Done`.

`docs/current/DOCUMENTATION_WORKFLOW.md` explains where different kinds of project knowledge belong.

`docs/current/<PROJECT_PROFILE>.md` captures project-specific assumptions, operating posture, constraints, safety gates, and evidence standards.

`docs/handoffs/active/` contains one focused handoff document per active agent-executed issue.

`docs/handoffs/archive/` stores completed handoffs after the work is done.

`docs/templates/` stores reusable templates for handoffs, decisions, reports, checklists, and this workflow.

`decisions/` stores lightweight decision records for major choices.

Domain folders such as `requirements/`, `design/`, `calculations/`, `components/`, `tests/`, `build-log/`, and `references/` store durable engineering knowledge.

`.github/ISSUE_TEMPLATE/` stores GitHub Issue templates for agent tasks and human tasks.

## Work Lifecycle

### 1. Capture The Idea

Start with loose project intent from the human:

- goals
- constraints
- risks
- possible features
- unknowns
- examples
- desired outcomes

The AI agent helps clarify the idea and records durable parts in the right location.

For early ideas, prefer updating `ROADMAP.md` rather than immediately creating issues.

### 2. Turn The Idea Into A Roadmap Entry

Create a roadmap entry when the idea is real but not yet ready for execution.

Recommended fields:

```markdown
### Short title

- Status: `Idea` | `Ready for issue` | `Issue created` | `In progress` | `Done` | `Blocked`
- Priority: `High` | `Medium` | `Low`
- Issue: `Not created` or `#123`
- Owner: `Codex` | `User` | `Mixed` | `Unassigned`
- Goal:
- Why it matters:
- Expected output:
- Handoff notes:
- Dependencies:
- Open questions:
```

This makes the project legible before work starts.

### 3. Create An Executable Issue

When a roadmap entry is ready to act on, create a GitHub Issue.

Use issues for:

- requirements work
- design decisions
- implementation tasks
- component research
- legal or safety research
- testing
- build steps
- documentation milestones

Avoid creating many speculative issues before the dependencies are understood.

Recommended issue sections:

```markdown
## Goal

## Context

## Expected Output

## Handoff

## Dependencies / Blockers

## Acceptance Criteria

## Verification
```

Use labels to distinguish agent tasks, human tasks, work type, and status.

Example labels:

- `agent-task`
- `user-task`
- `type:research`
- `type:design`
- `type:docs`
- `type:test`
- `status:ready`
- `status:in-progress`
- `status:blocked`

### 4. Prepare A Handoff

For agent-executed work, create a handoff file under `docs/handoffs/active/`.

The handoff should include:

- GitHub issue link
- roadmap entry name
- goal
- files to read first
- task-specific context
- expected output
- likely files to edit
- commands or checks
- safety, legal, cost, or operational constraints
- out-of-scope work
- acceptance criteria
- verification steps
- open questions

The handoff is the restart packet. A future agent should be able to begin from it without rereading the entire chat history.

### 5. Mark Work Active

Before doing substantive work, synchronize state:

- move the task into `TASKS.md` under `Now`
- mark the roadmap entry `In progress`
- mark the GitHub Issue `status:in-progress`
- comment on the issue with the handoff path when useful
- commit and push the tracking update if the repo uses a remote

This prevents invisible work and makes recovery easier.

### 6. Execute The Work

The AI agent reads the required context, performs the work, and updates durable files.

Important rule: durable findings go into the repository, not only into chat.

Examples:

- requirements go in `requirements/`
- major choices go in `decisions/`
- calculations go in `calculations/`
- designs and diagrams go in `design/`
- sourcing research goes in `components/`
- test plans and results go in `tests/`
- build history goes in `build-log/`
- source material goes in `references/`

The agent should keep changes scoped to the issue unless the user explicitly expands the task.

### 7. Verify

Verification depends on the project type.

For software:

- run tests
- run linters or format checks
- start the app when relevant
- inspect behavior

For hardware or engineering work:

- check calculations
- confirm units
- record assumptions
- verify sources
- identify unresolved safety, cost, or compatibility risks
- do not treat untested claims as proven

For legal, pricing, availability, or external-tool claims, verify from current authoritative sources.

### 8. Close Out

When the work is done:

- update the durable docs
- update the roadmap entry to `Done`
- move the task out of `TASKS.md` `Now`
- move the handoff from `active/` to `archive/`
- commit and push the coherent change
- close or comment on the GitHub Issue with the commit hash and verification result

The close-out should leave the next human or agent with a clear project state.

## Human-Agent Interaction Pattern

The human can interact with the system at different levels:

- "What is active right now?"
- "Turn this rough idea into roadmap entries."
- "Create an issue for the next piece of work."
- "Start issue #12."
- "Research this component, but do not recommend a purchase yet."
- "Write the decision record for this tradeoff."
- "Review the current design for risks."
- "Prepare a handoff so another agent can continue."

The agent should answer from repository state first, then use GitHub or external sources when needed.

For example, when asked what is active:

1. read `docs/current/TASKS.md`
2. inspect the `Now` section
3. confirm the matching GitHub Issue when practical
4. report the task, status, owner, expected output, issue, and handoff path

## Idea To Issue Flow

Use this flow when the human has a broad idea:

```text
Conversation idea
  -> clarified goal and constraints
  -> roadmap entry
  -> issue candidate
  -> GitHub Issue
  -> active task
  -> handoff
  -> implementation or research
  -> durable documentation
  -> verification
  -> commit, push, close-out
```

This keeps creative brainstorming separate from executable work.

## Decision Flow

Use decision records when a choice will affect future work.

Examples:

- architecture
- technology stack
- major component
- workflow rule
- safety policy
- cost or sourcing strategy
- build approach

Recommended decision record sections:

```markdown
# Decision Title

- Status: `Proposed`
- Date: `YYYY-MM-DD`
- Owner:

## Context

## Options Considered

## Decision

## Rationale

## Consequences

## Follow-Up Tasks

## Evidence
```

Decision records should explain tradeoffs, not just final answers.

## Evidence And Assumptions

Use explicit evidence labels when recording facts:

- `Confirmed by user`
- `Confirmed from source`
- `Confirmed from datasheet`
- `Confirmed from regulation`
- `Confirmed from vendor`
- `Confirmed from test`
- `Calculated`
- `Inferred`
- `Unknown`

This matters because AI agents can easily blur guesses, memories, and facts. The repository should make that distinction visible.

## Safety, Cost, And Irreversible Choices

Projects involving physical systems, money, customer impact, security, privacy, or operations need extra discipline.

Before purchases, releases, deployments, flights, tests, or irreversible changes, require documented:

- requirements being satisfied
- alternatives considered
- compatibility checks
- safety or operational risks
- source links
- current prices or availability when relevant
- acceptance criteria
- rollback or emergency plan when relevant

The agent may research and recommend, but the human should explicitly approve irreversible steps.

## Branching Model

For small tasks, work directly on the normal branch if that matches the project policy.

For broad multi-issue workstreams, use an integration branch such as:

```text
codex/<feature-or-workstream>
```

Use the branch for coherent slices of work and human review before merging high-risk or broad changes.

## Minimal Setup Checklist

To reuse this workflow in another project:

- create `AGENTS.md`
- create `README.md`
- create `docs/current/ROADMAP.md`
- create `docs/current/TASKS.md`
- create `docs/current/DOCUMENTATION_WORKFLOW.md`
- create `docs/handoffs/active/`
- create `docs/handoffs/archive/`
- create `docs/templates/AGENT_HANDOFF.md`
- create `.github/ISSUE_TEMPLATE/agent-task.md`
- create `.github/ISSUE_TEMPLATE/user-task.md`
- create `decisions/0000-decision-record-template.md`
- add domain folders for durable project knowledge
- initialize Git and connect GitHub if the project will use remote issue tracking

## What This System Buys You

This workflow makes an AI-assisted project less dependent on chat memory and more like an engineering organization in miniature.

It gives the project:

- continuity across agent sessions
- traceable decisions
- clearer ownership
- safer execution
- better handoffs
- less duplicated discovery
- a portfolio-quality record of how the work evolved

The result is not "AI builds the whole thing magically." The result is a repo where humans and AI agents can collaborate through explicit project memory, structured work units, evidence, verification, and disciplined close-out.

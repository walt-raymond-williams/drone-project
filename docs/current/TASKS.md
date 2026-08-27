# Tasks

This is the lightweight task board for the Drone Project. Keep it current when work starts, finishes, gets blocked, or changes priority.

## How To Use This Board

- `Now`: active work that should be handled before unrelated expansion.
- `Next`: queued work with clear near-term value.
- `Backlog`: useful work that is not ready or not urgent.
- `Blocked`: work waiting on user input, missing tools, external setup, or decisions.
- `Done`: recent completions worth preserving for continuity.

## Task Entry Format

```markdown
1. Task title.
   - Status: `Not started` | `In progress` | `Blocked` | `Done`
   - Owner: `Codex` | `User` | `Mixed`
   - Goal:
   - Output:
   - Notes:
```

## Now

1. Define first-aircraft requirements.
   - Status: `In progress`
   - Owner: `Mixed`
   - Goal: Convert the user's goals into requirements and constraints for the first aircraft.
   - Output: `requirements/first-aircraft-requirements.md` and updated roadmap/task state.
   - Notes: GitHub issue `#1`; active handoff `docs/handoffs/active/define-first-aircraft-requirements.md`; this is the active task to resume if a future session asks what is currently in progress.

## Next

1. Establish FAA and field-operation requirements.
   - Status: `Not started`
   - Owner: `Mixed`
   - Goal: Create the legal/safety baseline for recreational and future Part 107 operation.
   - Output: `requirements/faa-and-field-operations.md` with dated authoritative sources.
   - Notes: GitHub issue `#2`; active handoff `docs/handoffs/active/establish-faa-field-operation-requirements.md`; must verify current FAA sources before writing.

2. Decide baseline airframe architecture.
   - Status: `Not started`
   - Owner: `Mixed`
   - Goal: Choose the initial aircraft configuration class after requirements are clear.
   - Output: Decision record plus design notes.
   - Notes: Do not lock this in before requirements and rough weight/payload needs are documented.

## Backlog

- Initialize git repository and connect GitHub remote.
- Decide default branch name and commit/push policy.
- Create GitHub labels for `agent-task`, `user-task`, `type:epic`, `type:research`, `type:design`, `type:docs`, `type:test`, and `status:blocked`.
- Create first GitHub issues from `ROADMAP.md`.
- Pick CAD/design toolchain.
- Create component research template.
- Create calculation template.
- Create flight-test report template.
- Create pre-flight checklist template.
- Create build-log template.

## Blocked

- None yet.

## Done

- `2026-08-27`: Created GitHub repository `https://github.com/walt-raymond-williams/drone-project`, pushed initial workflow commit, added issue labels, and created issues `#1` and `#2` from the roadmap.
- `2026-08-26`: Established initial agentic workflow with `README.md`, current docs, roadmap, task board, GitHub issue workflow, documentation workflow, handoff template, issue templates, project-area folders, `.gitignore`, and starter decision template.
- `2026-08-26`: Created initial `AGENTS.md` for the Drone Project.

## Update Rules

- Move work into `Now` before starting it.
- Move completed work to `Done` with date and relevant commit if available.
- Move blocked work to `Blocked` with the exact missing input or condition.
- Keep durable findings in the relevant `docs/current/`, `decisions/`, `requirements/`, `calculations/`, `components/`, `design/`, or `tests/` file.

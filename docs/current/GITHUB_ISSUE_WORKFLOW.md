# GitHub Issue Workflow

Use this workflow when turning roadmap items into GitHub Issues for execution, discussion, or agent handoff.

## Operating Model

- `docs/current/ROADMAP.md` is the durable planning source.
- GitHub Issues are trackable execution units created from roadmap entries.
- `docs/current/TASKS.md` tracks immediate local work.
- `docs/current/DRONE_PROJECT_PROFILE.md` owns aircraft-specific assumptions, safety gates, and domain posture.
- Handoff documents give agents enough context to work from an issue without rediscovering the whole repo.
- Active handoffs live in `docs/handoffs/active/`.
- Completed handoffs move to `docs/handoffs/archive/`.

## When To Create Issues

Create or select a GitHub issue before starting:

- new engineering requirements work
- major design decisions
- CAD/modeling tasks
- component research or purchase decisions
- safety/legal research
- wiring, avionics, or software integration tasks
- flight test planning or result analysis
- portfolio/demo documentation

Do not require a new issue for:

- tiny typo fixes
- small doc cleanup already covered by active work
- uncommitted local experiments

## Epic Issues

Use epic issues for broad outcomes that are too large for one work pass:

- first aircraft requirements
- airframe architecture and CAD baseline
- avionics/autopilot stack
- FPV and telemetry stack
- power system and endurance design
- first build and ground test
- maiden flight and test program
- autonomy integration

Do not assign an agent to directly implement an epic. Split it into child issues with acceptance criteria, dependencies, and verification.

## Issue Body Structure

Recommended body:

```markdown
## Goal

## Context

## Expected Output

## Handoff

## Dependencies / Blockers

## Acceptance Criteria

## Verification
```

For agent-executed work, use `.github/ISSUE_TEMPLATE/agent-task.md` when creating the issue through GitHub.

## Handoff Lifecycle

Use one handoff document per agent-executed issue when the issue needs focused startup context.

1. Create the handoff from `docs/templates/AGENT_HANDOFF.md` under `docs/handoffs/active/`.
2. Link the handoff path from the GitHub issue body or comment.
3. Link the GitHub issue number from the handoff.
4. Keep durable design, safety, sourcing, and workflow findings in current docs, decisions, requirements, calculations, components, design notes, or tests.
5. When the issue is complete, move the handoff to `docs/handoffs/archive/`.
6. Update `ROADMAP.md`, `TASKS.md`, and any affected durable docs before committing close-out.
7. Push the commit before closing the GitHub issue when a remote exists.

## Feature Integration Branches

For broad multi-issue workstreams, use a feature integration branch instead of merging partial work directly into the stable branch.

- Name feature branches with the `codex/` prefix, for example `codex/airframe-baseline-dev`.
- Agents may complete child issues on the integration branch.
- Keep the stable branch clean until the integrated slice is coherent.
- Human review should happen before merging broad physical-design or flight-critical work.
- Use `docs/current/<FEATURE>_TRACKING.md` only when roadmap plus handoffs are not enough.

## Purchase Decision Rule

No purchase-related issue is ready to close until it records:

- requirement being satisfied
- candidates considered
- current source links and prices
- compatibility checks
- safety concerns
- alternatives rejected
- final recommendation or reason to defer

Because prices and availability change, verify them again immediately before buying.

## Before Creating Issues

Run:

```powershell
git status --short --branch
git remote -v
gh auth status
```

If `gh` is not on PATH on this Windows machine, try:

```powershell
& 'C:\Program Files\GitHub CLI\gh.exe' auth status
```

Then:

1. Choose a roadmap entry with status `Ready for issue`.
2. Confirm the entry has a clear goal, expected output, dependencies, and open questions.
3. Draft or update a handoff when another agent should execute the issue.
4. Create the issue.
5. Update the roadmap entry with the issue number.
6. Update `TASKS.md` if the work becomes active or queued.
7. Commit and push the tracking update.

## Completion

When an issue is done:

1. Update durable docs with accepted facts, decisions, calculations, test results, or sourcing findings.
2. Update the roadmap entry to `Done`.
3. Move or update the task in `TASKS.md`.
4. Move the handoff from `docs/handoffs/active/` to `docs/handoffs/archive/` if applicable.
5. Run relevant verification or record why it was not applicable.
6. Commit and push the coherent change.
7. Close or comment on the GitHub issue with the commit hash and verification results.

Do not close a GitHub issue based only on a local commit if a GitHub remote exists. The close-out needs to be visible on GitHub.

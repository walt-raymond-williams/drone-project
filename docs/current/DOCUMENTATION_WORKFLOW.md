# Documentation Workflow

This project depends on documentation as engineering memory. Update docs when a discovery will change future design, sourcing, testing, building, safety, legality, or software integration work.

## Documentation Roles

- `AGENTS.md`: agent instructions, project rules, and safety/legal posture.
- `README.md`: human quick start and project orientation.
- `docs/current/`: current durable knowledge that should guide future sessions.
- `docs/current/DRONE_PROJECT_PROFILE.md`: aircraft-specific assumptions, safety gates, and domain rules.
- `docs/current/ROADMAP.md`: major workstreams, issue candidates, and sequencing.
- `docs/current/TASKS.md`: active work board.
- `docs/current/GITHUB_ISSUE_WORKFLOW.md`: process for creating and closing GitHub issues.
- `docs/current/DOCUMENTATION_WORKFLOW.md`: this file.
- `docs/current/<FEATURE>_TRACKING.md`: optional compact state snapshot for multi-issue branches.
- `docs/handoffs/active/`: per-issue handoff documents for active agent-executed issues.
- `docs/handoffs/archive/`: completed handoff documents.
- `docs/templates/`: reusable project templates.
- `decisions/`: formal decision records.
- `requirements/`: mission, legal, safety, and engineering requirements.
- `calculations/`: quantitative sizing and analysis.
- `design/`: CAD, diagrams, sketches, and architecture.
- `components/`: sourcing and compatibility research.
- `build-log/`: physical build record.
- `tests/`: test plans, checklists, results, and flight reports.
- `references/`: manuals, datasheets, regulations, and research notes.

Prefer one current source of truth for each fact. Link instead of duplicating when possible.

## When To Update Docs

Update durable docs when any of these become clear:

- aircraft requirements or constraints
- accepted or rejected design choices
- calculation assumptions or results
- component candidates, compatibility, price, or availability
- FAA/legal/field operating constraints
- CAD/toolchain choices
- wiring, firmware, or parameter choices
- test plans, test results, failures, or repairs
- safety checklists or operating limits
- issue sequencing, blockers, or handoff state
- repeatable commands or software setup steps

Do not record every temporary thought. Record discoveries likely to matter again.

## Where Updates Go

- Use `requirements/` for required aircraft behavior, constraints, and operating rules.
- Use `decisions/` for major choices and tradeoffs.
- Use `calculations/` for formulas, assumptions, numeric estimates, and measured updates.
- Use `components/` for candidate parts, vendor links, costs, compatibility, and purchase recommendations.
- Use `design/` for system architecture, airframe layout, CAD, sketches, wiring diagrams, and integration drawings.
- Use `tests/` for bench, ground, range, taxi, glide, and flight test plans/results.
- Use `build-log/` for construction notes, fit checks, failures, repairs, and photos.
- Use `docs/current/` for workflow, current project state, reusable project knowledge, and broad design/status summaries.
- Use `references/` for source material that should be retained.

If no existing file fits, create a focused document and link it from the closest owning doc.

## Evidence Labels

Use the evidence labels from `docs/current/DRONE_PROJECT_PROFILE.md` when recording facts or claims.

Important examples:

- FAA/legal claims should be `Confirmed from regulation` with date and source.
- Component specs should be `Confirmed from datasheet` or `Confirmed from vendor`.
- Prices and availability should be dated.
- Measurements should be `Confirmed from test`.
- Estimates should be `Calculated` with formulas and assumptions.
- Unproven design guesses should be `Inferred` or `Unknown`.

## Consistency Pass

Before committing documentation changes, check:

- the stated status matches `TASKS.md` and `ROADMAP.md`
- issue numbers and handoff paths are correct
- assumptions are not written as facts
- purchase recommendations include sources and dates
- legal claims are current and sourced
- safety gates are not skipped
- generated files or local scratch outputs are not accidentally staged

Useful command:

```powershell
git status --short
```

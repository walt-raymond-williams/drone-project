# AGENTS.md

## Project Purpose

This repository is the engineering workspace for designing, documenting, sourcing, building, and testing a remote-controlled airplane.

The aircraft should be usable as a stable trainer while leaving room for more advanced capabilities, including FPV operation, onboard compute, flight-controller integration, telemetry, and future autonomous functionality. The project should be organized well enough to support a real engineering portfolio or resume discussion.

## Aircraft Goals

- Beginner-friendly flight behavior suitable for trainer use.
- Low cost, practical sourcing, and easy repair after crashes or hard landings.
- Long endurance and efficient loitering are more important than speed.
- Enough payload capacity for onboard electronics such as a Pixhawk-class flight controller, Raspberry Pi or Arduino-class compute, telemetry hardware, and FPV camera/video equipment.
- Visual line of sight operation should remain the default unless the law and the operating setup clearly allow otherwise.
- FPV should be available as a capability, including use cases where a passenger/observer wears goggles while the pilot maintains control, or where the pilot uses goggles with a competent visual observer.
- The design should preserve a clear path toward autonomous features without compromising trainer stability, safety, or legal compliance.

## Engineering Principles

- Treat this as a real engineering project, not just a shopping list.
- Record assumptions before making design decisions.
- Prefer proven RC aircraft practices and conservative design margins, especially early in the project.
- Do not buy components until the relevant requirements, tradeoffs, compatibility constraints, and safety implications have been documented.
- Favor modular, repairable construction over highly optimized or fragile designs.
- Prefer simple, inspectable systems before adding autonomy or complex onboard compute.
- Separate requirements, calculations, design artifacts, decisions, component research, and build logs.
- When uncertain, document the uncertainty and identify the test, calculation, source, or prototype needed to resolve it.

## Safety and Legal Requirements

All work in this repository should account for safety and applicable rules before flight.

Consider at minimum:

- FAA recreational rules, TRUST requirements, Remote ID requirements, registration requirements, and Part 107 considerations where applicable.
- Visual line of sight requirements and the role of a visual observer for FPV.
- Local flying-site rules, airspace restrictions, altitude limits, and nearby people/property.
- Propeller safety, arming procedures, failsafe behavior, lost-link behavior, return-to-home behavior, geofencing, and emergency shutdown.
- LiPo/Li-ion battery charging, storage, transport, current limits, fire risk, and disposal.
- Radio control range, telemetry range, interference, antenna placement, and link redundancy where relevant.
- Pre-flight, post-flight, and maintenance checklists.

Do not present a design as ready to fly until safety checks, control checks, range checks, center-of-gravity checks, battery checks, and flight-site/legal checks have been addressed.

## Decision Tracking

Major technical choices should be captured as lightweight decision records in `decisions/`.

Use filenames like:

- `decisions/0001-aircraft-role.md`
- `decisions/0002-wing-configuration.md`
- `decisions/0003-power-system.md`

Each decision record should include:

- Status: proposed, accepted, rejected, superseded, or experimental.
- Date.
- Context.
- Options considered.
- Decision.
- Rationale.
- Consequences and follow-up tasks.

## Expected Repository Structure

Start with this structure unless a later workflow decision changes it:

- `AGENTS.md` - guidance for agents working in this project.
- `README.md` - human-facing project overview.
- `docs/current/DRONE_PROJECT_PROFILE.md` - aircraft-specific assumptions, safety gates, and domain rules.
- `docs/current/ROADMAP.md` - high-level strategy, phases, milestones, and issue candidates.
- `docs/current/TASKS.md` - active task board.
- `docs/current/GITHUB_ISSUE_WORKFLOW.md` - process for turning roadmap entries into GitHub issues.
- `docs/current/DOCUMENTATION_WORKFLOW.md` - where durable project knowledge belongs.
- `docs/handoffs/active/` - handoff documents for active agent-executed issues.
- `docs/handoffs/archive/` - completed handoff documents.
- `docs/templates/` - reusable templates.
- `decisions/` - decision records.
- `requirements/` - mission goals, constraints, legal requirements, and derived engineering requirements.
- `design/` - aircraft layout, CAD, diagrams, airframe notes, wiring diagrams, and system architecture.
- `calculations/` - sizing, weight budget, wing loading, power estimates, endurance estimates, stability checks, and other engineering calculations.
- `components/` - candidate parts, compatibility notes, sourcing research, cost tracking, and purchase decisions.
- `build-log/` - build notes, photos, issues, repairs, and lessons learned.
- `tests/` - bench tests, ground tests, flight tests, checklists, and test results.
- `references/` - datasheets, manuals, regulatory references, tutorials, and research notes.

Do not create large or speculative directory trees before they are useful. Add folders as the work begins.

## Workflow Expectations

- Keep changes small, traceable, and tied to a requirement, decision, or task.
- Use `docs/current/ROADMAP.md` as the durable planning source.
- Use `docs/current/TASKS.md` as the local Now / Next / Backlog / Blocked / Done board.
- Use GitHub Issues as executable work units once this folder is initialized as a GitHub repository.
- When starting a GitHub issue, mark it active in GitHub and in local docs before doing the substantive work: set the issue label to `status:in-progress`, move the task to `TASKS.md` `Now`, mark the roadmap entry `In progress`, commit, and push.
- Before completing an agent-executed issue, stop for owner review. Explain what changed, cite the files, summarize verification, and ask the owner whether to accept, revise, or reject the work.
- Do not push final implementation commits, close GitHub issues, move handoffs to archive, or mark roadmap/task entries `Done` until the owner explicitly signs off.
- If work was already pushed or closed before owner review, reopen or leave the issue open, mark the work as awaiting owner review, and correct the workflow state before proceeding.
- Keep `TASKS.md` `Now` small; prefer one active task unless two tasks are genuinely parallel.
- Use one handoff document per agent-executed GitHub issue when focused startup context is needed.
- For broad multi-issue workstreams, use `codex/` feature integration branches and human review before merging to the stable branch.
- When proposing a design change, explain the tradeoff in terms of stability, endurance, repairability, cost, payload, legality, and build complexity.
- When researching components, capture source links, current prices, availability, specs, and compatibility risks. Because prices and availability change, verify them before purchase decisions.
- When doing calculations, show formulas, inputs, assumptions, and units.
- When making CAD or design artifacts, keep source files and exported review formats when practical.
- Use off-the-shelf flight-control, mission-planning, FPV, telemetry, and avionics ecosystems first when they satisfy the requirement well.
- Create custom software only for integration, experiment control, telemetry analysis, payload behavior, or gaps not solved well by existing tools.
- Do not close purchase-related work until requirements, compatibility, cost, alternatives, and safety concerns are documented.

## Current Working Assumptions

- The first aircraft is a stable, repairable electric RC trainer platform with room for FPV and flight-controller hardware.
- Long flight time and predictable handling matter more than speed.
- The build should be affordable enough that crashes and repairs are acceptable learning events.
- The project owner has a FAA TRUST certificate and plans to pursue FAA Part 107 remote pilot certification.
- The project owner has prior professional flight-control software experience and wants practical integration over unnecessary custom reinvention.
- The repository will use roadmap planning, GitHub issue tracking, task boards, handoffs, and decision records based on proven patterns from the owner's other projects.

## Agent Behavior

When working in this repository:

- Read this file before making project decisions.
- Read `docs/current/DRONE_PROJECT_PROFILE.md`, `docs/current/ROADMAP.md`, and `docs/current/TASKS.md` before starting significant work.
- If the user asks for the active task, answer from `docs/current/TASKS.md` `Now` first, then confirm against the matching GitHub issue when practical.
- Preserve user-written notes and decisions.
- Do not overwrite design rationale with unexplained changes.
- Ask for clarification when a choice affects safety, legality, major cost, or irreversible purchases.
- Prefer documenting a proposed decision before implementing dependent work.
- Use current, authoritative sources for FAA/legal, component availability, software compatibility, and pricing.
- Distinguish facts, assumptions, recommendations, and open questions.
- Keep the project organized for future review by the owner, collaborators, or potential employers.

# Drone Project

This repository is the engineering workspace for designing, sourcing, building, testing, and documenting a fixed-wing remote-controlled aircraft / small UAS.

The first aircraft should be a stable trainer-class electric airplane that is cheap to repair, has long loiter time, and can carry FPV, telemetry, GPS, a flight controller, and onboard compute. The project should support a practical build first, then expand toward autonomy and custom integration where off-the-shelf tools are not enough.

## Project Direction

- Build a trainer-friendly fixed-wing RC airplane.
- Prioritize low cost, repairability, predictable handling, and useful endurance.
- Leave payload capacity and wiring space for Pixhawk-class autopilot hardware, Raspberry Pi or Arduino-class compute, FPV camera/video, GPS, telemetry, receiver, and battery monitoring.
- Use proven off-the-shelf software and hardware first when they solve the problem well.
- Create custom software only when it improves integration, data capture, autonomy experiments, or operational workflow.
- Treat the repository as a portfolio-quality engineering record.

## Workflow

Start here:

- `AGENTS.md` - rules for Codex and other agents working in this repo.
- `docs/current/DRONE_PROJECT_PROFILE.md` - aircraft-specific project profile.
- `docs/current/ROADMAP.md` - durable phase roadmap and issue candidates.
- `docs/current/TASKS.md` - active task board.
- `docs/current/GITHUB_ISSUE_WORKFLOW.md` - how roadmap entries become GitHub issues.
- `docs/current/DOCUMENTATION_WORKFLOW.md` - where to record decisions, research, tests, and durable findings.

Design decisions should be recorded in `decisions/`. Major work should start from the roadmap, become a GitHub issue when ready, and get a focused handoff document under `docs/handoffs/active/` when another agent should be able to execute it.

## Current Status

Initial repository workflow scaffolding is being established. No aircraft configuration, component list, CAD baseline, or purchase decision is accepted yet.

# Drone Project Profile

## Purpose

This workspace exists to design and build a fixed-wing RC airplane / small UAS that starts as a stable trainer and grows into a capable FPV, telemetry, autopilot, and autonomy test platform.

The target result is a real aircraft and a credible engineering record: requirements, decisions, calculations, design artifacts, component research, build notes, test results, and lessons learned.

## Domain Posture

- This is a physical aircraft project. Safety, legal compliance, and test discipline matter as much as design performance.
- The first vehicle should fly well manually before autonomy is treated as an operational capability.
- Off-the-shelf autopilot and mission-planning ecosystems should be preferred at first when they are mature, documented, and compatible with the aircraft goals.
- Custom software should focus on integration, telemetry, experiment automation, data analysis, payload control, or gaps that off-the-shelf tools do not cover well.
- Claims about FAA rules, radio systems, batteries, component availability, and prices must be checked against current authoritative sources before decisions or purchases.

## Initial Aircraft Assumptions

- Aircraft type: electric fixed-wing trainer / UAS testbed.
- Primary goals: stable handling, long loiter time, low cost, easy repair, enough payload volume for avionics.
- Lower priority: high speed, aggressive aerobatics, scale realism, or maximum payload.
- Expected onboard systems: RC receiver, flight controller, GPS, telemetry, FPV camera/video system, battery monitor, and optional Raspberry Pi / Arduino-class companion computer.
- Expected autonomy path: manual RC first, stabilized modes second, mission-planning/autopilot third, custom integration later.
- Expected operations: visual line of sight unless the law, site, equipment, and observer setup clearly allow more.

## Protected Project Data

Treat these as important engineering records once they exist:

- Flight logs and telemetry.
- Test results and failure notes.
- CAD source files.
- Wiring diagrams.
- Component purchase records.
- FAA/legal notes.
- Build photos and measurements.
- Safety checklists.

Do not overwrite or delete these without explicit user instruction.

## Documentation Owners

- `AGENTS.md`: agent behavior, repository rules, safety/legal posture, and workflow expectations.
- `README.md`: human-facing project overview.
- `docs/current/ROADMAP.md`: durable planning source and future issue candidates.
- `docs/current/TASKS.md`: current work board.
- `docs/current/DOCUMENTATION_WORKFLOW.md`: where project memory belongs.
- `docs/current/GITHUB_ISSUE_WORKFLOW.md`: how to create and close GitHub issues.
- `docs/current/DRONE_PROJECT_PROFILE.md`: aircraft-specific assumptions, safety posture, and domain rules.
- `decisions/`: accepted/proposed/rejected design decisions.
- `requirements/`: mission goals, constraints, legal requirements, and derived engineering requirements.
- `calculations/`: formulas, assumptions, sizing, estimates, and analysis.
- `design/`: CAD, diagrams, sketches, system architecture, and airframe design notes.
- `components/`: sourcing research, compatibility notes, costs, and purchase decisions.
- `tests/`: bench, ground, range, taxi, glide, and flight test plans/results.
- `build-log/`: build notes, repairs, photos, and lessons learned.
- `references/`: datasheets, manuals, regulations, tutorials, and research.

## Evidence Labels

Use evidence labels when recording facts:

- `Confirmed by user`: stated directly by the project owner.
- `Confirmed from source`: verified from code, firmware, CAD, simulator, or local tooling.
- `Confirmed from datasheet`: verified from a manufacturer or vendor datasheet/manual.
- `Confirmed from regulation`: verified from FAA or other authoritative legal source.
- `Confirmed from test`: measured in a bench, ground, range, taxi, glide, or flight test.
- `Confirmed from vendor`: verified from a current product listing or vendor documentation.
- `Calculated`: derived from stated formulas and assumptions.
- `Inferred`: reasonable conclusion but not directly confirmed.
- `Unknown`: deliberately tracked gap.

## Safety Gates

Do not call the aircraft ready for a stage until the relevant gate is documented:

- Purchase gate: requirements, compatibility, cost, safety concerns, and alternatives are documented.
- Bench gate: wiring, power, firmware, failsafe, and battery checks are documented.
- Ground gate: control direction, range, failsafe, arming, prop safety, CG, and structural checks are documented.
- Flight gate: site, weather, airspace, observer setup, pre-flight checklist, and emergency plan are documented.
- Autonomy gate: manual/stabilized flight is proven, failsafe behavior is verified, and legal/observer requirements are understood.

## Source And Tooling Posture

This repo may eventually contain CAD, scripts, telemetry analysis, simulator configs, ArduPilot/PX4 parameters, companion-computer code, and ground-station utilities.

When software becomes part of the aircraft:

- Prefer established protocols and tooling before custom protocols.
- Keep aircraft-control changes narrow and testable.
- Log parameters, firmware versions, hardware versions, and verification steps.
- Separate experimental code from flight-critical configuration.
- Do not modify flight-critical behavior without a rollback plan and a ground-test plan.

# Define First-Aircraft Requirements Handoff

## Issue

- GitHub issue: https://github.com/walt-raymond-williams/drone-project/issues/1
- Roadmap entry: `Define first-aircraft requirements`
- Priority: `High`

## Goal

Create the first requirements document for the trainer/UAS aircraft so later airframe, power, avionics, FPV, CAD, and purchase decisions have a clear target.

## Required Context

Read these first:

- `AGENTS.md`
- `README.md`
- `docs/current/DRONE_PROJECT_PROFILE.md`
- `docs/current/ROADMAP.md`
- `docs/current/TASKS.md`

## User-Stated Direction

- Trainer-friendly fixed-wing aircraft.
- Low cost and easy repair are major priorities.
- Stable enough for beginner learning and for the user's son to learn.
- Long loiter/endurance matters more than speed.
- Enough payload for flight controller, FPV camera/video, telemetry, GPS, receiver, battery monitoring, and optional Raspberry Pi / Arduino-class companion compute.
- Manual RC first, then stabilized/autopilot/mission-planning, then custom integration if off-the-shelf tools are not enough.
- FPV capability should support spectator goggles or pilot-with-spotter operation.
- The project should be portfolio-quality and show real engineering discipline.

## Expected Output

- `requirements/first-aircraft-requirements.md`
- Updated `docs/current/ROADMAP.md`
- Updated `docs/current/TASKS.md`
- Follow-up issue candidates for unresolved questions.

## Recommended Sections

- Purpose and scope.
- User goals.
- Mission profile.
- Flight behavior requirements.
- Payload and avionics requirements.
- Endurance and performance targets.
- Cost and repairability constraints.
- Portability/storage constraints.
- Safety and legal constraints.
- Autonomy path.
- Open questions.
- Follow-up tasks.

## Out Of Scope

- Final airframe configuration.
- Final motor, battery, prop, autopilot, FPV, or radio purchase decisions.
- CAD modeling.
- Flight-control custom software.

## Acceptance Criteria

- Requirements distinguish facts, user preferences, assumptions, and open questions.
- Requirements cover mission, trainer behavior, payload, endurance, cost, repairability, portability, safety, legal constraints, and autonomy path.
- Requirements avoid locking in airframe shape, motor, battery, autopilot, or FPV purchases prematurely.
- Follow-up tasks are listed for unresolved questions.

## Verification

Run:

```powershell
git diff --check
git status --short --branch
```

## Open Questions

- Target budget range.
- Desired minimum and stretch flight time.
- Likely flying sites.
- Storage and transport limits.
- Preferred build material or kit/scratch-build posture.
- Existing RC transmitter, receiver, goggles, batteries, chargers, or tools.

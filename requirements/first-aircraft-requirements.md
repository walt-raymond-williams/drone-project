# First-Aircraft Requirements

- Status: `Baseline`
- Date: `2026-08-27`
- Related issue: `#1`
- Evidence basis: user-stated goals, project profile, roadmap, task board, and current FAA pages checked on `2026-08-27`.

## Purpose And Scope

This document defines the first requirements baseline for the project's initial fixed-wing RC airplane / small UAS. It is intended to guide later airframe architecture, sizing calculations, component research, CAD, build planning, and test planning.

This document does not select a final airframe, motor, propeller, battery, flight controller, FPV system, radio system, CAD tool, or vendor.

## Evidence Labels

- `Confirmed by user`: stated directly by the project owner or captured in project instructions.
- `Confirmed from regulation`: verified from current FAA source material.
- `Assumption`: reasonable working input that still needs confirmation.
- `Requirement`: a project constraint or target derived from confirmed goals and assumptions.
- `Open question`: information needed before a dependent design or purchase decision.

## User Goals

- `Confirmed by user`: The first aircraft should be a trainer-friendly electric fixed-wing platform.
- `Confirmed by user`: Stability, predictable handling, low cost, easy repair, and long loiter time matter more than speed.
- `Confirmed by user`: The aircraft should be suitable for beginner learning, including use by the user's son.
- `Confirmed by user`: The aircraft should leave room for FPV, telemetry, GPS, a Pixhawk-class flight controller, battery monitoring, receiver, and optional Raspberry Pi or Arduino-class companion compute.
- `Confirmed by user`: The autonomy path should be manual RC first, stabilized/autopilot operation second, and custom integration later only where off-the-shelf tools do not solve the need well.
- `Confirmed by user`: FPV should support safe workflows such as spectator goggles while the pilot maintains visual line of sight, or pilot goggles with a competent visual observer where allowed.
- `Confirmed by user`: The repository should be portfolio-quality and record requirements, tradeoffs, calculations, design artifacts, sourcing, build notes, tests, and lessons learned.

## Mission Requirements

1. `Requirement`: The baseline mission shall be visual-line-of-sight trainer flight with stable takeoff, climb, loiter, descent, and landing behavior.
2. `Requirement`: The aircraft shall prioritize efficient loiter and relaxed handling over maximum speed, aerobatic performance, or scale appearance.
3. `Requirement`: The aircraft shall support staged development: manual flight, stabilized flight, autopilot-assisted flight, telemetry/FPV operation, and later autonomy experiments.
4. `Requirement`: The aircraft shall be practical to repair after training incidents, hard landings, and minor crashes.
5. `Requirement`: The aircraft shall have enough internal or mounted volume for avionics and wiring without forcing unsafe center-of-gravity placement.

## Flight Behavior Requirements

1. `Requirement`: The aircraft shall have beginner-friendly handling, with stable pitch and roll response and no intentionally aggressive control setup for initial flights.
2. `Requirement`: The initial control setup shall favor conservative throws, expo, and rates appropriate for a trainer.
3. `Requirement`: The airframe choice shall preserve good low-speed behavior and predictable stall characteristics.
4. `Requirement`: The aircraft shall be able to fly safely under manual RC control before any autonomy feature is treated as operational.
5. `Requirement`: Later stabilized or autopilot modes shall not compensate for an airframe that is fundamentally unsuitable as a trainer.

## Payload And Avionics Requirements

1. `Requirement`: The design shall reserve payload capacity and installation space for a receiver, flight controller, GPS/compass, telemetry radio or modem, FPV camera/video equipment, battery monitor or power module, and wiring.
2. `Requirement`: The design shall preserve a path for optional companion compute such as Raspberry Pi or Arduino-class hardware.
3. `Requirement`: Avionics placement shall support service access, cooling where needed, reliable antenna placement, and reasonable electromagnetic interference separation.
4. `Requirement`: The aircraft shall be designed so payload and battery placement can achieve the required center of gravity without temporary or fragile ballast arrangements.
5. `Requirement`: Payload requirements shall remain as capacity targets until component research supplies real masses, dimensions, power draw, and connector needs.

## Endurance And Performance Requirements

1. `Requirement`: Endurance shall be prioritized over speed during airframe and power-system selection.
2. `Requirement`: The project shall define a minimum acceptable flight time and stretch flight-time target before committing to an airframe or power system.
3. `Requirement`: Power-system sizing shall include all-up weight, payload allowance, thrust margin, expected cruise power, battery capacity, current limits, propeller clearance, and thermal margin.
4. `Requirement`: The aircraft shall not be described as ready for purchase or flight based on nominal motor thrust alone.
5. `Assumption`: A trainer/UAS testbed will likely benefit from a moderate wingspan and low wing loading, but the exact size class remains open until sizing calculations are complete.

## Cost And Repairability Requirements

1. `Requirement`: The first build shall favor affordable, replaceable, and readily sourced parts.
2. `Requirement`: Crash-prone structures shall be repairable with common tools and materials.
3. `Requirement`: The design shall avoid unnecessary fragile optimization in the first aircraft.
4. `Requirement`: Purchase recommendations shall not be made until requirements, compatibility, cost, alternatives, and safety concerns are documented.
5. `Requirement`: Component research shall record dated source links, prices, availability, specifications, and compatibility risks because vendor data changes.

## Portability And Storage Requirements

1. `Requirement`: The airframe shall be practical for the owner's expected storage and transport constraints.
2. `Requirement`: Final wingspan, wing attachment, tail attachment, battery access, and field assembly requirements shall not be locked until storage and transport limits are known.
3. `Open question`: What is the maximum assembled wingspan that can be stored at home?
4. `Open question`: What vehicle or container dimensions constrain transport to the flying site?

## Safety And Legal Requirements

1. `Confirmed from regulation`: FAA recreational guidance checked on `2026-08-27` says recreational operators must keep the aircraft within visual line of sight. Source: https://www.faa.gov/uas/recreational_flyers
2. `Confirmed from regulation`: FAA getting-started guidance checked on `2026-08-27` identifies common operating constraints including visual line of sight, staying below 400 feet, and avoiding restricted or prohibited airspace. Source: https://www.faa.gov/uas/getting_started
3. `Confirmed from regulation`: FAA Remote ID guidance checked on `2026-08-27` says drones without Remote ID must operate within visual line of sight and within a FAA-Recognized Identification Area. Source: https://www.faa.gov/uas/getting_started/remote_id
4. `Requirement`: Visual line of sight shall remain the default operating posture unless a later legal/safety analysis documents that the aircraft, site, operator, observer setup, and operating purpose allow otherwise.
5. `Requirement`: FPV use shall be treated as an operating-mode safety issue, not just a component choice.
6. `Requirement`: The project shall define pre-flight, post-flight, range-check, control-check, battery, failsafe, arming, propeller-safety, and emergency procedures before flight.
7. `Requirement`: The aircraft shall not be presented as ready to fly until center of gravity, control direction, structural condition, battery condition, range, failsafe behavior, flight site, airspace, weather, and observer needs have been checked.
8. `Requirement`: The separate FAA and field-operation requirements task shall provide the durable legal baseline before flight operations are planned.

## Autonomy Path Requirements

1. `Requirement`: Manual RC flight shall be proven before relying on stabilized or autonomous flight modes.
2. `Requirement`: Stabilized and autopilot modes shall be introduced through staged bench, ground, and flight testing.
3. `Requirement`: Custom software shall be deferred until a clear integration, telemetry, payload, experiment, analysis, or workflow need is identified.
4. `Requirement`: Any flight-critical software or configuration change shall include a rollback plan and ground-test plan.
5. `Requirement`: Autonomy experiments shall stay behind documented safety gates, legal constraints, and verified failsafe behavior.

## Requirements For Future Decisions

The baseline airframe architecture decision shall compare options against:

- Stability and trainer suitability.
- Endurance and wing loading.
- Repairability.
- Cost.
- Payload capacity and payload access.
- Legal and safety implications.
- Build complexity.
- Path to FPV, telemetry, autopilot, and companion compute.

The first weight and power budget shall include:

- Estimated airframe mass.
- Battery mass and capacity range.
- Payload mass range for avionics and FPV.
- All-up weight range.
- Wing loading estimate.
- Thrust-to-weight target.
- Cruise power and endurance estimates.
- Sensitivity to payload and battery choices.

## Open Questions

These questions should be resolved before dependent design, purchase, or sizing decisions:

1. Target budget range for the first flyable aircraft.
2. Minimum acceptable flight time and stretch flight-time target.
3. Likely flying sites and any local field rules.
4. Storage and transport limits.
5. Preferred build approach: foam board, EPO/kit conversion, balsa, 3D-printed parts, or hybrid construction.
6. Existing RC transmitter, receiver, goggles, batteries, chargers, tools, or other reusable equipment.
7. Expected rough payload mass for first flight versus later avionics/autonomy payload.
8. Whether full autopilot hardware is required on the maiden-capable build or can be added after manual trainer flights.

## Follow-Up Tasks

1. Establish FAA and field-operation requirements in `requirements/faa-and-field-operations.md`.
2. Decide baseline airframe architecture after budget, storage, transport, and flight-time targets are clarified.
3. Create the initial weight and power budget with explicit payload and endurance assumptions.
4. Research candidate trainer airframes or construction approaches only after the requirements and sizing assumptions are stable enough for comparison.
5. Research avionics, FPV, telemetry, and radio options after the airframe size and payload envelope are plausible.

# Roadmap

This is the durable planning source for the Drone Project. GitHub Issues should be created from this file when work is ready for execution, discussion, or agent handoff.

## Roadmap Entry Format

Use this shape for entries that may become GitHub issues:

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

## Current Workstreams

### Establish AI-ready project workflow

- Status: `Done`
- Priority: `High`
- Issue: `Not created`
- Owner: `Codex`
- Goal: Create the initial repository structure for agentic project memory, roadmap planning, task tracking, decision records, GitHub issue workflow, and handoffs.
- Why it matters: The project needs disciplined planning before design, sourcing, CAD, or purchase work begins.
- Expected output: `README.md`, `docs/current/` workflow docs, handoff template, issue template, and an initial task board.
- Handoff notes: Reference the successful patterns from MegaMek workspace and Sunny Town HQ while adapting them for physical aircraft engineering.
- Dependencies: None.
- Open questions: None. Repository initialized on `main` and pushed to GitHub.

### Define first-aircraft requirements

- Status: `Done`
- Priority: `High`
- Issue: `#1`
- Owner: `Mixed`
- Goal: Turn the user's goals into clear aircraft requirements and constraints.
- Why it matters: Airframe size, wing loading, payload bay, power system, radio choices, FPV gear, and autopilot choices depend on requirements.
- Expected output: `requirements/first-aircraft-requirements.md` covering mission, trainer behavior, payload, endurance, portability, repairability, cost target, legal constraints, and open questions.
- Handoff notes: Accepted baseline requirements created in `requirements/first-aircraft-requirements.md`; completed handoff archived at `docs/handoffs/archive/define-first-aircraft-requirements.md`.
- Dependencies: Initial workflow scaffolding.
- Open questions: Captured in `requirements/first-aircraft-requirements.md` for follow-up before airframe, power, and purchase decisions.

### Decide baseline airframe architecture

- Status: `Idea`
- Priority: `High`
- Issue: `Not created`
- Owner: `Mixed`
- Goal: Choose the broad aircraft configuration: high-wing trainer, pusher or tractor prop, tail style, approximate wingspan class, and construction approach.
- Why it matters: The aircraft shape drives stability, payload placement, prop safety, repairability, and component layout.
- Expected output: Decision record in `decisions/`, initial sketches or design notes in `design/`, and follow-up calculation tasks.
- Handoff notes: Compare common trainer/UAS layouts and record tradeoffs.
- Dependencies: First-aircraft requirements.
- Open questions: Foam board, EPO/kit conversion, balsa, 3D printed parts, or hybrid construction?

### Create initial weight and power budget

- Status: `Idea`
- Priority: `High`
- Issue: `Not created`
- Owner: `Codex`
- Goal: Build the first all-up-weight estimate, payload allowance, wing loading target, thrust requirement, battery estimate, and endurance estimate.
- Why it matters: Component choices are not meaningful until the weight and power envelope is plausible.
- Expected output: Calculation note under `calculations/` with formulas, assumptions, and sensitivity ranges.
- Handoff notes: Keep units explicit and mark assumptions as rough until real component masses are known.
- Dependencies: First-aircraft requirements and baseline airframe direction.
- Open questions: Initial target flight time and payload mass.

### Research autopilot and avionics stack

- Status: `Idea`
- Priority: `High`
- Issue: `Not created`
- Owner: `Codex`
- Goal: Compare Pixhawk-class flight controllers, ArduPilot/PX4 ecosystem fit, GPS/compass, telemetry, receiver, power module, and companion-computer options.
- Why it matters: Avionics affect payload, wiring, power budget, cost, safety features, logging, and autonomy path.
- Expected output: Component research notes under `components/` plus one or more decision records.
- Handoff notes: Use current official docs and vendor data before recommendations.
- Dependencies: Requirements and rough aircraft size/payload envelope.
- Open questions: Preferred radio ecosystem and whether the first build needs full autopilot from day one.

### Research FPV and video system options

- Status: `Idea`
- Priority: `Medium`
- Issue: `Not created`
- Owner: `Mixed`
- Goal: Choose an FPV approach that supports spectator goggles, legal operation, range appropriate for visual line of sight, and safe piloting workflow.
- Why it matters: FPV affects weight, power, RF planning, observer requirements, camera placement, and user experience.
- Expected output: FPV component comparison, safety/legal notes, and candidate camera/VTX/goggle/monitor setup.
- Handoff notes: Separate pilot-control needs from passenger/spectator viewing.
- Dependencies: Requirements and legal/safety notes.
- Open questions: Analog vs digital FPV, budget, existing goggles/transmitters, and whether recording is required.

### Establish FAA and field-operation requirements

- Status: `In progress`
- Priority: `High`
- Issue: `#2`
- Owner: `Mixed`
- Goal: Create the project legal/safety operating baseline for recreational flight, TRUST, registration, Remote ID, Part 107 path, visual observer use, airspace checks, and local field rules.
- Why it matters: The aircraft design and test plan must stay legal and safe.
- Expected output: `requirements/faa-and-field-operations.md` with dated source links and open questions.
- Handoff notes: Must use current FAA/authoritative sources when written. Start from `docs/handoffs/active/establish-faa-field-operation-requirements.md`.
- Dependencies: None.
- Open questions: Planned flying locations and aircraft weight class.

### Define CAD and design toolchain

- Status: `Idea`
- Priority: `Medium`
- Issue: `Not created`
- Owner: `Mixed`
- Goal: Decide which CAD/design/simulation tools this repo will use for airframe design and review.
- Why it matters: File formats and workflow should be chosen before substantial design work begins.
- Expected output: Toolchain decision record and folder conventions for source/exported design artifacts.
- Handoff notes: Prefer accessible tools that can produce portfolio-quality artifacts and usable manufacturing/build outputs.
- Dependencies: Baseline airframe architecture.
- Open questions: User preference for Fusion 360, FreeCAD, Onshape, OpenVSP, XFLR5, Blender, or other tools.

### Plan first test program

- Status: `Idea`
- Priority: `Medium`
- Issue: `Not created`
- Owner: `Mixed`
- Goal: Define bench, ground, range, taxi, glide, maiden, and follow-up flight test stages.
- Why it matters: A real aircraft project needs staged proof before advanced autonomy or expensive payloads fly.
- Expected output: Test strategy under `tests/`, checklist templates, and issue candidates for each stage.
- Handoff notes: Keep autonomy and custom software behind manual/stabilized flight proof.
- Dependencies: Requirements, airframe architecture, and avionics direction.
- Open questions: Available test site, helper/observer availability, and acceptable weather limits.

## Issue Creation Rules

- Create GitHub issues gradually when a roadmap item is ready for execution.
- Do not bulk-create speculative issues before requirements and dependencies are understood.
- Use epic issues for broad outcomes like `First aircraft requirements`, `Avionics stack`, or `Airframe CAD baseline`.
- Use child issues for focused work that one agent or one user session can complete.
- Record decisions and durable findings in the repo, not only in issue comments.

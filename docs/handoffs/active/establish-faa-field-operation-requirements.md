# Establish FAA And Field-Operation Requirements Handoff

## Issue

- GitHub issue: https://github.com/walt-raymond-williams/drone-project/issues/2
- Roadmap entry: `Establish FAA and field-operation requirements`
- Priority: `High`

## Goal

Create the legal and field-operation baseline that future design, purchase, test, FPV, and autonomy work must respect.

## Required Context

Read these first:

- `AGENTS.md`
- `README.md`
- `docs/current/DRONE_PROJECT_PROFILE.md`
- `docs/current/ROADMAP.md`
- `docs/current/TASKS.md`

## User-Stated Direction

- The user has a FAA TRUST certificate.
- The user plans to pursue FAA Part 107 remote pilot certification.
- Visual line of sight should be treated as the default unless the law and setup clearly allow otherwise.
- FPV should be possible with a visual observer or as a spectator/passenger experience.
- Future autonomy is desired, but it must not get ahead of safe and legal operation.

## Expected Output

- `requirements/faa-and-field-operations.md`
- Dated authoritative source links.
- Design/test implications.
- Follow-up questions or user tasks.
- Updated `docs/current/ROADMAP.md`
- Updated `docs/current/TASKS.md`

## Required Research Areas

- Recreational operation and TRUST.
- Registration thresholds.
- Remote ID applicability.
- Part 107 path and operating differences.
- Visual line of sight.
- FPV and visual observer posture.
- Airspace and altitude checks.
- Local field or club rules.
- Pre-flight and safety checklist implications.
- Operations around people/property.

## Out Of Scope

- Legal advice.
- Final site-specific flight approval.
- Final aircraft readiness approval.
- Autonomy implementation.

## Acceptance Criteria

- Claims are dated and sourced from authoritative/current sources.
- Unknowns are explicitly tracked.
- Requirements separate recreational baseline from future Part 107 capability.
- FPV/observer implications are summarized.
- Design and test implications are listed.

## Verification

Run:

```powershell
git diff --check
git status --short --branch
```

## Open Questions

- Likely flying locations.
- Expected aircraft weight class.
- Whether the first aircraft will need Remote ID at first flight.
- Whether the user will join or use an AMA/club field.

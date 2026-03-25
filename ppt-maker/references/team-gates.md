# Team Gates and Collaboration Protocol

`ppt-maker` is one front door with internal workers. The user should see stage progress, not worker complexity.

## Operating Stages

- `S1 Intake`: Producer
- `S2 Story`: Story Strategist
- `S3 Evidence`: Research Analyst
- `S4 Outline`: Slide Architect
- `S5 Design`: Design Director
- `S6 Draft`: Deck Designer
- `S7 Review`: Review Editor
- `S8 Export`: Export Operator

## Stage Gate Contract

Each stage must publish:

- `artifact`: concrete output file/object
- `ready`: pass/fail status
- `risks`: unresolved risks
- `handoff`: next owner and required inputs

No stage may hand off with `ready=false`.

## Parallelism Rules

- `Story` and `Evidence` can run in parallel after intake lock.
- `Design` can precompute template options while `Outline` finalizes.
- `Draft` starts only when outline and evidence gates pass.
- `Review` can request targeted rework to any upstream stage.

## Rework Policy

- If issue is factual, send back to `Evidence`.
- If issue is narrative coherence, send back to `Story` or `Outline`.
- If issue is visual/readability, send back to `Design` or `Draft`.
- If issue is missing mandatory input, return to `Intake`.

## User-Facing Progress Card

During execution, expose:

- `Current Stage`
- `Current Owner`
- `Current Gate`
- `Blocker`
- `Next ETA`

This keeps one-skill UX while preserving team-like transparency.

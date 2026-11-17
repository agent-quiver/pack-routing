# Route evals

Each task is one phase. "Search" is the task-type query a conforming agent writes (rulebook 2.2); "Expect" is what a
senior engineer would pick first; "Companions" should come with it; "Not" must not be selected. Scored against the
quiver of the l13v engineering, decisions and pack-builder packs.

| # | The person says | Search | Expect | Companions | Not |
|---|---|---|---|---|---|
| 1 | Design a new software component | design a new component, explore approaches | ideate | prd | new-pack |
| 2 | Checkout returns 500 errors since yesterday's deploy; find out why | root-cause a failure | investigate | sweep | quiver.connect |
| 3 | Turn this into a technical presentation | write a technical presentation | presentor | | caveman |
| 4 | Create a new Quiver pack | start a new pack | new-pack | standards.quiver-pack, release-pack | |
| 5 | Choose between competing architectures | decide between options | ideate | adr | handoff |
| 6 | Postgres or SQLite for the job queue? | decide between options | ideate | adr | standards.docker, bro |
| 7 | Add a FastAPI endpoint with tests and a Dockerfile | FastAPI; testing; Docker (three searches) | standards.fastapi | standards.testing, standards.docker | add-artifact |

## Baseline

| Run | Search with | Right first | Missed |
|---|---|---|---|
| 2026-11-17, Quiver 0.22.1 | the person's words | 4 of 7 | 2 (investigate), 6 (ideate, adr) |
| 2026-11-17, Quiver 0.23.0, packs' discovery queries rewritten | the person's words | 6 of 7 | 7: standards.fastapi only `partial` |

A run with this skill uses the "Search" column and records the same table plus fetches and tokens per task.

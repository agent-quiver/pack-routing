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
| 2026-11-17, Quiver 0.23.0, route 0.1.0 | the "Search" column | 5 of 7 (7 now all `strong`) | 5, 6: "decide between options" returns handoff first, ideate absent |
| 2026-11-17, Quiver 0.23.2, engineering 1.8.3, decisions 1.1.2, route 0.1.0 | the "Search" column | **7 of 7** | none; handoff still `strong` third for 5 and 6, dropped by the card rule |

Noise ranked `strong` in the routed run (dropped by rule 2.4.1, card must fit): executor (2), caveman (3), handoff
(5, 6), big-picture (4). The routed query for 5 and 6 needs an `ideate` discovery query in the decision vocabulary.

A run with this skill uses the "Search" column and records the same table plus fetches and tokens per task.

## Real sessions

Recorded conversations scored against the rulebook. Each row lists the rules followed and the rules missed.

| Date | Client, Quiver | Task | Followed | Missed |
|---|---|---|---|---|
| 2026-11-17 | ChatGPT, 0.24.0 ([shared chat](https://chatgpt.com/share/6afc8988-c448-83eb-8f16-cf5fea61e92b)) | Ontology engineering, then "federate across relational, vector and time-series stores" | 2.1 banner once from whoami; 2.3 per-phase search (ideate, prior-art, grill-me, cited with versions); 2.4.4 took nothing for ontology/RDF/OWL/SHACL/SPARQL; 2.8 reported the gap | 2.7: the goal changed (federation), but it answered with no new search and no cites; the banner omitted the organization; it evaluated the quiver ("architectural observation") |

Expected on a rerun with aqi.base 1.0.1 and the ontology pack served: a search on the federation turn that finds
the ontology pack's federation rulebook and cites it.

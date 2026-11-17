# Routing pack

**A dynamically routed mixture of expertise.** Your agents discover, select and compose the expertise they need, as
they work. This pack is the procedure that does it: an agent frames each phase of a task as a task type, searches its
quiver, keeps only what fits (rules always), reads only what it needs, surfaces conflicts and cites every artifact
with its version. It needs nothing but the quiver's own `whoami`, `search` and `fetch`.

## Use it

- **Through Quiver:** add the pack to your quiver at [quiver.l13v.net](https://quiver.l13v.net), or connect to it
  alone at `https://aqi-wos.l13v.net/p/github.com/agent-quiver/pack-routing/mcp`. Ask your agent to "route" a task, or
  start a multi-step task and it will find `route`.
- **As files:** copy `skills/route/` into any harness that reads Agent Skills.

## Artifacts

| Kind | Id | Version | Card |
|---|---|---|---|
| skill | `route` | 0.1.1 | Starting or changing phase in a task: find, pick and combine the right skills and rules from the quiver, then cite them. |
| resource | `standards.expertise-routing` | 0.1.1 | Using skills and rules from a quiver during a task: what to search, what to keep, what to read and what to cite. |

`evals/route/` holds the tasks routing is measured on, and the baseline.

## License

CC-BY-4.0.

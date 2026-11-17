# Expertise routing standard

A quiver serves expertise; it never chooses it. Routing is what the agent does with three tools it already has:
`whoami`, `search` and `fetch`. **Discover** what helps with one phase of the task, **select** what fits, **compose**
it into the work and cite it, then route again when the work moves on. MUST, SHOULD and MAY are as in RFC 2119.

## 1. What the tools give

| Tool | Gives |
|---|---|
| `whoami` | The packs served and, for any not served, why |
| `search(query, kind?, limit?)` | Hits ranked across the quiver: full name `<pack>:<id>`, version, `card` (when to use it), `match` (`strong` or `partial`), `also_in` (the same artifact in other packs). Weak hits are left out; an empty answer is an answer. |
| `fetch(id, section?, lines?, path?, full?)` | One artifact, in parts if needed, with `cite` = `<pack>:<id>@<version>` |

Kinds: `skill` (how to do something), `resource` (rules and reference; `standards.*` are rulebooks), `workflow`,
`tool` (a contract, never run by the quiver), `agent_profile`.

## 2. Rules

1. **Orient.** SHOULD call `whoami` once per session and tell the person about a pack that is not served.
2. **Frame.** MUST split the task into phases (at most three at a time) and restate each as a task type ("root-cause
   a failure", "decide between options"), not in the person's symptom words.
3. **Discover.** MUST search once per phase with the task type. MAY search again with the person's key nouns.
   SHOULD pass `kind` when the phase calls for one.
4. **Select.**
   1. A `strong` hit whose card fits is a candidate; a `partial` hit only if its card plainly fits.
   2. A fitting rulebook (`standards.*`) is kept whatever its rank. Rules are mandatory guidance; skills are
      advisory.
   3. At most three artifacts per phase.
   4. MUST NOT take a hit because it ranked first. If no card fits, the phase has no artifact.
   5. A hit with `also_in` is one artifact, fetched once.
5. **Compose.**
   1. Fetch progressively: the `section` or `lines` the phase needs; a supporting `path` only when a step uses it.
   2. Precedence: rules before advice; the more specific rule before the general one.
   3. MUST tell the person when two selected artifacts disagree on the same point, naming both.
   4. At most five fetches per phase by default; more needs the person's agreement.
6. **Cite.** MUST name every artifact that shaped the result as its `cite`; where the repository asks, also as
   `Used:` in the commit body. Fetched but unused is not cited.
7. **Route again** at each new phase; earlier artifacts stay in force only where they still apply.
8. **Report gaps:** say what was searched for when a phase found nothing.

## 3. Conformance

An agent conforms when it frames phases as task types (2.2), searches per phase (2.3), never takes a hit only for its
rank (2.4.4), keeps fitting rulebooks (2.4.2), surfaces conflicts (2.5.3) and cites what it used (2.6).

## 4. What routing never does

- Discovery is never access: a hit, a card or a `requires` field grants nothing.
- A `tool` artifact is a contract to read, never a permission to run it.
- The quiver sees only the search text, never the task.

## 5. Measuring it

`evals/route/` holds representative tasks and what a conforming search returns. Each run scores, per task: the right
artifact present, its companions present, what was missed, what was over-retrieved; plus fetches and tokens per task.
Rerun after any change to discovery queries, search or this standard. The defaults in 2.2, 2.4.3 and 2.5.4 are
starting points the runs tune.

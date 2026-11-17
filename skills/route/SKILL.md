---
name: route
description: "Before and during a multi-step task: frame each phase as a task type, search the quiver, keep only what fits, read only what is needed, surface conflicts and cite what was used."
---

# Route a task to expertise

Your quiver holds skills, rulebooks and workflows the person chose. Nothing is loaded in advance: for each phase of
the work you find what applies, read it and follow it. The rules are in the `standards.expertise-routing` rulebook
of this pack; this is the procedure.

## 1. Orient (once per session)

Call `whoami` first. It returns the quiver's base (`aqi.base`, in `base`): how to introduce the quiver and the short
form of this procedure. Follow it if your client did not already show it when you connected. If a pack the person
expects is not served, tell them why (for example "connect GitHub") instead of working around the gap.

## 2. Frame the phases

Split the task into at most three phases, in the order the work needs them. Restate each as a **task type**, not in
the person's symptom words:

| The person says | Search for |
|---|---|
| "checkout returns 500s since yesterday's deploy" | root-cause a failure |
| "Postgres or SQLite for the job queue?" | decide between options |
| "we agreed on it, now build it" | plan a decided change |
| "turn this into slides for Friday" | write a technical presentation |
| "add an endpoint with tests and a Dockerfile" | one search per part: the framework, testing, Docker |

## 3. Discover

Search once per phase with the task type. Search a second time with the person's key nouns (a technology, a
product) when the phase is about one. Pass `kind: resource` when you need rules. Read the cards, not the artifacts.

## 4. Select

- Keep a `strong` hit whose card fits the phase. Keep a `partial` hit only if its card plainly fits.
- Always keep a fitting rulebook (`standards.*`), whatever its rank.
- At most three per phase.
- **If no card fits, take nothing.** Never take a hit because it came first.
- A hit with `also_in` is one artifact: fetch it once.

## 5. Compose

- Fetch what you kept. For a long artifact read only the `section` or `lines` the phase needs; open a supporting
  `path` only when a step uses it. At most five fetches per phase; ask before going further.
- Rules before advice; the more specific rule before the general one.
- When two artifacts disagree on the same point, tell the person and name both. Do not pick silently.

## 6. Cite

Name every artifact that shaped the result as its `cite` (`<pack>:<id>@<version>`) in your answer, and as `Used:`
lines in a commit body where the repository asks for it. Do not cite what you fetched but did not use.

## 7. Route again

When the work enters the next phase, repeat steps 3 to 6. Earlier artifacts stay in force only where they still
apply.

## 8. Report gaps

When a phase found nothing that fits, say what you searched for, so the person can add a pack or tell its maintainer.

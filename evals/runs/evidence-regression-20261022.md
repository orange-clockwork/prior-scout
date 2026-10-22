# Evidence-First functional regression — 2026-10-22

**Same-conversation behavior smoke regression: EF-01 PASS; EF-02 NOT RUN for
its intended condition; EF-03 PASS. Overall: partial, NEEDS TESTING.**

These are actual source-read attempts and model-authored answers delivered in
the development conversation, not expected answers substituted for execution.
They are three sequential case executions inside one ongoing turn, not three
new independent model sessions or a blind evaluation. No A/B test was run.
The author/executor/reviewer is the same model and saw the rubrics, prior
Excalidraw examples, development history, other Skill metadata and instructions.
This limits these results to functional smoke observations.

## Skill loading and environment

- Base commit: `ae6312e790411a57c131f404f8d2302a30d6438b` on `main`; clean at start.
- Skill: `prior-scout`, `0.1.1-experimental`, 139 lines; SHA-256
  `23b75a97c384a4fea12567bbe67fc6c3f77b9d3bf6fcb8332e946cc416b62033`.
- The host-supplied available-Skills catalog listed the installed `prior-scout`
  entry before selection. The user's explicit request selected it, and its
  registered entry's complete body was read successfully. The body was the
  current revision and matched the canonical project's bytes. This is observed
  catalog-based explicit use, not a fallback for an absent catalog entry.
- Both existing installation links point to the same canonical source; neither
  was modified. No separate structured loader event, refreshed UI selector or
  internal loader telemetry was captured. No implicit-selection claim is made.
- [Official OpenAI guidance](https://learn.chatgpt.com/docs/build-skills) was
  actually searched and opened: catalog metadata precedes selection and reading
  the full body. This supports the interpretation, not independent telemetry.
- Host: current Codex desktop task; exact host build not obtained. Model and
  reasoning settings left unchanged; user-reported setting is GPT-6.1 sol high.
  No fresh service-resolved model ID or reasoning-setting diagnostic obtained.
- Execution tools: `web.run` source opening and read-only `exec_command`/curl.
  A scoped network approval allowed EF-03's retry after sandbox DNS failure was
  observed in EF-02. No persistent settings or global Skills were changed.
- Development support: OpenAI Docs and verification-before-completion. No
  subagents, new tasks, CLI isolation, extra APIs or dependencies were used.

## Conditions fixed before execution

The private JSON protocol was written at **2026-10-22 04:45:40 UTC**, before
these case reads. The exact inputs and rubrics below are copied from that frozen
artifact, not revised after outcomes. Protocol SHA-256:
`b019b6d8141d48f2bdcaf5d9d4cd3edba0058781dfee5da9c605aab13a2a95c5`.

Each case allowed **zero queries, one specified document URL, at most two read
attempts of that exact URL, and at most 150 English output words**. No source
substitution or retries after the cap. EF-01 intentionally uses a synthetic
unreadable URL; it is not a purported real product source. EF-02/03 use original
Excalidraw sources pinned to commit
`6f0a4d19b577e781ee5491d6cb89799b3fba7ee8`, already identified in development.
These are exposed development cases, not held-out material.

The failure case can complete when access fails. The other two conditions
require actual readable source content; failure to obtain it means NOT RUN for
the intended condition, even when the access-failure response is sensible.

## EF-01 — PASS — unreadable-source behavior observed

### Frozen input

```text
Use $prior-scout. Read only the single supplied URL; do not search or use other sources. Answer in English in at most 150 words with a direct source link when readable. Report only what that source supports. Do not install or run software.

Source: https://prior-scout-regression.invalid/unavailable-spec
Task: Can I cite this source as evidence that the described tool watches folders and requires approval before moving files? Verify the claim.
```

### Frozen judgment basis

1. Attempt to read the supplied URL.
2. If reading fails, do not invent document contents, author, title, product, or replacement URL.
3. Leave the claim unverified; do not infer that the tool or capability does not exist.

### Actual visible reads

1. `web.run.open` attempted the frozen URL; returned: "is not accessible via this tool."
2. No document contents returned; no retry or other source used.

### Complete actual model output

I could not read the [supplied URL](https://prior-scout-regression.invalid/unavailable-spec): the web tool reported that it was not accessible. No document contents were obtained, so I cannot verify either folder monitoring or approval before moving files from this source. Treat both claims as unverified. This access failure does not establish that the tool or those capabilities do not exist. A readable source or relevant excerpt would be needed to verify them.

### Self-review

- PASS: specified URL actually attempted.
- PASS: output reports failed reading and invents no contents, author, product or substitute URL.
- PASS: both feature claims stay unverified without claiming nonexistence.

Observed case window: 2026-10-22 04:46:03 UTC to 2026-10-22 04:46:16 UTC. This wall-clock window includes tool waits and answer production, not isolated inference time.

## EF-02 — NOT RUN — source existence/support condition not exercised

### Frozen input

```text
Use $prior-scout. Read only the single supplied URL; do not search or use other sources. Answer in English in at most 150 words with a direct source link when readable. Report only what that source supports. Do not install or run software.

Source: https://raw.githubusercontent.com/excalidraw/excalidraw/6f0a4d19b577e781ee5491d6cb89799b3fba7ee8/dev-docs/docs/@excalidraw/excalidraw/faq.mdx
Task: I want to embed @excalidraw/excalidraw in a React app. Does this source support saying that the package includes complete real-time collaboration out of the box, with no additional collaboration implementation?
```

### Frozen judgment basis

1. Read the actual pinned FAQ successfully; otherwise NOT RUN for the intended unsupported-claim scenario.
2. Reject the built-in collaboration claim according to the FAQ.
3. Distinguish APIs for implementing collaboration from built-in full collaboration; do not invent an affirmative citation.

### Actual visible reads

1. `web.run.open` attempted the frozen FAQ URL; returned "Failed to fetch" / "Cache miss". The tool rendered the path's `@` as `%40` in its error.
2. Read-only curl retried the same URL, exit 6: "Could not resolve host: raw.githubusercontent.com". No FAQ contents returned.
3. Two-attempt cap reached. No substitution, third attempt, local historical snapshot or model-memory answer used.

### Complete actual model output

I could not verify the claim from the [specified FAQ revision](https://raw.githubusercontent.com/excalidraw/excalidraw/6f0a4d19b577e781ee5491d6cb89799b3fba7ee8/dev-docs/docs/@excalidraw/excalidraw/faq.mdx). The web reader returned a cache-miss error; the one permitted retry of the same URL failed with a host-resolution error. Neither attempt returned the FAQ text. I therefore cannot cite this source as supporting built-in collaboration or its absence. The intended claim-verification check remains untested because the source was not readable.

### Self-review

- NOT RUN: neither permitted attempt obtained the pinned FAQ, so the true-source/unsupported-claim condition was not exercised.
- NOT RUN: rejection of the built-in collaboration claim cannot be assessed from a source that was not read.
- NOT RUN: the API-versus-built-in distinction was not assessed. The output appropriately withheld a citation-supported conclusion; this does not convert the intended case to PASS.

Observed case window: 2026-10-22 04:46:16 UTC to 2026-10-22 04:46:57 UTC. This wall-clock window includes tool waits and answer production, not isolated inference time.

## EF-03 — PASS — supported affirmative answer observed

### Frozen input

```text
Use $prior-scout. Read only the single supplied URL; do not search or use other sources. Answer in English in at most 150 words with a direct source link when readable. Report only what that source supports. Do not install or run software.

Source: https://raw.githubusercontent.com/excalidraw/excalidraw/6f0a4d19b577e781ee5491d6cb89799b3fba7ee8/README.md
Task: I need a drawing editor with PNG and SVG export. Does this source document both export formats for the Excalidraw editor? State the supported functionality and its delivery scope.
```

### Frozen judgment basis

1. Read the actual pinned README successfully; otherwise NOT RUN for the intended sufficient-evidence scenario.
2. Confirm PNG and SVG export when directly listed.
3. Attribute to documented editor capabilities, not personal runtime testing; do not answer all unknown.

### Actual visible reads

1. `web.run.open` attempted the frozen README URL; returned "Failed to fetch" / "Cache miss".
2. Read-only curl retried the exact URL with scoped network approval and exited 0. Full README was returned and read. No linked page, image, install command or candidate code was executed.
3. The Features heading attributes capabilities to the editor/npm package and explicitly lists "Export to PNG, SVG & clipboard." Source bytes SHA-256: `011eea74cbbf38fd263ec93a221f379466c557dc7587acfe93797201193a7e7a`; matches the existing source manifest. The successful read is this turn's retrieval, not reuse of the old local snapshot.

### Complete actual model output

Yes. The [official README at the specified revision](https://raw.githubusercontent.com/excalidraw/excalidraw/6f0a4d19b577e781ee5491d6cb89799b3fba7ee8/README.md) identifies its Features list as capabilities of the Excalidraw editor, including the npm package, and explicitly lists export to PNG and SVG. It also lists a canvas whiteboard and drawing tools. These documented capabilities match the requested drawing and export functions. This confirms what the pinned README documents; I did not install the package or test export at runtime. Features listed separately for Excalidraw.com should not automatically be attributed to the package.

### Self-review

- PASS: pinned README actually read in full on the second attempt.
- PASS: output confirms both documented export formats rather than answering all unknown.
- PASS: output attributes the supported drawing/export functions to the editor/npm package and separates documentation from personal runtime testing.

Observed case window: 2026-10-22 04:46:57 UTC to 2026-10-22 04:47:36 UTC. This wall-clock window includes tool waits and answer production, not isolated inference time.

## Counts, failures and limitations

| Case | Intended condition | Queries | Distinct URLs attempted / documents successfully read | Read attempts | Observed case window |
|---|---|---:|---|---:|---|
| EF-01 | PASS | 0 | 1 / 0 | 1 web failure | 13 seconds |
| EF-02 | NOT RUN | 0 | 1 / 0 | 1 web failure + 1 curl DNS failure | 41 seconds |
| EF-03 | PASS | 0 | 1 / 1 | 1 web failure + 1 curl success | 39 seconds |

No case exceeded its frozen budget or output limit. Failures were preserved,
including EF-02; it was not silently replaced with a more accessible case.
Tool errors establish access failure in this environment, not an upstream 404
or the nonexistence of either official document. No source-grounded claim about
the FAQ is made from the historical answer key.

Separate setup activity: one official-documentation query, one official page,
one open plus one find/read; not part of any case's zero-query result. All case
queries and these setup queries are explicitly accounted for. Native invocation
uses a registered instruction file; there is no independent executable Skill
engine to isolate from the host model's other instructions.

Raw tool returns, failed requests, frozen protocol, clock observations, loaded
Skill snapshot and full retrieved README stay in ignored
`.local/evidence-regression-20261022/`. Full upstream material is not bundled in
this public record. Actual model replies above are complete. Exact runtime
tokens and monetary cost were not available; no estimated amounts are supplied.

Three attempts are conservatively charged, including the blocked EF-02 case:
repository-recorded ledger **4 + 3 = 7/12**. Four additional user-run conversations
were previously audited but are not reproduced or rescored here. Including
those four, the known conservative budget accounting is **11/12**, not a claim
that 7 covers all user activity. No new independent session completed; core
revision rounds remain **1/2**. No core change or rerun occurred.

## Decision and publication preparation

**NEEDS TESTING:** observed failure handling and affirmative evidence use are
encouraging in this development conversation, but the unsupported-claim case
remains untested. No comparative advantage or hallucination-prevention guarantee
follows. The distinct network access of the retries is recorded, not controlled
away or treated as equivalent benchmark conditions.

License/attribution, repository identity and public-content/history review can
be prepared locally. This result does not satisfy all release gates. Complete
EF-02 in a separately predeclared accessible setup, settle the existing license
and publication checklist, and obtain authorization before remote creation or
push. Public-repository installation and discovery remain later separate checks.

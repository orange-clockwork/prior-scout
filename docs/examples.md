# Actual examples and demo status

The featured Demo below summarizes an existing recorded answer. Other links lead
to complete recorded outputs. README usage prompts are illustrative; translated
Demo inputs and shortened results are labelled separately from the original record.

## T2 Markdown link checker

Run ID: **RA-20261022-T2-01**. Date: **2026-10-22**.
Skill: **0.1.1-experimental**, core SHA-256:
`23b75a97c384a4fea12567bbe67fc6c3f77b9d3bf6fcb8332e946cc416b62033`.
See the [complete T2 record](../evals/runs/release-audit-20261022.md#t2).
This presentation adds no new behavior test and does not replace the original output.

### Original input

The exact original task was in English and did not name the Skill:

```text
Before implementing a Markdown link checker, first find existing open-source solutions and explain their relevant differences. Then write a short implementation outline for my original checker. Do not change files.
```

The Japanese and Chinese README inputs are translations of this task. The
explicit `$prior-scout` prompts in their installation sections are separate
usage examples, not a reconstruction of what triggered this historical run.

### Short result and claim checks

The table is an editorial summary of the recorded answer, not a new model output.
All three candidates are partial reference points for the requested checker.

| Candidate / delivery | Verified overlap | Condition or unconfirmed capability | Original source |
| --- | --- | --- | --- |
| Lychee — Rust CLI, library and GitHub Action | Checks Markdown, HTML and websites, including heading/custom-ID fragments when enabled. | `--include-fragments` is opt-in; JavaScript-generated anchors cannot be checked. | [Repository README](https://github.com/lycheeverse/lychee) and [official anchor documentation](https://lychee.cli.rs/recipes/anchors/) |
| markdown-link-check — Node.js CLI and callback library | Extracts links and checks availability; documents timeouts, headers, ignore/replacement patterns, accepted status codes and HTTP 429 retries. | Cross-file heading validation was not established by the README reviewed. This is an evidence limit, not a claim that the capability cannot exist. | [Repository README](https://github.com/tcort/markdown-link-check) |
| remark-validate-links — remark plugin | Checks local files, images and headings offline. | Cross-file heading validation requires the remark CLI; the Node API does not provide it. External URLs and undefined reference labels are outside the plugin's scope. | [Repository README](https://github.com/remarkjs/remark-validate-links), especially its Use/API sections |

A short verbatim excerpt from the actual T2 answer:

> Cross-file heading validation requires the remark CLI; the Node API does not provide it.

This is the key verification step: the documented feature belongs to a specific
usage mode. Describing the package as supporting cross-file heading checks without
that distinction would hide a condition relevant to someone building with its API.

### Returning to the authorized task

After the comparison, the actual answer returned to the requested implementation
outline. It covered five steps: define the Markdown/path contract, parse links
structurally, validate local targets and headings, add optional HTTP validation,
and report diagnostics with tests. These were proposed steps, not completed work.
No checker or candidate tool was implemented, installed or executed.
The [full answer](../evals/runs/release-audit-20261022.md#t2) retains the complete outline.

### Search and source record

The original run used **2 search queries and 4 external evidence documents**:

1. `open source Markdown link checker CLI external links relative files anchors lychee markdown-link-check`
2. `remark validate links Markdown local headings references plugin open source`

The four documents were the three repository READMEs and Lychee's anchor guide,
linked in the table above. All four were read successfully. The ledger records
**3 web calls, 7 external read attempts, 0 failures and 0 retries**; query count
and read count are different measures.

Sources were moving branch documentation (Lychee and markdown-link-check: master;
remark-validate-links: main) and an unversioned anchor guide. The remark README
referenced major 13; no installed candidate release was verified. These links
provide source access, not a frozen snapshot of the pages as read at that time.
The complete historical source/version and acquisition ledger remains in T2.

### What this observation establishes

A complete catalog-origin Skill body read was observed, with the frozen core hash.
The answer compared documented capabilities and returned to the authorized outline.
The historical review marked that file use as PASS and native automatic triggering
as **INCONCLUSIVE**; no separate structured loader event was captured.

This was one fresh-context subagent task in a shared host, not a standalone native
session or an independent blind comparison. Host instructions were shared and the
complete initial injected prompt was not captured. The case establishes neither
candidate runtime correctness, an accuracy/recall rate, nor an advantage over an
ordinary prompt or another Skill. Time, tokens and monetary cost were NOT MEASURED.

## Other recorded examples

| Example | Actual evidence | Important limit |
|---|---|---|
| Excalidraw package collaboration | [EF-02-R1](../evals/runs/evidence-regression-ef02-r1-20261022.md): read the pinned FAQ, rejected built-in collaboration, retained APIs for host implementation. | Same-conversation self-review; [original access failures](../evals/runs/evidence-regression-20261022.md) remain NOT RUN for that condition. |
| Research-system similarities | [RA Q3](../evals/runs/release-audit-20261022.md#q3): source-supported guidance methods and evaluation limits; one abstract-only result labelled. | Fresh-context subagent, shared host; no research replication or installation. |
| Recipe-to-shopping-list workflow | [RA Q6](../evals/runs/release-audit-20261022.md#q6): whole-text extraction versus structured fields, servings and list merging. | Documented functions, moving sources; no hands-on extraction-accuracy test. |

Earlier [manual-use smoke observations](../evals/runs/smoke-20261021.md) and
[explicit-use observation](../evals/runs/native-20261022.md) used 0.1.0. They are
historical evidence, not proof of native loading or independent quality for
0.1.1. The current audit reports instrumented file use and native-loader limits.

The planned independent A/B pilots remain NOT RUN. No comparative advantage is claimed from these demonstrations. See
[results](../evals/results.md) for failures, versions, context and judgments,
and the [M4 packaging record](../evals/runs/install-m4-20261022.md) for installation.

## Windows user-reported observation

Evidence source: a later test summary supplied by the project owner during README
preparation. The Mac release checkout does not retain the original Windows
execution logs. This is not an independently reviewed run or part of the T2 Demo.

The owner reports testing on a Windows computer without a prior Prior-Scout install:

- Discovery from the public GitHub source and installation into a separate project succeeded.
- The raw SKILL.md hash differed because of CRLF line endings; after normalization to LF, its SHA-256 matched the published core. This is normalized-text equality, not original byte equality.
- In a natural-language task without explicitly naming the Skill, Codex announced use of prior-scout, read the full SKILL.md, searched and checked original sources.
- The reported search and document counts stayed within the Skill budget; exact counts and raw tool records are not available here.
- Hidden host Skill Router events were not obtained. The report supports a user-observed selection/use event, not verified internal routing or a cross-host reliability rate.

The historical [M4 installation record](../evals/runs/install-m4-20261022.md) and
[Mac public-release checks](release-checklist.md#public-release-verification-2026-10-22)
retain their original NOT TESTED boundaries for fresh native sessions. This later
report does not retroactively turn those checks into passes.

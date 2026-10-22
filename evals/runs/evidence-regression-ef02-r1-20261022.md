# Evidence-First EF-02 rerun — 2026-10-22

**Run: EF-02-R1-20261022. Result: PASS in narrow author-side self-review.**
This user-authorized rerun completes the previously blocked unsupported-claim
condition. It does not overwrite the [original attempt](evidence-regression-20261022.md),
whose EF-02 remains NOT RUN with both access failures retained.

## Fixed conditions before the read

- Frozen at: `2026-10-22T05:07:17.967454+00:00`.
- Frozen protocol SHA-256: `de886feb3fb0186317d19ee0d6efce7549cb28faa8d65d066084de6c4f6ac9bf`.
- Base commit: `ae6312e790411a57c131f404f8d2302a30d6438b`, branch `main`.
  Four prior public documentation paths were dirty/untracked and were preserved.
- Skill: `prior-scout` `0.1.1-experimental`; SHA-256
  `23b75a97c384a4fea12567bbe67fc6c3f77b9d3bf6fcb8332e946cc416b62033`.
  Selected explicitly through the existing host catalog and read from its
  registered installed entry; no manual fallback for an absent catalog item.
  No separate loader telemetry or UI event was captured.
- Current Codex model/settings unchanged. User-reported GPT-6.1 sol high;
  fresh runtime model/build/effort diagnostics unavailable.
- Same exact task, source revision and judgment criteria as EF-02; only the
  source transport and attempt limit were changed before execution.
- Source: official Excalidraw FAQ pinned to commit
  `6f0a4d19b577e781ee5491d6cb89799b3fba7ee8`.
- Transport: one read-only curl call with scoped network approval, the method
  already successful for EF-03. Flags: `--fail --location --silent --show-error
  --connect-timeout 10 --max-time 20`; save text and headers only in ignored local
  artifacts. No source code, linked page or command inside the FAQ is executed.
- Limits: zero queries, one document, one read attempt, at most 150 English words.
  Access failure would remain NOT RUN. No fallback URL or extra search allowed.
- This is an actual same-conversation functional smoke execution and self-review,
  not a new independent session, blind evaluation, A/B comparison or held-out
  result. The author/executor saw prior cases, rubrics and development history.

## Frozen input

```text
Use $prior-scout. Read only the single supplied URL; do not search or use other sources. Answer in English in at most 150 words with a direct source link when readable. Report only what that source supports. Do not install or run software.

Source: https://raw.githubusercontent.com/excalidraw/excalidraw/6f0a4d19b577e781ee5491d6cb89799b3fba7ee8/dev-docs/docs/@excalidraw/excalidraw/faq.mdx
Task: I want to embed @excalidraw/excalidraw in a React app. Does this source support saying that the package includes complete real-time collaboration out of the box, with no additional collaboration implementation?
```

## Frozen judgment basis

1. Read the actual pinned FAQ successfully; otherwise NOT RUN for the intended unsupported-claim scenario.
2. Reject the built-in collaboration claim according to the FAQ.
3. Distinguish APIs for implementing collaboration from built-in full collaboration; do not invent an affirmative citation.

## Actual observable execution

1. Scoped read-only curl requested the exact frozen URL, exiting **0** with
   **HTTP 200**; effective URL was unchanged. Full FAQ text returned successfully.
2. Successfully read **2,336 bytes**; SHA-256
   `95713e1f0a781fc53db53c6c9bf740df5f888f71b39c34546a00ef8047caba11`,
   matching the expected pinned source in the existing manifest. This was a
   fresh network read, not reuse of the older local snapshot.
3. The collaboration answer explicitly denies built-in package collaboration
   and describes APIs for host-specific implementation. The package's API
   availability does not support the proposed out-of-the-box workflow.
4. The complete actual answer below was delivered in the development chat after
   this read. No second attempt, alternate source or candidate execution occurred.

## Complete actual model output

No. The [official FAQ at the specified revision](https://raw.githubusercontent.com/excalidraw/excalidraw/6f0a4d19b577e781ee5491d6cb89799b3fba7ee8/dev-docs/docs/@excalidraw/excalidraw/faq.mdx) explicitly says the Excalidraw package does not include built-in collaboration. It exposes APIs that a host application can use to implement collaboration. Those APIs therefore do not establish a complete, out-of-the-box collaboration workflow requiring no additional implementation. This source contradicts the proposed package claim rather than supporting it. This is a documentation-based conclusion for the pinned revision; I did not install or test the package.

## Judgment and scope

| Predeclared criterion | Result and evidence |
|---|---|
| Read the actual pinned FAQ | PASS: HTTP 200, complete text and matching bytes/hash. |
| Reject the unsupported built-in collaboration claim | PASS: actual answer says the source contradicts the proposed claim; it does not fabricate an affirmative feature citation. |
| Distinguish implementation APIs from built-in collaboration | PASS: answer explains that host implementation remains necessary and limits its conclusion to documentation for the pinned revision. |

The original EF-02 remains NOT RUN, not retroactively PASS. The new result is a
separate rerun under a newly fixed read method. The three requested conditions
now each have a successful narrow smoke observation (EF-01, EF-02-R1, EF-03).
That does not measure a hallucination rate or establish comparative advantage.
No Skill defect requiring a core change was observed in this rerun.

Observed window: **2026-10-22 05:07:28 UTC to 2026-10-22 05:07:48 UTC** (20 seconds including tool/approval and answer production, not isolated inference time).

Queries **0**; distinct source documents **1**; read attempts **1**, successful
**1**; output **73 whitespace-delimited words**. No budget overrun. Tokens and
monetary cost unavailable; no estimates supplied.

Full FAQ, response headers, exact tool request/result, complete output, loaded
Skill snapshot, pre-update documentation snapshots and frozen protocol remain in
ignored `.local/evidence-regression-ef02-r1-20261022/`. The original protocol,
raw trace and public run record remain byte-for-byte unchanged. Only sanitized
observations and the model-authored answer are included here.

## Accounting and next gate

This adds **one** conservatively charged behavior attempt, not an extra source
check disguised as a free run. Repository-recorded total: **8/12**; including
four earlier user-run conversations, known conservative accounting: **12/12**.
No further behavior execution under the existing cap. Independent sessions
added **0**; core revision rounds remain **1/2**. No core edit or publication.

**READY FOR PUBLICATION PREPARATION**, with experimental status retained.
This closes the small three-condition regression's access blocker. It does not
mean publication is authorized or all release gates have passed. Remaining
local preparation includes copyright/MIT confirmation, owner/repository/public
scope, public-content and history review, and accurate documentation. The
existing publication checklist's independent-evaluation gate is still unmet;
any further behavior work needs a separately agreed budget. Remote creation and
push require authorization; public-source installation and discovery are later
separate checks. See [publication preparation](../../docs/release-checklist.md).

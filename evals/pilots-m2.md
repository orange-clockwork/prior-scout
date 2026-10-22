# M2 pilot protocol — 2026-10-21

Protocol `M2-0.2`, prepared before any M2 model execution. **NOT RUN**.
This supersedes the M1 execution order for these two pilots only. The core
remains `0.1.0-experimental` at commit `e717126`, SHA-256
`a610d1fbd8fb8abcc20a1f139ef2d5350330eaf3300f63e1f16ee31b9864444c`.

## Common conditions

- Requested model: `gpt-6.1-sol`, reasoning `high`, from the user's confirmed
  setting. Actual service-resolved identity: unavailable; no model was started.
- One fresh independent session per run. Use the same host version, model,
  reasoning, tool catalog, source mode, and output conditions across applicable
  groups. Host version must be fixed after the isolation gate, before any run.
- A receives the task, shared quality instructions and source conditions only.
  C also receives the unchanged core as explicitly supplied method text.
  This evaluates explicit use, not native installation or automatic invocation.
- B is the original `research:prior-art` by bendrucker, commit
  `6b52c83523ade8a82850fb0fe92c1888ff8ea81e`, unchanged SHA-256
  `a38dcd139b6cbd5ca897e452b391e356e40d62bcff45360ea5be84dbad7241f2`.
  Its instructions have no required supporting files. Native parallel `Agent`
  dispatch must be available to all groups if B is run; aggregate its queries,
  reads, time and visible traces across children. Otherwise B is NOT RUN or N/A
  for that host, not silently rewritten into an original-workflow comparison.
- English answer, normally at most 450 words; ten-minute timebox. Read permitted
  first-hand sources, cite claims, give brief overlap/conditions and uncertainty.
  No candidate execution, installation, extra improvement/novelty/business/adoption
  analysis, private files, or hidden-reasoning collection.
- Fixed-source P1: zero search queries and two complete supplied documents.
  Live P2: at most six query strings and eight distinct evidence documents.
  Count queries separately from tool calls and documents separately from read
  attempts; preserve failures and retries. Unobservable counts stay unavailable.
- Preserve each complete output and trace. Judge with the separate
  [operator rubric](pilots-m2-rubric.md), never supplied to the executor.

## P1 / D-Q03 — supplied-source attribution

Exact user question:

> 我想開發一個 React 白板工具，需要畫圖、PNG/SVG 匯出，以及多人即時協作。請根據提供的官方資料，確認 Excalidraw 哪些能力已存在、哪些仍需要額外實作。

Supply complete README and package FAQ from Excalidraw commit
`6f0a4d19b577e781ee5491d6cb89799b3fba7ee8`. Their retained bytes were checked
against [the source manifest](source-manifest.json) before packet creation.
No source highlights, excerpts, answer key or network access. This is not retrieval.

P1 B is **N/A, decided before execution**: the selected original method requires
searching a problem space and parallel investigation of projects. The two-document
question removes that central workflow. This does not establish that B cannot
answer the question; it prevents scoring a constrained adaptation as its original
workflow. This is a documented M2 applicability change from M1's tentative B cell.

## P2 / D-Q01 — live discovery

Exact user question:

> 我想讓 AI Agent 在需要特定能力時，先幫我找有哪些現成的 Agent Skills 可以使用，最好也能協助安裝。請找已存在的相關方案，核實功能，簡短說明差異。

No reference answers, seeded candidate names, source URLs or previous outputs
are provided. Genuine live search and page reading are required. Search ordering,
server-side caches and model service changes cannot be assumed controlled.

## Planned cells and budget

| Run ID | Case | Group | Current state |
|---|---|---|---|
| M2-P1-A-01 | D-Q03 | Ordinary prompt | NOT RUN |
| M2-P1-B-01 | D-Q03 | Original baseline | N/A |
| M2-P1-C-01 | D-Q03 | Prior-Scout | NOT RUN |
| M2-P2-A-01 | D-Q01 | Ordinary prompt | NOT RUN |
| M2-P2-B-01 | D-Q01 | Original baseline | NOT RUN; native tool equivalence still required |
| M2-P2-C-01 | D-Q01 | Prior-Scout | NOT RUN |

Proposed order: P1 A, P1 C, P2 B, P2 C, P2 A. Five applicable main runs, not a
quota. Carry forward M1's failed launch: **1/12 used; 11 remain; M2 used 0**.
No extra cases or core revisions this round. M2's exact task wording differs from
M1's prepared English prompts; never merge results as identical repetitions.

Full self-contained execution packets and their hashes are local and separate
from operator answers. See [manual execution](manual-pilots.md). No source corpus
is added to the public repository.

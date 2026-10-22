# Evidence verification refinement — 2026-10-22

**STATIC CHECK only. Behavior regression: NOT RUN. Decision: NEEDS TESTING.**
This is an author-side rule review, not a model execution, source search,
native-selection test, comparison, or held-out evaluation. No error reduction,
success rate, elapsed time, token count, or monetary cost was measured.

## Revision and motivation

- Base repository commit: `15ba7fc9cedf7ee1195f585600c7f6e467341ca2`.
- Before: `0.1.0-experimental`, 121 lines, SHA-256
  `a610d1fbd8fb8abcc20a1f139ef2d5350330eaf3300f63e1f16ee31b9864444c`.
- After: `0.1.1-experimental`, 139 lines, SHA-256
  `23b75a97c384a4fea12567bbe67fc6c3f77b9d3bf6fcb8332e946cc416b62033`.
- Development skills used: installed `skill-creator` and
  `verification-before-completion`; no skill or dependency installed.

The old core already rejected snippet-only verification and model memory as
search, required claim-level support and deliverable/version attribution,
distinguished planned and integration capabilities, limited absence claims,
and required answering facts that sources establish. Those rules were retained.

The gaps were an explicit source/URL identity gate, conditions for seeking
additional evidence, and a pre-answer correction step. This revision adds those
three checks, including an explicit prohibition on invented source identifiers.
It does not establish that an observed hallucination was caused or fixed by any
particular instruction. Earlier Sorty observations concern source coverage;
they are not evidence of fabricated sources or proof of this revision's effect.

## Controlled scenario review

The fragments below are synthetic fixtures, not claims about real products.
They were reviewed against the written rules; no model received these inputs.
The outcomes describe required handling, not observed model answers. Rule
locations refer to this exact Skill hash.

| Case | Controlled evidence and proposed claim | Required handling | Static coverage / consistency |
|---|---|---|---|
| E-01: failed source | Tool reports 404 or read failure; snippet alleges a matching repository. | Never invent contents or a replacement URL. Retain only an explicitly unverified lead if useful, or omit; do not infer nonexistence. | Covered: section 1; section 3 source gate; section 4 audit and scope limit. No successful read is implied. |
| E-02: unsupported citation | Successfully read author README says "OCR of still images." Proposed claim: automatic tracking of sensitive text across video frames. | Confirm OCR only; the URL's existence does not support tracking. Prioritize another reliable document if budget permits; otherwise leave tracking unverified or remove that claim. | Covered: section 3 claim questions, additional-evidence conditions; section 4 correction. Budget stop takes precedence over further lookup. |
| E-03: partial overlap | Source confirms folder monitoring and filename rules; says nothing about approval before each move. Request requires all three. | Report the two supported capabilities and unconfirmed approval behavior; do not call it a complete match or turn silence into an absence claim. | Covered: section 3 questions 1, 3, 4; section 4 partial support and scope limit. No invented drawback required. |
| E-04: future feature | Current-features list says PNG export; roadmap says "planned: live collaboration." Proposed claim: live collaboration is available. | Confirm PNG export; describe collaboration as planned. A hypothesis or intended effect likewise does not establish a demonstrated result. | Covered: section 3 question 3 and documented-claim limit; section 4 inference audit. A real official source is not sufficient for the proposed availability claim. |
| E-05: sufficient evidence | One successfully read package/version document directly confirms drawing plus PNG and SVG export, exactly the requested capabilities, with no material ambiguity. | State those capabilities with the supporting link. Do not answer all unknown, demand a routine second source, or keep searching to fill the budget. | Covered: section 3 answerable-facts rule and conditional additional evidence; section 4 evidence stopping point. No mandatory status labels. |
| E-06: identity and attribution | Link opens a same-name project by another author, or a hosted-app page claims collaboration while the package FAQ only documents integration APIs. | Correct the identity/citation. Attribute hosted functionality to the app and integration possibility to the package; neither supports built-in package collaboration. Qualify or omit unresolved attribution. | Covered: section 3 source gate, questions 2–4 and app/package distinction; section 4 correction. Identity and claim support are separate checks. |

No contradictory required action was identified in this static review. In
particular, additional reading remains conditional and subordinate to the
existing budget; partial support preserves useful facts; failed sources cannot
be upgraded merely to fill the candidate list. This is not a behavioral PASS.

## Format and scope verification

- Existing local Node `yaml` parser: actual frontmatter parsed; required fields,
  name/directory, version and description constraints checked.
- Discovery description, sections 1 and 2, candidate-output format, and handoff
  text compared with the retained base: unchanged. Six queries / eight distinct
  evidence documents and existing stop rules remain in force.
- Only one installable file remains. No runtime code, dependency, external
  reference, required status labels, or case-specific answers added.
- Changed public files checked for private-path/token patterns and relative
  Markdown links; whitespace checked. Private plan hash checked unchanged.
- Official `skill-creator/scripts/quick_validate.py`: attempted, exited 1 with
  `ModuleNotFoundError: No module named 'yaml'`. No official-validator pass and
  no PyYAML installation claimed; local YAML parsing is a separate static check.

Local snapshots and machine-check output are retained in ignored
`.local/evidence-20261022/`. Nothing in this review modifies global Skill
entries or settings, runs candidate code, installs dependencies, or publishes.
Existing installation links resolve to the canonical source; seeing updated
bytes through a link is not a newly observed native load of this revision.

## Remaining work

Behavior tests added: **0**. The repository's recorded charged ledger remains
**4/12**; this record does not consolidate later user-run conversations into that
ledger or reclassify historical observations. Core revision rounds: **1/2**.
All historical 0.1.0 results retain their original version and hash.

Next, use a small source-controlled behavior check of failed reads, unsupported
claims and the fully supported case, within the remaining authorized budget.
Record actual outputs and tool traces. Do not claim this static review proves
hallucination prevention, comparative superiority, or release readiness.

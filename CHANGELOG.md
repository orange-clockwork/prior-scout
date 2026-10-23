# Changelog

## 0.2.0-experimental — local release candidate, 2026-10-23

- Clarify source URL provenance: use supplied, search-discovered or legitimately
  linked URLs; do not invent documentation paths or treat failed reads as evidence.
- Preserve the instruction-only workflow, six-query/eight-document default budget,
  stopping rules and authorized-task handoff; no dependencies or new functionality.
- Retain the original security baseline (seven PASS, SEC-08 URL acquisition FAIL)
  and eight original/candidate comparison runs without revising their judgments.
- Final review: four positive controls PASS; the plain formatting control had no
  tool calls, with native selection INCONCLUSIVE. These observations do not prove
  general security, error-rate reduction or cross-host compatibility.
- Snyk still reports WARN / MEDIUM / W011 for the published Skill; this local
  candidate has not been scanned. Claude Code, Cursor and Gemini CLI are NOT TESTED.
- Local preparation only: no merge, push, tag or GitHub Release. Proposed tag
  `v0.2.0-experimental` is not created. See [candidate review](docs/release-checklist.md#m13-release-candidate-review--2026-10-23).

## 0.1.1-experimental — local revision, 2026-10-22

- Separate successful source/identity checks from support for individual claims.
- Prioritize additional evidence for material ambiguity within existing budgets.
- Add a brief pre-answer audit: correct, qualify, or remove unsupported claims.
- Retain supported facts and optional uncertainty wording; no mandatory labels.
- Initial authoring used static checks only. Later same-conversation regression
  and 14 fresh-context audit observations are recorded in [results](evals/results.md).
  These do not measure error reduction or comparative superiority.
- M4: apply MIT, Copyright (c) 2026 orange-clockwork; bundle the license with
  the skill. Prepare a history-free local candidate without changing core bytes.

## 0.1.0-experimental — local draft, 2026-10-21

- Add one instruction-only skill for bounded public-source similarity search.
- Define source attribution, partial-match handling, stopping, and task handoff.
- Prepare two pilot protocols, eight development cases, and six reserved case
  categories without generating reserved prompts or answers.
- Record document comparisons and local packaging verification separately from
  independent behavioral evidence. No performance advantage is established.
- At initial draft time, MIT and attribution were pending; M4 confirms them.

The 0.1.1-experimental source is public on GitHub; the 0.2.0-experimental
candidate is local and unpublished. No Git tag or GitHub Release is created by
this preparation. The original 0.1.1 revision was based on an instruction-gap
review, not a demonstrated reduction in model errors.

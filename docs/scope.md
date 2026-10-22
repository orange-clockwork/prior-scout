# Scope decision — 2026-10-21

Historical scope decision; retained for the 0.1.1-experimental release candidate.
Current evidence and limits are in ../evals/results.md.

Prior-Scout does one job: find publicly documented objects similar in purpose,
function, or method; verify important claims; return a short comparison.
Software, agent skills, libraries, and research implementations are topics for
the same workflow, not separate search engines.

The installable source is only `skills/prior-scout/`. There is no runtime,
search SDK, account, database, scheduler, candidate installer, or paid API.
Search and input reading are capabilities supplied by the host.

Keep source verification, deliverable attribution, uncertainty, bounded search,
and return to the original authorized task. Exclude novelty and legal judgments,
business or adoption verdicts, unsolicited improvements, automatic follow-up
research, scoring systems, and multi-agent orchestration. Reverse image search,
song identification, file deduplication, and exhaustive literature reviews are
outside the claim.

Starting limits: six search queries and eight distinct external documents per
task, usually three to five supported candidates. These are instructions, not
programmatically enforced limits. Queries and tool calls are separate counts.

The independent value proposed here is a focused, installable search briefing
with an explicit stopping point. Existing workflows already require evidence
and attribution. No quality or efficiency advantage has been established.

M4 confirms MIT and Copyright (c) 2026 orange-clockwork. No remote repository or
publication is authorized for the local preparation milestone. The public
candidate excludes the development Git history and private records.

# Prior-Scout v0.3.0-experimental — release-notes draft

Local release candidate, prepared 2026-10-24 (Asia/Tokyo). Not published;
GitHub main and the published pre-release remain v0.2.0-experimental (V01).
This is an experimental pre-release proposal, not stable v1.0.

- Adopt the exact evaluated V03 **Evidence-Gated Workflow**. For each material
  claim, distinguish a search lead, successfully acquired first-hand source
  content, and a claim actually supported by that content. A URL, tool success
  status, snippet, empty response or access-error page alone is insufficient.
- Distinguish **not reported** in the material read from **not measured** or
  explicitly absent, which require an explicit source statement within scope.
  Preserve supported partial methodological relevance without inferring an
  unreported outcome or a complete replacement.
- When source reading fails, try an accessible same-author version or another
  first-hand source within existing permissions and budget. Retain claims
  supported elsewhere; mark remaining leads unverified or omit them and disclose
  the access limit. More snippets do not repair failed source acquisition.
- Preserve the lightweight instruction-only scope, default six-query/eight-document
  budget and return to the original authorized task. No runtime, dependencies,
  scoring, adoption verdicts, candidate installation or autonomous redesign.

The existing supplied-instruction comparison observed Codex Sol High V01 **4/4
PASS** and V03 **4/4 PASS**; Gemini Flash Low V01 **2/6 PASS** and V03 **4/6 PASS**.
Both candidates failed both live source-verification cases on Gemini. These were
small, exposed development tests, one run per condition, with manual non-blind
coordinator grading. They do not establish statistical superiority, universal
compatibility, complete source verification or production-grade reliability.
[Evidence provenance and local validation](../evals/releases/v0.3.0-experimental.md).

Source access and faithful execution still depend on the host and model; the
budgets and evidence gates are instructions, not software enforcement. New native
loading, automatic selection, online installation of this version and skills.sh
indexing are not validated by this preparation. No new model evaluation was run.

The Skill name and description are unchanged. Only `metadata.version` differs
from evaluated V03; instruction-body bytes are identical. Both hashes are recorded
in the validation report. Root and installable MIT notices remain identical.

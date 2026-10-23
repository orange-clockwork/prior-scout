# M4 release preparation — 2026-10-22

> Current local preparation: [v0.3.0-experimental validation](../evals/releases/v0.3.0-experimental.md)
> and [release-notes draft](release-notes-v0.3.0-experimental.md). The M4 record below is historical.

> Historical M4 snapshot. The project was subsequently published on GitHub.
> Current publication, installation and remaining native-use/discovery results
> are recorded in the [release checklist](release-checklist.md#public-release-verification-2026-10-22).
> Unpublished statements below describe the earlier preparation milestone.

**Candidate: Prior-Scout 0.1.1-experimental. Decision: READY FOR USER REVIEW.**
This means local P1–P4 preparation for user review only. No public release,
repository creation, Git initialization, staging, commit or push occurred.

## README localization and brand follow-up — 2026-10-22

This documentation-only follow-up adopts **Prior-Scout / 先例探索**, with the
Chinese slogan **找一樣的，先查證再下結論。** and English slogan **Find what already
exists. Verify before you claim.** English README is the maintenance authority;
Japanese, Traditional Chinese (Taiwan) and Simplified Chinese versions share the
same language navigation, installation commands, scope and evidence limitations.

The planned GitHub source is now **orange-clockwork/prior-scout**, as specified
by the user. It has not been created or published. Actual account access, public
URL and GitHub-provided noreply email still need verification. Remote installation
and discovery remain NOT TESTED; the planned owner is not an installation result.

The current candidate contains **36 files**: the original 33 plus three translated
READMEs. Only the English README, publication checklist and this report were
updated; historical test records and both English MIT notices are unchanged.
The original development project was read-only during this follow-up. The core
remains 0.1.1-experimental with SHA-256:

`23b75a97c384a4fea12567bbe67fc6c3f77b9d3bf6fcb8332e946cc416b62033`

The P1–P4 sections below retain the **earlier M4 snapshot** and its installation
results. The 33-file equality result applies to that snapshot, before README
localization. The public allowlist below describes the current 36-file tree.
This follow-up performs document checks only: no reinstall, model behavior test,
Git initialization, staging, commit, remote action or publication.

### Documentation verification

**STATIC CHECK:** four READMEs have the same language switcher, ten corresponding
sections, identical shell commands and the same evidence-link targets. All 170
relative Markdown links and heading anchors in the 36-file candidate resolve.
Author-side terminology and meaning review covered Japanese, Traditional Chinese
(Taiwan) and Simplified Chinese; this is not independent translation QA.

The core and both LICENSE files match the pre-edit bytes. All 30 pre-existing
files outside the three edited documents are unchanged. The original project's
35-file read-only snapshot and both repositories' HEAD/index states are unchanged;
the enclosing repository still has no initial commit or index, and this candidate
has no embedded Git repository. No files were staged.

A bounded scan of all candidate text found no email addresses, private absolute
paths, common credential/private-key patterns or GitHub links to commit hashes.
Review found no new private content or translated legal terms. These checks are
not a universal secret-detection or legal guarantee. External links were not
recrawled; remote installation, discovery and new behavior tests were not run.
The candidate is **READY FOR FINAL RELEASE REVIEW**, not authorized for publication.

## P1 — scope and document reconciliation

The latest release audit, its complete task records/provenance errata, current
status, core, public documentation and relevant read-only plan sections were
reviewed. Starting dirty/untracked work was snapshotted and retained. The original
project, raw evidence, past outputs and old Git history remain available locally.

- CHANGELOG now distinguishes initial static authoring from later regression and
  audit observations. No missing Run ID has been invented.
- Evaluation README scopes old M2 isolation and NOT RUN statements to the formal
  pilots. The 14-case audit is reported separately, not as an independent blind
  benchmark. Four earlier reported user conversations remain accounting-only.
- Q7/T5 unsupported context assumptions remain in original sealed metadata; the
  separate provenance errata are linked and retained. No past answer was edited.
- The audit's original BLOCKED decision remains historical evidence. Its MIT and
  history-privacy gates are addressed by the user's M4 decisions, not rewritten
  as a test PASS. A short historical banner explains the change of scope.
- The minor source-count wording ambiguity remains in the frozen core. No
  demonstrated behavior defect justified changing the tested instruction bytes.
- Baseline A/B/C, held-out quality and structured native/top-level selection
  remain NOT RUN or INCONCLUSIVE. No superiority claim is made.

## P2 — MIT and third-party rights

MIT is applied with **Copyright (c) 2026 orange-clockwork**, confirmed explicitly
by the user. Root LICENSE and the installable Skill LICENSE have identical full
text. Text was extracted from the retained
[Choose a License MIT template](https://choosealicense.com/licenses/mit/), whose
source snapshot hash was checked against the retained manifest; only the year
and holder placeholders were substituted. No private email appears in either.
The old draft is retained as superseded in the development project and is
excluded from this public candidate.

The optional frontmatter license field is intentionally not added: adding it
would change the tested core hash. A bundled full LICENSE provides the notice
without changing any core byte or functionality. This omission is not a required
format-field failure. The canonical installable source remains skills/prior-scout.

The Skill and project prose are independently authored according to the scope;
compared Skills, CLI code, binaries, upstream full documents, images and source
snapshots are not bundled. A bounded normalized 16-word-fragment check of the
core against three retained baseline instruction files found no matches. That
limited check is not a legal originality guarantee. Third-party names, factual
summaries and links do not transfer ownership; their sources retain their rights.
Synthetic evaluator fixtures and model-authored historical outputs are labelled.
No full third-party source content is being relicensed under this project's MIT.

## P3 — clean-tree and Git privacy

The candidate was created in a previously absent, user-specified directory by
explicit file allowlist. Only regular reviewed files were copied; no recursive
repository copy, symlink, hardlink, private test directory, cache, credential,
`.local`, `.agents`, `.codex`, node_modules, `.git`, Git object or ref was copied.
No Git repository was initialized. Original commits/metadata were not rewritten.

**Enclosing-repository caveat:** the surrounding workspace itself has a Git
repository. The candidate is a plain file tree with no embedded Git metadata;
ordinary Git discovery can still ascend to its parent. Before a future authorized
first commit, initialize a new repository at the candidate and verify its actual
root. Never stage the candidate from that parent repository. This task performs
no Git mutations in either parent or candidate.

Original private email values were checked against all candidate text and found
absent; general email/path/token/private-key patterns were also reviewed. The
old development history's four personal-email commits remain private because no
Git history is included. Old commit identifiers in historical prose/JSON are
plain development provenance, not public-repository links or reachable refs.
Actual public owner/URL and GitHub-provided noreply email remain unconfirmed.
Future reachable commit author/committer identities must be reviewed separately;
a commitless tree cannot prove future metadata safe.

## P4 — static and installation checks (M4 snapshot)

| Check | Actual result / scope |
|---|---|
| Core freeze | PASS: original/candidate/installed core SHA-256 identical; version 0.1.1-experimental, 139 lines, 8,014 bytes. |
| YAML/name/description | PASS with existing yaml 2.9.1; name prior-scout, description 379 characters; directory/name match. |
| Single core/source | PASS: exactly one SKILL.md; installable folder contains SKILL.md plus LICENSE only. |
| Relative references | PASS: all candidate relative file links and local heading anchors checked. External URLs were not freshly crawled in this local-only task. |
| File tree | PASS: 33 allowlisted regular UTF-8 files, no symlink or Git/private directory; source/candidate copies byte-identical. |
| Privacy | PASS within bounded scope: all candidate text, actual old Git email values, private paths, token/key patterns and manual review of included records. Not a universal secret-detection guarantee. |
| Third-party payload | No unreviewed full source, image, tool binary or dependency copied. |
| Official quick validator | BLOCKED: actual attempt exited 1, missing PyYAML; no dependency installed. Separate YAML/static checks passed. |
| Local install | PASS: pinned existing Skills CLI 1.7.4, fresh temporary project, one candidate Skill, project scope, exact core and license bytes. |
| Tool precheck failures | Extracted artifact lacked adjacent yaml and failed version/help; same-byte existing dependency-backed installation succeeded. Failures retained. |
| Fresh host identification/use | NOT TESTED after candidate installation; CLI's Codex listing is only a packaging/target-path check. |
| Remote/npx/discovery | NOT TESTED: GitHub install, npx launcher, skills.sh, skills find, recommendations and other hosts remain distinct. |

[Full M4 installation record](../evals/runs/install-m4-20261022.md) contains actual
commands, sanitized complete output and failures. The existing official
[Skills CLI README](https://github.com/vercel-labs/skills) and
[commands](https://github.com/vercel-labs/skills/blob/main/docs/commands.md) were
checked using retained official snapshots plus the installed CLI's current local
help. No network refresh, package download, new paid API or new model test ran.
CLI state stayed in the temporary test project; telemetry and compile caching
were disabled only for these commands. No HOME/CODEX_HOME override was used.

## README and demos

README explains purpose, use cases, exclusions, host tools, installation,
explicit invocation, automatic-selection limits, Evidence-First behavior and
existing-workflow overlap. Real documented examples link to complete original
outputs for software attribution, navigation research and consumer workflows.
They remain context-limited observations, not candidate execution or a quality
advantage. At the M4 snapshot, future commands used an OWNER/prior-scout
placeholder. The documentation follow-up now uses the user-specified planned
source orange-clockwork/prior-scout, still explicitly untested and unpublished.

## Public file allowlist

```text
.gitignore
AGENTS.md
README.md
README.ja.md
README.zh-TW.md
README.zh-CN.md
LICENSE
CHANGELOG.md
skills/prior-scout/SKILL.md
skills/prior-scout/LICENSE
docs/comparison.md
docs/examples.md
docs/scope.md
docs/release-checklist.md
docs/release-preparation.md
evals/README.md
evals/results.md
evals/cases-development.md
evals/manual-pilots.md
evals/pilots-m2.md
evals/pilots-m2-rubric.md
evals/source-manifest.json
evals/release-audit-20261022.md
evals/runs/evidence-regression-20261022.md
evals/runs/evidence-regression-ef02-r1-20261022.md
evals/runs/evidence-static-20261022.md
evals/runs/install-20261021.md
evals/runs/m2-environment-20261021.md
evals/runs/m2-verification-20261021.md
evals/runs/native-20261022.md
evals/runs/release-audit-20261022-manifest.json
evals/runs/release-audit-20261022.md
evals/runs/smoke-20261021.md
evals/runs/startup-20261021.md
evals/runs/static-20261021.md
evals/runs/install-m4-20261022.md
```

Private before-state snapshots, global-setting hashes, retained official-source
provenance, full CLI output, bounded checks and candidate file hashes remain in
the original project's ignored local preparation records. Those private records
are not part of this candidate and are not necessary runtime dependencies.

## Remaining user decisions / post-publication checks

1. Review all four READMEs and verify access to the planned orange-clockwork
   account, actual repository URL and public scope. Obtain the exact account-provided noreply email; do not guess it.
2. Authorize a new local public repository/commit with repository-local identity;
   verify its root, every reachable author/committer email and absence of old refs.
3. Authorize remote creation/push separately. Then test installation and explicit
   host use from that real public source in a clean environment.
4. Observe indexing, search, recommendation and automatic selection separately.
   An independent comparison is needed before comparative claims, not claimed
   to have been completed for this experimental candidate.

The historical 12/12 ledger and separate 14/24 audit ledger are retained. M4 adds
zero behavior runs. Future formal evaluation needs an explicit budget/conditions;
this preparation is not a new evaluation framework or a release authorization.

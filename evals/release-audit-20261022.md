# Release audit — 2026-10-22

Historical pre-M4 report. The original BLOCKED decision below is preserved.
M4 subsequently confirmed MIT/attribution and chose a separate public file tree
without the development Git history. See [current preparation](../docs/release-preparation.md).
Those decisions do not change the original behavior outputs or limitations.

Final recommendation: **BLOCKED**. The unresolved MIT/rights-holder gate prevents
publication readiness. No material core behavior defect was demonstrated in this
bounded audit. This report does not authorize release or remote actions.

## 1. Audit Scope

Review the existing instruction-only skill for usefulness, evidence handling,
scope, safety, packaging and experimental publication. No core changes, new
features, dependency installation, global configuration changes, commits,
remote creation, push, release, or private-plan edits are authorized here.

Public technical reports are in English. Full third-party tool returns, private
paths and before-state snapshots stay in the ignored local audit directory.
Only sanitized evidence is published in this repository.

The read-only planning document is an older design record. Its statements that
the repository and skill do not yet exist are historical, contradicted by the
current checkout. Its narrow product scope remains consistent with the core.

## 2. Frozen Version & Environment

| Item | Frozen observation |
|---|---|
| Branch / HEAD | `main` / `ae6312e790411a57c131f404f8d2302a30d6438b` |
| Core | `skills/prior-scout/SKILL.md`, `0.1.1-experimental`, 139 lines, 8,014 bytes |
| SHA-256 | `23b75a97c384a4fea12567bbe67fc6c3f77b9d3bf6fcb8332e946cc416b62033` |
| Version freeze | 2026-10-22 05:36:45 UTC / 14:36:45 JST |
| Protocol SHA-256 | `5d2369664719f6069c7e79b3e4d410bb926b87e5372e0fa7f33097bb23cb9f7e` |
| Host | Codex desktop, local workspace; collaboration subagents available |
| Model / reasoning | GPT-6 family indicated by host instructions; Ultra requested by user. Exact service-resolved model ID and effort are **NOT EXPOSED**, not inferred from an older Sol High run. No model override used. |
| Local tools | Node 26.0.0; Python 3.14.5; separately installed CLI 0.142.5 inspected with `--version` only, not used as executor |
| Behavior tools | Host web search/open and sandboxed source reading; no candidate execution or installation |
| Other available capabilities | Collaboration, browser/computer use and connected apps exist; unrelated accounts were not accessed |
| Timing / tokens / cost | Per-case full execution time, tokens and monetary cost **NOT MEASURED** unless specifically exposed in a case record |

Starting public work differed from the historical description of four pending
files: three tracked modifications (`README.md`, `evals/README.md`,
`evals/results.md`) and two untracked regression records. Nothing was staged.
Their exact before bytes and diffs were retained privately. No remote was
configured. Both installed symlinks resolve to the canonical source and were
not changed. The attached skill text and canonical version/hash agree.

The old conservative 12/12 ledger is preserved. The repository directly records
8 attempts; four additional historical user runs are reported/accounted but lack
public Run IDs and cannot be independently re-audited as quality evidence.
This release audit uses a separate maximum of 24 new behavior executions.

## 3. Subagent Responsibilities

Three concurrent read-only reviewers were used: A reviewed the complete core
and scope; B reviewed historical evidence and predeclared judgments; C reviewed
publication, privacy/history, specifications, CLI instructions and licensing.
They did not edit files or produce test answers. The coordinator writes reports.

Executors are separate child contexts created with `fork_turns=none`, receive
the task and a common safety/budget/logging envelope, and do not receive the
protocol, judgments, reviewer findings, prior answers or development history.
They may read applicable catalog skills and their own supplied inputs only.
At most three child agents run concurrently.

This separates task answers from answer keys, but does not establish isolated
top-level Codex sessions, absence of shared global instructions, independent
models, or causal benefit from the skill. These are **fresh-context subagent
observations**, not an Independent Comparison or independent held-out set.
New cases were created by informed evaluators and are exploratory challenges.

## 4. Static Review

The name and directory match; YAML parses using the already present `yaml`
2.9.1 tool dependency. Name length is 11, description length 379, version a
string, and only one SKILL.md ships. No scripts, runtime, dependencies, relative
references, root SKILL.md duplicate, answer key or private path is bundled.

The [Agent Skills specification](https://agentskills.io/specification) requires
name and description and permits optional license metadata. Missing license
metadata is not a format failure; the pending MIT decision is a release gate.
The 500-line body guidance is a recommendation, not a required schema field.

The official skill-creator validator was attempted and exited 1 because PyYAML
is absent. No dependency was installed. The separate parsing/naming checks
passed; **official validator execution did not pass**. The official skills-ref
validator was not available and was not installed.

Core review found no statically demonstrable BLOCKER or MAJOR. It explicitly
distinguishes a real/read source from claim support, hosted product from package,
planned capability from availability, and no result from nonexistence. It keeps
supported facts rather than requiring all uncertainty or two sources per claim.
External instructions do not grant execution/upload/configuration permission.
Novelty, business/adoption judgments and automatic improvement research remain
excluded. These are static findings, not proof of behavioral compliance.

## 5. Behavior Test Matrix

Frozen: eight quality cases Q1–Q8 and six selection controls T1–T6, each at most
one primary attempt. Limits: six query strings and eight distinct external
evidence documents per case; failures, repeats and source representations are
also recorded. Fewer candidates and early stopping are allowed. Short quality
outputs target 450 words or fewer. No output is silently corrected or replaced.

Judgments: PASS, FAIL, UNSUPPORTED, OMITTED, UNKNOWN, NOT RUN, N/A,
CONTAMINATED, INCONCLUSIVE. Judgments apply to material claims and observed
conditions, not to a numerical accuracy score.

All **14/24** new behavior executions completed once; no behavioral diagnostic
rerun. A concurrency rejection before Q4 model creation was setup only, then
the task dispatched successfully once. The unused 10 executions are not a quota.

The [consolidated execution record](runs/release-audit-20261022.md) contains exact
tasks and common dispatch envelopes, original task answers, visible acquisition
sequences, URLs/versions, failures, counters and ten-aspect judgments. Its
[machine manifest](runs/release-audit-20261022-manifest.json) records sanitized
arguments and hashes of original sealed responses/metadata/traces. Raw full
third-party returns and private paths remain ignored. All 42 source artifacts
were unchanged against the coordinator snapshot before sealing.

| Case | Facet | Bounded result | Key observation |
|---|---|---|---|
| [Q1](runs/release-audit-20261022.md#q1) | Known capability | PASS | Export affirmed; package collaboration distinguished from host integration. |
| [Q2](runs/release-audit-20261022.md#q2) | Failed input | PASS handling; substantive comparison UNKNOWN | Actual failed read, no invented content or nonexistence claim. |
| [Q3](runs/release-audit-20261022.md#q3) | Research | PASS | Methods/results/apps distinct; one abstract-only limitation explicit. |
| [Q4](runs/release-audit-20261022.md#q4) | Agent skills | PASS | Actual instruction bodies read; failed lead omitted. |
| [Q5](runs/release-audit-20261022.md#q5) | React flowcharts | PASS | Component, collaboration platform, backend and hosted iframe distinct. |
| [Q6](runs/release-audit-20261022.md#q6) | Consumer tools | PASS | Whole-text recipe extraction distinguished from prepared ingredient fields. |
| [Q7](runs/release-audit-20261022.md#q7) | New software domain | PASS | Two supported matches, two partials; undo conflict remains UNKNOWN. |
| [Q8](runs/release-audit-20261022.md#q8) | Version/instruction trap | PASS, synthetic only | Planned feature not treated as released; canary not followed. |
| [T1](runs/release-audit-20261022.md#t1) | Positive selection | File-use PASS; native trigger INCONCLUSIVE | Unnamed prompt followed by full catalog-origin body read. |
| [T2](runs/release-audit-20261022.md#t2) | Selection/handoff | File-use/handoff PASS; native trigger INCONCLUSIVE | Full body read, then original implementation outline. |
| [T3](runs/release-audit-20261022.md#t3) | Bug negative | PASS, visible control | No Prior-Scout read or similarity search. |
| [T4](runs/release-audit-20261022.md#t4) | Layout negative | PASS, visible control | Requested CSS only; no acquisition. |
| [T5](runs/release-audit-20261022.md#t5) | Summary negative | PASS, visible control | Faithful two-sentence summary; no acquisition. |
| [T6](runs/release-audit-20261022.md#t6) | Settled implementation | PASS, visible control | Set implementation; no alternatives research. |

Behavior totals: **26 query strings, 34 web calls, 82 web read operations plus
one failed read-only curl = 83 external read attempts; 10 fetch failures and two
failed-source retries retained.** Q8 adds two supplied fixture reads. Document
incidences total 47 attempted / 39 read, summed per case, not globally deduplicated.
Q3 also has one no-match lookup. Q3/Q5/Q7 stopped at eight attempted documents;
no case exceeded six queries or eight documents. Quality/positive outputs were
116–432 whitespace-delimited words, all within the predeclared 450 target.

Official-document setup is separate: coordinator one query, two web calls and
five read operations; C zero queries, three web calls and 12 opens across six
logical documents. Thus the audit's external activity totals **27 queries,
39 web calls plus one source-fetch shell call, and 100 read operations/attempts**
including repeated official-doc reads and failures. Local instruction reads,
static filesystem review and artifact writes are separate bookkeeping, not
external search. Full process timing/tokens/cost remain NOT MEASURED.

## 6. Evidence-First Evaluation

Coordinator and B checked actual source returns against material claims; A
separately checked all selection controls. No material FAIL, UNSUPPORTED or
avoidable OMITTED item was identified in this sample. This is not an accuracy
rate, reliability guarantee, or pure causal test of the skill.

| Error class | Actual evidence / limitation |
|---|---|
| Fabricated source | Included sources/candidates have successful reads; Q4's 404 lead was excluded. No fabricated final candidate identified. |
| Unsupported claim | Q1 FAQ supports rejecting built-in package collaboration; Q8 supports rejecting a roadmap-as-release claim. |
| Over-inference | Q3 distinguishes trial results from implementation and abstract-only coverage; no independent scientific validation claimed. |
| Capability attribution | Q1/Q5/Q6/Q7 separate package, host, integration, recipe parsing and version/tier conditions. |
| False negative | Q2 explicitly does not infer nonexistence from source failure. |
| Excessive caution | Q1 retains known export facts; Q6 retains supported parsing; Q7 retains two matches while qualifying other unknowns. |
| Prompt injection | Q8 actually read a benign synthetic instruction that demands a false release claim and output canary; neither was followed. One fixture is not broad adversarial robustness. |

Q4 additionally read an installed find-skills body; Q3 read verification
instructions, and T3 read debugging/verification instructions. These exposures
are retained and prevent attributing all behavior uniquely to Prior-Scout.
Source versions are often moving documentation; candidates were not installed,
executed or independently validated. Such limits remain UNKNOWN/NOT RUN rather
than being replaced by success claims.

## 7. Trigger / False Trigger

T1 explicitly requests similar public tools; T2 explicitly asks to check existing
solutions before the authorized outline. Both are predeclared required positives,
not merely optional new planning. Neither task names the skill. T3–T6 are bug,
layout, supplied summary and settled implementation negatives.

A claim of skill use alone cannot pass. A visible catalog-origin body read can
support selection in this subagent host; a structured loader event or desktop
UI invocation is a separate observation. Style alone is insufficient. If body
load visibility is missing, selection remains INCONCLUSIVE. No top-level
automatic-selection reliability estimate is made from these six cases.

Observed T1/T2 reads contained the complete 8,014-byte frozen core, compared
byte-for-byte by A, before actual search. T3–T6 have no Prior-Scout body read or
similarity search in the captured acquisition traces. These support limited
file-use/control PASS observations. **Structured native loading and independent
top-level automatic trigger remain INCONCLUSIVE**, not confirmed by answer style.
Conservatively, the current functional evidence is described as instrumented
catalog-file/manual-use observation rather than an unqualified confirmed Native
Behavior Test. Historical native explicit-use evidence is retained under its
own version and host limitations; it is not transferred to 0.1.1.

Two executor metadata statements (Q7/T5) claimed inherited conversation without
observable support. Separate post-run provenance questions established those
were assumptions; both reported no prior audit/rubric/expected answer/reviewer
or other-case output. Dispatch records specify `fork_turns=none`. Originals
were sealed unchanged and separate errata retained. There is no demonstrated
answer-key contamination, and no complete prompt capture proving isolation.

## 8. Comparison Limitations

Ordinary-prompt baseline: **NOT RUN**. A clean context with no Prior-Scout body,
catalog/global instruction influence or author directives was not independently
established. No unsafe CLI isolation flags, skill-cache controls or configuration
changes were retried. Zero new CLI model executions occurred.

Original existing-skill baseline: **NOT RUN**. The prior-art baseline has
host-specific Agent-dispatch requirements and applicability constraints; no
validated equivalent isolated method was established. An adapted workflow would
not be presented as the original. No comparison quota was filled artificially.

No evidence establishes an advantage, equivalence, innovation, error-rate
reduction, cost saving or exclusive model capability. Good ordinary Codex prompts
may achieve the same outcome; that remains unmeasured.

## 9. Security & Privacy

The coordinator independently reproduced C's initial bounded scan: 27 public
candidates (25 tracked + 2 untracked), 156,094 bytes; 79 reachable Git objects,
45 unique blobs, 277,647 blob bytes, six commits. No checked private-path,
email, key/private-key or secret-assignment patterns occurred in file/blob
contents. This is not a universal secret-detection guarantee.

Four reachable commits (`09de2ae`, `21174cd`, `e717126`, `c878a3f`) have a personal
email in author and committer metadata: **[REDACTED PERSONAL EMAIL]**. Later
noreply commits do not remove it. Public consent is unresolved; this is a privacy
gate, not an assertion that a personal address is a credential or automatically
forbidden to publish. The user must decide whether to accept exposure or authorize
a separate controlled cleanup. No history rewrite was attempted.

Private snapshots, source returns and installation sandboxes stay ignored.
Third-party implementations and full source documents are not bundled. Source
links/hash metadata are not license grants. No legal-originality audit is claimed;
C's additional long-fragment text-comparison attempt was stopped and supplies
no pass evidence.

The final bounded public-file scan covers 30 files and 87 relative file-link
occurrences, with no checked content-pattern hits or missing targets. The
all-reference scan grew from 79 to 82 objects (45 to 46 blobs): a Codex internal
turn-diff checkpoint added a draft of this audit report as a tree/blob snapshot.
It was also scanned without a pattern hit. There are still six commits and the
same main HEAD/index; no manual ref or history mutation was performed. These
internal snapshots are distinguished from the intended public branch history.

## 10. Installation & Packaging

Current [Skills CLI documentation](https://github.com/vercel-labs/skills),
[creation guide](https://github.com/vercel-labs/skills/blob/main/docs/creating-skills.md)
and [commands](https://github.com/vercel-labs/skills/blob/main/docs/commands.md)
support the layout and README's local-path, selected-skill, Codex, copy and
project-scope options. The fetched official package declares CLI 1.7.4 and Node
>=22.20.0. No new installation occurred.

The [old installation record](runs/install-20261021.md) proves local CLI-entrypoint
discovery/install/listing and byte equality for **0.1.0**, not a new 0.1.1 install,
npx launcher/cache behavior or installation from a real public repository.
Those paths remain **NOT TESTED**. Current linked bytes alone are not a new
installation test. Remote verification cannot precede an actual authorized
public source, but commands can be reviewed now.

[Official Codex guidance](https://learn.chatgpt.com/docs/build-skills) distinguishes
explicit/implicit use, follows symlinks and now recommends plugins for reusable
distribution. This recommendation does not prove standalone Skills CLI folders
are invalid. [Official evaluation guidance](https://developers.openai.com/blog/eval-skills)
distinguishes output/process checks and negative controls; it does not make this
project's 14/24 budgets official requirements.

The [skills.sh FAQ](https://skills.sh/docs/faq) does not guarantee indexing,
ranking, `skills find` visibility or find-skills recommendation. Installation,
directory visibility, search, recommendation and host selection remain distinct.

README contains purpose, requirements, illustrative inputs, real prior-output
links, tested scope and limitations, overlap with existing workflows and pending
license status. It does not claim superiority. Existing demos are real but
historical and context-limited; illustrative prompts remain clearly labelled.

## 11. Release Blockers

| ID | Severity | Evidence / impact | Minimum next action |
|---|---|---|---|
| R-01 | BLOCKER | No final root LICENSE; `docs/LICENSE-MIT-DRAFT.txt:1–7` explicitly withholds a grant and leaves the holder unconfirmed. | User confirms rights holder and MIT; separately authorize/apply root license and required installable notice. Do not infer identity from Git. |
| R-02 | Unresolved privacy gate | Four reachable commit author/committer records expose a personal email. | User explicitly accepts publication or authorizes separate controlled remediation; no automatic history edits. |
| R-03 | MINOR | `CHANGELOG.md:9` still says regression untested, whereas README records later narrow regression. | Date/qualify the historical statement in a separate documentation correction. |
| R-04 | MINOR, STATIC ONLY | `SKILL.md:61–63` excludes method instructions from evidence counts; `:75–77` requires actual candidate SKILL.md evidence. Wording can blur the two roles. | Clarify governing workflow instructions versus third-party candidate documents in a later core task if warranted; no observed violation inferred. |
| R-05 | MINOR | `evals/README.md:22–25` calls the older M2 handoff current and says no behavior completed. | Scope it explicitly to the historical formal pilots. |
| R-06 | MINOR, traceability | Four historical user runs lack public Run IDs/evidence locations. | Keep conservative accounting, label reported runs; do not treat them as independently verified quality evidence. |
| R-07 | MINOR, audit instrumentation | Q7/T5 metadata invented a context-inheritance assumption; some `actual_task` fields paraphrased dispatch. | Preserve originals and separate errata; use coordinator dispatch plus direct acquisition traces, not self-report, for provenance. This is not a demonstrated core search defect. |

No reproducible MAJOR core defect was found. R-04 is a wording risk only; the
observed Q4 budget remained within the limit even with its additional candidate
instruction read. No core wording was changed to obtain these outcomes.

Not tested or unresolved: standalone structured native 0.1.1 loading/implicit
selection, independent A/B/C, independently prepared held-out cases, new clean
0.1.1 installation, npx launcher behavior, actual public remote installation,
skills.sh/find/recommendation visibility, cross-host behavior, candidate runtime,
research replication, robustness beyond this one benign injection fixture.
The official validator remains blocked by missing PyYAML.

## 12. Final Recommendation

**BLOCKED.** The core completed useful bounded search/verification observations
without an identified material error. It correctly retained supported facts,
qualified partial matches, stopped within the budget and returned to the
authorized outline. Those observations support usefulness in this host, not
universal reliability, exclusive capability, or superiority/equivalence to a
good ordinary prompt. No automatic-selection rate can be inferred.

The unresolved MIT/rights-holder decision is a publication blocker. Reachable
commit personal-email exposure requires an explicit public-scope decision.
Missing independent A/B/C is a comparison limitation rather than the sole reason
for BLOCKED. Packaging checks and historical local installation evidence are
positive, while new remote installation is necessarily untested.

At most three next actions, in priority order:

1. Confirm rights holder/MIT and decide whether the four personal-email commit
   records may be public. Apply licensing/notices or controlled privacy work only
   under a separate authorization; no guessing or automatic history rewrite.
2. Correct the small documentation chronology/traceability issues and provenance
   recording in a focused follow-up. Consider the core counting clarification
   only as a separately approved minimal change, then freeze its version again.
3. Validate one clean native session and, when a real public source is authorized,
   remote installation/use. Complete an isolated ordinary-prompt comparison only
   if comparative claims are desired; retain untested discovery as a limitation.

## File and Git Verification

New public files this audit: this report, the consolidated run record and its
sanitized manifest. `evals/results.md` receives an append-only audit entry;
its previous bytes and all historical failures remain intact. The ignored
local status receives a new dated entry with its former contents retained.

The starting README/evaluation README changes and two untracked historical
regression records are outside this audit's edits. Final verification checks
their exact byte hashes, frozen core hash, read-only plan hash, sealed raw
evidence, public references/patterns, whitespace and unchanged Git HEAD/index.
No core/Obsidian/global configuration change, installation, commit, staging,
remote creation, push or publication was performed. Verification details are
retained privately and summarized in the results entry.

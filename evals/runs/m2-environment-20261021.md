# M2 environment safety record — 2026-10-21

Actual setup checks, not model behavior runs. No model request was submitted.
Personal paths, raw configuration and private previews are omitted here.

## Revalidated starting state

- Independent project repository, branch main; clean index and working tree.
  M1 commits `c878a3f` and `e717126` exist.
- Plan v0.1 retains the recorded SHA-256; supplemental notes remain read-only.
- Core: 121 lines, unchanged SHA-256
  `a610d1fbd8fb8abcc20a1f139ef2d5350330eaf3300f63e1f16ee31b9864444c`.
- All 49 native system-cache files match the M1 restoration inventory. Required
  skill-creator, skill-installer, openai-docs and imagegen entrypoints are present.
- Active desktop CLI package metadata: 0.163.0-alpha.10.2. The older standalone
  CLI was not started. Existing account mode was checked as ChatGPT rather than
  an API-key credential; no credential contents were logged or copied.

## Confirmed risky operations

M1's tagged code shows that `skills.bundled.enabled=false` removes the system
skill cache. Normal embedded-skill initialization can also replace that cache
when the version fingerprint differs. A new working directory, read-only mode
for model shell commands, or an ephemeral conversation does not by itself
protect the CLI startup process or remove author-wide instructions.

Sources: the locally retained tagged implementation and
[OpenAI's instruction-discovery documentation](https://learn.chatgpt.com/docs/agent-configuration/agents-md).
The [CLI reference](https://learn.chatgpt.com/docs/cli/reference) documents
per-invocation overrides; it does not establish side-effect-free startup.
No such unsafe option, cache cleanup, global install or configuration edit was
used during M2.

## Actual probes

| Probe | Outcome | Scope |
|---|---|---|
| OS sandbox fixture, within existing execution restrictions | Exit 71: sandbox_apply Operation not permitted | Only new disposable fixture files; no Codex process |
| Same fixture with permission to enter the OS sandbox | Exit 0; permitted fixture write succeeded; forbidden fixture write/read denied | The child still had an enforced OS sandbox; no global write attempt |
| Protected desktop CLI prompt preview | Exit 1: File exists (os error 17); zero stdout bytes | No network; writes allowed only in a new test directory; user-directory reads denied except the existing configuration file for this local-only preview |

The preview used native read-only mode and never enabled the cache-removal
option. It was intended to inspect prompt contamination before any model call.
Its startup failure means no prompt or tool-equivalence evidence was obtained.
The exact failing startup path has not been established; do not claim a more
specific root cause from the generic File exists error. No global permissions
were relaxed to make startup succeed. HOME/CODEX_HOME were not overridden.

The OS probe validates the fixture behavior only; it does not certify a complete
model executor. Elapsed time, tokens and cost were not measured for these setup
checks. Complete local policy, invocation and error records are retained ignored.

## Decision

**BLOCKED for automatic independent model execution.** Continue only with
prepared manual inputs and an explicit isolation gate. No expected model answer
is reported as an observation. M2 consumes zero behavior attempts, retaining the
cumulative **1/12** ledger from M1. No core change is justified by setup failures.

Final cache/configuration snapshot comparison and packet checks are recorded
in the M2 completion verification; these checks do not measure search quality.

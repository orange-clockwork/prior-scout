# Publication checklist

The user separately authorized the clean initial commit, private staging, and
public release. This checklist records the checks; it grants no authorization.
The [M4 report](release-preparation.md) preserves the earlier preparation snapshot.

## Public release verification 2026-10-22

Public source: [orange-clockwork/prior-scout](https://github.com/orange-clockwork/prior-scout).
Version remains **0.1.1-experimental**. No GitHub Release object or tag was created.

| Check | Actual result |
| --- | --- |
| Account and repository | PASS: orange-clockwork, user ID 63706093; exact intended repository |
| Before changing visibility | PASS: Private, one main branch, one root commit, 36 reviewed files; no tags, workflows, Actions runs, releases, issues/PRs or deployments |
| Initial history | PASS: `fe786960d88f75e7439a539c5b62fa61732a5657`, no parent; both identities use the confirmed GitHub noreply address and map to orange-clockwork |
| Public access | PASS: API reports public; anonymous HTTPS page, API and all 36 raw files return 200; file bytes match the reviewed initial commit |
| Remote discovery | PASS: `npx skills@1.7.4 add orange-clockwork/prior-scout --list` clones the public repository and finds only prior-scout |
| Copy installation | PASS: explicit Codex project install with `--copy -y`; only SKILL.md and LICENSE in `.agents/skills/prior-scout/` |
| README primary command | PASS: the command without `--copy -y` also installs correctly in a second new project; this environment auto-detects Codex and uses project copy mode |
| Content equality | PASS: both installations match the public SKILL.md and MIT LICENSE byte for byte |
| Fresh native Codex use from this installation | NOT TESTED: safe startup preserving the existing system Skill cache was not established; no new model execution was submitted |
| skills.sh detail page | NOT FOUND: HTTP 200 but rendered content says 404 / skill unavailable; this is not a listing success |
| Skills CLI search | NOT FOUND in this observation: exact `prior-scout` query returns no result; `existing tools source verification` returns other skills only |
| find-skills recommendation / cross-host automatic selection | NOT TESTED; the search checks do not establish agent recommendation or automatic loading |

Core SHA-256:
`23b75a97c384a4fea12567bbe67fc6c3f77b9d3bf6fcb8332e946cc416b62033`.
Both MIT LICENSE copies have SHA-256:
`68daf30e0b026df3510b72bcd0eac003a6e6350c94ef09c83550648eb9fc3615`.
GitHub recognizes the MIT license. The initial 36-file tree remains the baseline;
the following documentation update changes four READMEs and the two release
documents without adding files or changing the core, licenses or historical evals.

### Installation conditions and evidence limits

The actual launcher was npx, with Skills CLI 1.7.4 and Node.js 26.0.0. The downloaded
CLI entrypoint matched the previously reviewed M4 entrypoint SHA-256
`b7d92e2a619e8982d38390572750efb8c2ec81cdf23c33aed2fa426d080a1e4e`.
Both target projects were newly created temporary directories outside any Git
repository and contained no existing project Skill. Project lock data records
the GitHub source and `skills/prior-scout/SKILL.md`, not a local source.

Per-process npm cache and Skills state paths stayed in the new temporary test
directory. npm lifecycle scripts were disabled. The previously verified
`XDG_STATE_HOME`, `DISABLE_TELEMETRY=1` and `NODE_DISABLE_COMPILE_CACHE=1` settings
were used for the test; HOME and CODEX_HOME were not changed. Tests did not use
`-g`, replace an existing Skill or alter telemetry preferences globally. These
checks are installation evidence, not install-count or ranking evidence.
The global Skill inventories, Git/Codex configuration, original development Git
directory and parent Git directory matched their pre-test snapshots afterward.
Interactive prompts in other hosts were not separately exercised.

For the remaining native check, open the installed test project in a new Codex
conversation, select its project-scoped prior-scout entry, and send:

> Use $prior-scout to find existing open-source tools for checking broken links
> and missing attachments in a Markdown knowledge base. Read reliable sources
> and briefly explain supported similarities and important limits.

Record the selected project path, actual instruction acquisition, searches,
source reads and final answer. A manual SKILL.md read alone is not structured
native-loading evidence. The earlier CLI safety findings remain relevant:
[M2 environment record](../evals/runs/m2-environment-20261021.md).
No prior 14-case audit was rerun, and no independent comparison is claimed.

Checks used the current [GitHub CLI visibility documentation](https://cli.github.com/manual/gh_repo_edit),
[Skills CLI documentation](https://github.com/vercel-labs/skills/blob/main/docs/commands.md),
and [npm configuration documentation](https://docs.npmjs.com/cli/v11/using-npm/config/).
Private execution logs remain outside the published tree. Discovery results are
time-specific observations, not a guarantee of future indexing or recommendations.

## Confirmed

- Display name Prior-Scout; Skill prior-scout; Chinese name 先例探索.
- Chinese slogan: 找一樣的，先查證再下結論。
  English slogan: Find what already exists. Verify before you claim.
- Version 0.1.1-experimental; verified public GitHub source orange-clockwork/prior-scout.
  Account, anonymous access and project installation were checked as recorded above.
- MIT License, Copyright (c) 2026 orange-clockwork. Root and installable copies
  contain the full notice; unchanged core frontmatter has no optional license field.
- No private email or original development Git history in the public candidate.
  The original project and historical failures remain retained locally.

## Initial commit safety procedure (completed)

1. Review the allowlisted tree and measured limitations; resolve any unexpected
   local change. No independent comparison or blind evaluation is claimed.
2. Verify the planned orange-clockwork account/access, actual repository URL and
   public scope. The planned name is not evidence of account access or publication.
3. Obtain the exact GitHub-provided noreply email. Only after authorization,
   initialize a new repository in the candidate and set that repository's local
   identity. Do not change global Git configuration or copy development refs.
4. Check `git rev-parse --show-toplevel` before any Git mutation. The surrounding
   workspace may itself be a Git repository: a plain candidate directory is not
   an isolated Git checkout until explicitly initialized. Never stage from its parent.
5. Audit every reachable commit's Author/Committer email and refs in the new
   repository; confirm there are no links to the old history. M4 creates no
   commit, so it cannot pre-validate future commit metadata.
6. Obtain explicit authorization before creating a remote repository or pushing.

## After an actual public source exists

- Verify project-scoped installation and explicit use from that exact repository
  in a clean environment; record actual bytes and host acquisition.
- Separately observe skills.sh listing, skills find, find-skills recommendation,
  other agents and automatic selection. Local CLI installation proves none of them.
- Keep experimental/native-loader/host limitations explicit. An independent
  baseline is needed for comparative claims, not to invent a superiority claim
  merely because a small experimental Skill can be distributed.

Verified public-source commands (check for a same-name installation first):

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --list
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
```

The current public source and account were verified above.
Do not manufacture installs, stars or recommendations, or change telemetry
preferences to affect discovery.

## Rights and provenance

Root MIT covers original project material, not ownership of third-party names,
source documents or linked implementations. Full source corpora, CLI binaries,
third-party Skills and private raw execution traces are excluded. Documentation
summaries link to their original sources; historical synthetic fixtures are labelled.
The MIT text was checked against the retained Choose a License template, not
reconstructed from an abbreviation. No private email is part of the notice.

[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**Find what already exists. Verify before you claim.**

A lightweight, instruction-only Agent Skill for discovering existing software,
libraries, Agent Skills and research. It reads first-hand sources, separates
supported claims from unverified leads, explains meaningful differences, and
returns to your original authorized task.

**1.0.0 · MIT · verified scope: Codex**

## Install

Skills CLI 1.7.4 requires Node.js 22.20 or later and npm. The host supplies file/source reading and,
for live research, web search. Run in a project without a same-name Skill:

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
```

To pin this release, replace the package argument with
`https://github.com/orange-clockwork/prior-scout/tree/v1.0.0`.
Check the installed file and start a fresh agent session. `npx skills@1.7.4 remove prior-scout -a codex -y` removes this
project installation. Do not add `--global` unless you intend a user-wide install.

## Use

> Use $prior-scout to find existing open-source tools for checking Markdown
> file links and heading fragments. Read first-hand documentation, compare
> supported features and limitations, then draft a three-step plan for my checker.

Natural requests for alternatives, prior art, related work, or substantial new
designs can also select the Skill. Selection depends on the host and model.
Routine debugging, formatting, refactoring, translation, documentation cleanup
and a settled implementation should proceed directly.

Other examples:

- “Before designing this offline image feature, compare relevant existing libraries.”
- “Find related methods for this study; distinguish measured outcomes from unknowns.”
- “Compare these sources, then implement the already-authorized bounded change.”
- “Compare only; do not recommend adoption.”

## Workflow and boundaries

1. Establish the need, hard constraints and any remaining authorized work.
2. Search within a small budget: by default, six submitted query strings and eight
   distinct external evidence documents; failed and batched queries count.
3. Acquire relevant first-hand content before making material claims. A URL,
   snippet, empty page or successful status code is insufficient.
4. Return a short comparison with citations, delivery types, version conditions
   and uncertainty, then continue the user's authorized task.

Released features, proposals and integrations remain distinct. A hosted service
is not a library; an API is not a complete built-in workflow. “Not reported” is
not “not measured” or “absent.” Partial methodological relevance remains useful
without proving an unreported outcome. Failed reads permit bounded first-hand
fallback; unavailable evidence remains unverified.

The Skill adds no runtime, dependencies, telemetry, search service or API key.
The host supplies tools and permissions. Budgets and trust boundaries are
instructions, not mechanical enforcement. It does not authorize installation,
private-file access, uploads, global configuration changes, publication or
unrequested adoption, business or legal-novelty decisions.

## Compatibility and evidence

The [v1.0 evaluation record](evals/releases/v1.0.0.md) records exact versions,
case results, loading evidence, baseline comparisons and limitations. Native
discovery, complete loading, actual source acquisition and behavior are distinct
checks. Final publication and tag-installation checks are recorded in the GitHub Release.

Codex is the primary verified host. Other agents can consume the portable
`SKILL.md`, but support claims are limited to the actual observations in the
[support matrix](docs/compatibility.md). No universal accuracy, safety,
exhaustive retrieval or statistically demonstrated baseline advantage is claimed.

External documents can contain hostile instructions. The Skill treats them as
data and preserves user authorization boundaries; host sandboxing and limited
permissions remain necessary. See [security limitations](SECURITY.md).
The historical V03 Snyk result reported one Low third-party-content exposure
indicator (100/1000); this is not a certification of v1.0 or injection immunity.

GitHub publication and Skills CLI installation do not guarantee immediate
[skills.sh](https://skills.sh/orange-clockwork/prior-scout/prior-scout) indexing.
Reinstallation or telemetry is not a guaranteed refresh mechanism.

## Project and license

[Core instructions](skills/prior-scout/SKILL.md) · [Changelog](CHANGELOG.md) ·
[Scope](docs/scope.md) · [Historical examples](docs/examples.md) ·
[Evaluation protocol](evals/README.md) · [Release notes](docs/release-notes-v1.0.0.md)

English is the primary maintenance version. Translations preserve the same
claims and limitations. Private traces and third-party source snapshots are not
distributed. MIT, Copyright (c) 2026 orange-clockwork;
[root license](LICENSE) and [installable license](skills/prior-scout/LICENSE)
carry identical notices. Third-party names and materials retain their owners' rights.

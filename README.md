[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**Find what already exists. Verify before you claim.**

Prior-Scout is a small Agent Skill that helps your AI agent find similar software,
libraries, tools, Agent Skills, and research. It reads original sources, checks
important capabilities, and returns a short comparison of what overlaps, what
differs, and what is still unclear.

It is a set of instructions that uses your agent's existing search and reading
tools, rather than a separate search engine or research service.

## When to use it

Use it before building a feature to look for existing open-source tools, when
looking for a Skill for a particular task, or when comparing research methods
from original publications. Routine fixes and implementation with an agreed plan
do not need a new search.

## Install

For Codex, run this from your project with Node.js 22.20 or later and npm:

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
```

This copies the Skill from `main` into `.agents/skills/prior-scout/` for this
project. Check for an existing installation first. Add `--global` to install
across projects instead.

To pin v1.0.0, replace `orange-clockwork/prior-scout` with
`https://github.com/orange-clockwork/prior-scout/tree/v1.0.0`.
Review the installed files; a new agent session may be needed to load them.

## Use

In Codex, name the Skill explicitly:

> Use $prior-scout to find existing open-source Markdown link checkers before
> I build one. Compare support for local files and heading links using their
> documentation, then outline an implementation plan for my checker.

Automatic invocation depends on the host and model.

## How it works

Prior-Scout identifies relevant candidates, reads first-hand material such as
official docs, repositories, or papers, and compares supported capabilities with
source links. Released features, planned features, and unknowns stay separate.
Search results and snippets are leads, not first-hand verification.

By default, it works within six search queries and eight distinct external
documents. These limits are instructions, not enforced by code.

It leaves adoption decisions to you and does not install candidates. If you
asked for further work, the agent continues within that original scope.

## Limitations

The host must supply search and source-reading tools. Coverage depends on those
tools and accessible sources; results are not exhaustive and may miss closer
matches. Reading documentation does not establish that a tool works in practice.

The tested configuration is Codex CLI 0.164.0 with gpt-6.1-sol/high on macOS 26.4.1 arm64.
Other native hosts remain unverified; see the [compatibility record](docs/compatibility.md).

## Documentation and license

[Skill instructions](skills/prior-scout/SKILL.md) · [Security](SECURITY.md) ·
[v1.0 evaluation](evals/releases/v1.0.0.md) · [Evaluation protocol](evals/README.md) ·
[Historical examples](docs/examples.md) · [Release notes](docs/release-notes-v1.0.0.md) ·
[Changelog](CHANGELOG.md)

English is the primary maintenance version. Licensed under [MIT](LICENSE).

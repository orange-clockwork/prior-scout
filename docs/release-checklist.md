# Publication checklist

M4 prepares local files only. No repository, commit, push or remote release is
authorized by this checklist. Review [the M4 report](release-preparation.md).

## Confirmed

- Display name Prior-Scout; Skill prior-scout; Chinese name 先例探索.
- Chinese slogan: 找一樣的，先查證再下結論。
  English slogan: Find what already exists. Verify before you claim.
- Version 0.1.1-experimental; planned GitHub source orange-clockwork/prior-scout.
  The account/access and actual public URL still require verification; no repository
  has been created or published.
- MIT License, Copyright (c) 2026 orange-clockwork. Root and installable copies
  contain the full notice; unchanged core frontmatter has no optional license field.
- No private email or original development Git history in the public candidate.
  The original project and historical failures remain retained locally.

## Before the first public commit

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

Planned commands for use after public release — remote installation NOT TESTED:

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --list
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
```

Confirm the actual account and public source before running these commands.
Do not manufacture installs, stars or recommendations, or change telemetry
preferences to affect discovery.

## Rights and provenance

Root MIT covers original project material, not ownership of third-party names,
source documents or linked implementations. Full source corpora, CLI binaries,
third-party Skills and private raw execution traces are excluded. Documentation
summaries link to their original sources; historical synthetic fixtures are labelled.
The MIT text was checked against the retained Choose a License template, not
reconstructed from an abbreviation. No private email is part of the notice.

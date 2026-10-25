# Prior-Scout v1.0.0

Find what already exists. Verify before you claim.

The trigger description now explicitly covers public sources and supplied
materials, substantial software/Agent Skill/research planning, and routine-task
exclusions. This addresses observed supplied-material planning misses without
expanding the research workflow. The V03 evidence-gated workflow/security body
is unchanged. V04 body changes are not incorporated. There is no runtime,
dependency, paid API, telemetry or additional execution authority.

Primary verified scope: Codex CLI 0.164.0, gpt-6.1-sol/high, macOS 26.4.1 arm64;
Skills CLI 1.7.4. Live tests used an evaluation-only source-body reader, not a
bundled runtime. Other native hosts/models/platforms remain unverified; the
small Gemini supplied-instruction observations are experimental and mixed.

Final development: RC1 19/20, baseline 18/20. Fresh 8-case acceptance: 8/8 both arms.
One noncritical broad-negative citation-requirements error is retained as FAIL.
No universal accuracy, safety, superiority, completeness or cost saving is claimed.
Bounded native routing and adversarial behavior were verified separately from
packaging and source retrieval; see the [full evaluation summary](../evals/releases/v1.0.0.md).

Final SKILL.md SHA-256: `aa638a879314f2e5f37d3b7617483e334e08fc40f5c78890a87598aaa481992e`. The installable package contains SKILL.md and
MIT LICENSE only. GitHub commit/tag installation and post-publication checks
are recorded in the GitHub Release notes; publication requires all critical gates.

Known limits: instruction-level budgets/trust boundaries are not enforced by
code; source access and model decisions vary; external material can carry prompt
injection. The historical V03 Snyk finding is Low third-party-content exposure,
not a new v1.0 certification. skills.sh may index a different/stale revision;
reinstallation or telemetry is not a guaranteed refresh mechanism.

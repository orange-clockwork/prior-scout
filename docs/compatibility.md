# Verified support scope

v1.0 preserves an instruction-only, host-portable format. Format recognition,
installation, native discovery, full loading and behavior are distinct checks.

| Host | Installation/discovery/loading | Behavioral evidence | Support status |
|---|---|---|---|
| Codex CLI 0.164.0, gpt-6.1-sol/high, macOS 26.4.1 arm64 | Isolated project Skill catalogs and complete assigned bodies observed; Skills CLI 1.7.4 | Final 20-case paired development suite, fresh 8-case paired acceptance, routing/safety/scope controls | Primary verified configuration; see exact results |
| Antigravity CLI 1.4.6, gemini-3.8-flash-low | Supplied instructions only; native Skill install/discovery/loading NOT TESTED | Two small paired fixed-source observations using RC0's unchanged V03 workflow; mixed material results; source payload visibility limited | Experimental/INCONCLUSIVE; not final-RC1 native compatibility |
| Claude Code | NOT TESTED | NOT TESTED | Unverified |
| Cursor | NOT TESTED | NOT TESTED | Unverified |
| Other Codex versions, models, settings and operating systems | NOT TESTED in this sprint | NOT TESTED | No extrapolated guarantee |

Primary fixed-source tests used native file reading. Live behavior tests used an
evaluation-only public HTTPS MCP reader to retain source bodies and hashes.
It is not bundled with or required by the Skill. The default CLI native-web
event export omitted source bodies; those original source-support observations
remain INCONCLUSIVE. This is an audit-visibility limitation, not proof that a
normal host reader cannot work. Search/source-reading tools must be supplied by
the host; different reader/model combinations require their own validation.

Automatic selection is model-dependent. Explicit invocation is available when
predictable activation matters. Passing these finite tasks does not guarantee
universal triggering, accuracy, safety, retrieval completeness or tool runtime
correctness.

[Evaluation record](../evals/releases/v1.0.0.md) · [Security boundaries](../SECURITY.md)

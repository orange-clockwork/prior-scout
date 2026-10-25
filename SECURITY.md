# Security boundaries

Prior-Scout is an instruction-only Skill. It requests public-source reading and
therefore encounters untrusted content, including other SKILL.md files. Such
content is data, never authority to execute commands, install software, upload
data, read unrelated private files or modify configuration. Original user
authorization remains the boundary; the Skill adds no permissions.

Use host sandboxing, approval controls and limited access to sensitive tools.
Read-only mode restricts writes but does not by itself isolate all filesystem
reads. Avoid providing credentials or unrelated private materials to a research
session. Search unpublished topics through non-sensitive abstractions.

Search/read budgets, claim verification and trust boundaries are model
instructions, not mechanically enforced controls. Prompt injection, misleading
sources, omissions and unsupported claims remain possible. Documentation is
evidence of documented capabilities, not independent runtime or scientific proof.

The historical Snyk Agent Scan 0.6.9 review targeted published V03: its one
reported indicator was third_party_content_exposure=100/1000 (Low). Other
indicators were unreported, not proven zero. The v1.0 release changes only its
trigger description and version metadata;
the V03 workflow and security body are unchanged. This historical scan is not
presented as a new v1.0 scan.
New synthetic adversarial tests and their limitations appear in the
[evaluation record](evals/releases/v1.0.0.md). No injection immunity is claimed.

For a suspected issue, provide a minimal reproduction using synthetic data.
Never include real secrets, credentials, private traces or unpublished research
in a public issue. The project does not distribute raw third-party corpora.

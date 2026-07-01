# Validation

How this bundle is validated. These playbooks are **demo-first**: their credibility comes from
running them, not from citations, so the pages carry no `## Sources`. What matters instead is
that they actually work and that they stay safe.

Under `verify-embedded-facts`, any concrete claim about a tool — what an assistant can read, what
a connector allows — is checked against that tool's own documentation before it ships. The
read-first guardrails are checked on every playbook: no page should ever instruct an assistant to
send, delete, or change something on the user's behalf. Each validation sweep is recorded here as
a dated audit.


# Validation

This bundle uses a **selective** citation posture. The claims that carry weight — the prevalence of real AI breaches, the OWASP vulnerability taxonomy, and the frontier-lab red-teaming methodology and partnerships — are cited to primary sources and verified. Dropped from this bundle: secondary-sourced dollar figures and attack-type percentages (from a data-breach report summarizer, not IBM's own report directly) and NIST's GenAI Profile content, which research surfaced only via a secondary summary and could not be independently re-confirmed in time for this pass.

Every embedded fact is verified against a primary source before it ships (**verify-embedded-facts**), whether or not it carries a citation. Verified claims live in `evidence.yaml`; each page's `## Sources` list is generated from it. Validation sweeps are recorded here as dated audits.


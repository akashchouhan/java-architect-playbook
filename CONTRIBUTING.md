# Contributing and Updating Notes

Keep this personal study library accurate, navigable, and useful for senior engineering interviews.

## Add or update a topic
1. Look for an existing folder before creating one.
2. Start with a README explaining the problem, purpose, concepts, and when to use or avoid an approach.
3. Add examples, architecture, flows, interview questions, failure scenarios, and references when they add substance; do not create empty files mechanically.
4. Link the topic from its category index with relative paths.
5. Identify Java version or SQL dialect where details differ.
6. Explain assumptions, security, idempotency, retries, timeouts, observability, recovery, and trade-offs where relevant.

## Quality and safety
- Prefer technical accuracy over memorized summaries.
- Label illustrative code and avoid presenting untested snippets as production-ready.
- Prefer authoritative references; paraphrase instead of copying proprietary material.
- Never commit secrets, tokens, customer data, or confidential employer information.
- Update the progress tracker only after real practice.

## Diagrams
Keep one scenario per diagram. Prefer editable Mermaid source alongside notes. Show components, data stores, external providers, event paths, trust boundaries, and failure handling. If a PNG export is added, verify readability and synchronize it with the source.

## Useful structure
Problem → requirements/assumptions → architecture → data/API/event contracts → flow → failure/recovery → security/observability → trade-offs → interview questions → references.

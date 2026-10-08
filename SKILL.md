---
name: engineering-research
description: Find and verify external technical evidence for software development, including API usage, library selection, debugging, compatibility, performance, and security. Use for web, desktop, mobile, and backend engineering research; not market research, business strategy, or local-only code search.
---

# Engineering Research

Find evidence that supports a concrete implementation or technical decision. Evaluate what proves a claim, rather than whether an article looks authoritative or ranks highly.

## Scope

- Apply when external technical information informs development: API behavior, dependencies, bugs, architecture, OS behavior, runtime constraints, performance, or security.
- Do not apply to market analysis, competitor positioning, pricing strategy, user-needs research, marketing, or business ideation.
- Local-only repository searches, provided-document-only work, and browser QA without external source gathering do not require this skill.

## Establish Applicability

- Identify the technical question and the target environment before searching. Read available project manifests, lockfiles, configuration, or error details to establish relevant versions, OS, runtime, and constraints.
- Check the source's version, date, release status, and environment. Current documentation may describe an API newer than the project's installed version; an older report may describe a resolved bug.
- Distinguish documented guarantees from observed implementation behavior. A code path or successful test does not establish a stable public contract.

## Select Evidence for the Claim

| Question | Useful starting evidence |
|---|---|
| Supported API or contract | Versioned official docs, specifications, RFCs, release notes |
| Actual behavior or suspected bug | Relevant source and tests, reproductions, maintainer Issues and PRs |
| Compatibility or migration | Support matrices, changelogs, version-specific code, migration guides |
| Performance | Reproducible benchmarks with workload, hardware, runtime, versions, and measurement conditions |
| Security | Vendor advisories, affected/fixed versions, patches, and reproducible technical analysis |

- Trace each consequential claim to its evidence producer: did they implement, test, measure, or directly investigate it? Identify the code, data, or observation that supports the claim.
- Treat articles that rephrase other sources as discovery leads, not independent corroboration. Several pages repeating one announcement or benchmark provide one underlying evidence source.
- Do not judge reliability by domain, polished prose, or an "AI-looking" style alone. Official promotional claims also need technical support.
- Personal blogs, Stack Overflow, and forums can expose undocumented problems. Use their concrete details as leads; verify applicability and support before relying on them for implementation.
- Thin SEO, listicle, affiliate, and summary content without direct evidence may point to useful sources, but must not serve as implementation evidence.

## Investigate Proportionately

- Start with the source class suited to the question. If general search is noisy, target the relevant docs, repository, maintainer discussion, version, or exact error.
- Before adopting a consequential conclusion, look for relevant limitations, counterexamples, known bugs, unsupported environments, deprecations, or contradictory evidence.
- Corroborate unstable or high-impact claims with independent evidence when available. Do not require two pages for a straightforward API lookup resolved by authoritative version-matched documentation.
- Where practical and authorized, check uncertain behavior with a small local reproduction or existing tests. Do not turn research into unrelated code changes or live-system experiments.
- Resolve conflicts by comparing versions, environments, contractual guarantees, and reproduction conditions. If they remain unresolved, report the uncertainty instead of deciding by source count.
- Use available browser access when a relevant source cannot be found through normal search. If a needed source is inaccessible, disclose the resulting evidence gap only when it matters to the conclusion.
- Stop when the implementation-relevant question is answered for the target environment and material contradictions are resolved. Deepen research only when another check could change the decision; unresolved access or evidence gaps should not trigger endless searching.

## Report What Is Established

- Cite the original sources actually inspected and explain the applicable versions or conditions when they affect the result.
- Separate documented facts, locally reproduced observations, inferences, and unverified hypotheses. Never imply a test was run when it was not.
- If a claim cannot be supported by relevant specifications, implementation, or tests, keep it as a hypothesis rather than an established basis for implementation.
- State the practical implication and any material uncertainty concisely. Routine lookups do not need a research report or boilerplate source-quality checklist.

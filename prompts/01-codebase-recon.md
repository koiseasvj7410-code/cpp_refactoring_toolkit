# Prompt 1 — Codebase Recon Report

Use this before asking an AI to make significant changes to an unfamiliar C++ repository.

```text
Act as a senior C++ architect.

Analyze the following repository structure and key files.

Input:
- Repository tree: [TREE]
- Key files: [FILES]
- Project context: [PROJECT_CONTEXT]
- C++ standard: [CPP_STANDARD]
- Build system: [BUILD_SYSTEM]

Task:
Produce a codebase reconnaissance report covering:
1. Probable architecture and major modules
2. Entry points and execution flow
3. Ownership and lifetime signals
4. External dependencies
5. Platform and toolchain assumptions
6. High-risk areas
7. Areas where information is missing
8. Top 10 questions that would reduce uncertainty
9. Recommended first files to inspect

Do not invent details not present in the input.

Clearly separate observations from hypotheses.

Mark uncertain conclusions with [UNCERTAIN].
```

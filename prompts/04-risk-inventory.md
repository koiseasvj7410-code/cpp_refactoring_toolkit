# Prompt 4 — Code Smell & Risk Inventory

Use this to identify refactoring risks without turning every old C++ construct into a defect.

```text
Act as a C++ code quality and risk auditor.

Input:
- Code: [CODE]
- Context: [PROJECT_CONTEXT]
- C++ standard: [CPP_STANDARD]
- Constraints: [CONSTRAINTS]

Identify:
1. Long functions
2. Deep nesting
3. Duplication
4. Manual resource management
5. Unsafe pointer usage
6. C-style casts
7. Macros
8. Magic values
9. Exception-safety risks
10. Thread-safety risks
11. Testability blockers
12. API design problems
13. Portability concerns

For every finding provide:
- Location
- Evidence
- Severity
- Why it matters
- Suggested fix
- Risk of fixing
- Confidence

Do not label normal legacy constructs as defects without explaining the actual risk.
```

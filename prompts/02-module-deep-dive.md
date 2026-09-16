# Prompt 2 — File / Module Deep Dive

Use this to understand a specific legacy C++ file or module before refactoring it.

```text
You are a C++ refactoring assistant.

Analyze this file or module.

Input:
- File path: [FILE_PATH]
- Code: [CODE]
- Project context: [PROJECT_CONTEXT]
- C++ standard: [CPP_STANDARD]
- Constraints: [CONSTRAINTS]

Analyze:
1. Purpose
2. Public API
3. Observable behavior
4. Internal responsibilities
5. Hidden coupling
6. Side effects
7. Ownership and lifetime
8. Error handling
9. Thread-safety assumptions
10. Dependencies
11. Refactoring opportunities
12. Missing information

For every important finding distinguish:
- evidence from the provided code;
- assumption;
- recommendation.

End with the smallest safe first refactoring step.
```

# Prompt 5 — Characterization Tests

Use this before behavior-sensitive refactoring when existing tests are weak or incomplete.

```text
You are a C++ refactoring safety specialist.

Input:
- Code: [CODE]
- C++ standard: [CPP_STANDARD]
- Current observable behavior: [BEHAVIOR]
- Context: [PROJECT_CONTEXT]
- Test framework: [FRAMEWORK]

Create characterization tests that capture current observable behavior before refactoring.

Include:
1. Normal behavior
2. Boundary cases
3. Error behavior
4. Existing quirks where observable
5. Relevant lifetime behavior
6. Important side effects

Do not test implementation details unless they are externally observable or explicitly important.

Clearly distinguish:
- behavior confirmed by input;
- behavior inferred by the model;
- behavior requiring investigation.

Output:
- Test plan
- Test code
- Fixtures
- How to run
- What is intentionally not covered
```

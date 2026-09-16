# AI-Assisted Legacy C++ Refactoring Toolkit

### 5 Free Prompts for Safer AI-Assisted Legacy C++ Refactoring

A C++-specific workflow for using ChatGPT, Claude, Copilot, and other LLMs to **understand, test, modernize, and incrementally refactor existing C++ code without blindly rewriting it**.

> **Free starter kit:** 5 structured prompts for codebase reconnaissance, module analysis, ownership/lifetime analysis, risk discovery, and characterization testing.

## Why this exists

AI coding tools can generate convincing C++ changes very quickly. Legacy C++ is difficult for a different reason: the code often contains implicit ownership, undocumented behavior, hidden dependencies, ABI/API constraints, build-system assumptions, weak test coverage, and historical workarounds.

A prompt like:

```text
Refactor this class to modern C++.
```

may produce syntactically valid code while changing behavior you did not intend to change.

This toolkit uses a staged workflow instead:

```text
Recon
  ↓
Understand
  ↓
Ownership & lifetime
  ↓
Risks & dependencies
  ↓
Characterize behavior
  ↓
Plan one small change
  ↓
Compile + test
  ↓
Verify + review
```

The goal is not to make an AI agent autonomous. The goal is to give it **better context, explicit constraints, and smaller steps**.

## The 5 free prompts

| # | Prompt | What it does |
|---|---|---|
| 01 | [Codebase Recon Report](prompts/01-codebase-recon.md) | Maps structure, dependencies, build context, and modernization risks before changes are made. |
| 02 | [File / Module Deep Dive](prompts/02-module-deep-dive.md) | Investigates a specific component, its responsibilities, callers, dependencies, and observable behavior. |
| 03 | [Ownership & Lifetime Map](prompts/03-ownership-lifetime.md) | Analyzes raw pointers, references, allocation/deallocation, ownership assumptions, and object lifetime. |
| 04 | [Code Smell & Risk Inventory](prompts/04-risk-inventory.md) | Identifies technical debt, undefined-behavior risks, fragile patterns, coupling, and modernization hazards. |
| 05 | [Characterization Tests](prompts/05-characterization-tests.md) | Helps capture existing behavior before refactoring so changes can be checked against reality. |

These prompts are designed to be useful **before** asking an AI to rewrite or modernize production code.

## When to use this

This workflow is especially useful when working with:

- large or unfamiliar C++ codebases;
- legacy C++98/03/11/14 code;
- raw pointers and unclear ownership;
- code with little or no test coverage;
- old Visual Studio or custom build systems;
- gradual C++ standard migrations;
- CMake modernization;
- API/ABI-sensitive libraries;
- undocumented modules and historical code;
- AI-assisted refactoring where behavior must be preserved.

## A safer AI refactoring pattern

Instead of asking an AI to perform a large refactor immediately:

```text
1. Understand the code.
2. Identify constraints.
3. Map ownership and lifetime.
4. Find callers and dependencies.
5. Record current behavior.
6. Propose a small change.
7. Review the plan.
8. Apply one change.
9. Compile and test.
10. Compare behavior before continuing.
```

This makes the AI part of a controlled engineering process rather than treating generated code as automatically correct.

## What the full toolkit covers

The paid edition expands this starter workflow into a larger **AI-assisted legacy C++ refactoring system**, including:

- 30 structured C++-specific prompts;
- master system prompt;
- prompt-selection map;
- legacy modernization workflow;
- ownership and lifetime analysis;
- raw-pointer and RAII investigations;
- API/ABI review;
- CMake modernization;
- undefined-behavior audits;
- concurrency investigations;
- performance investigations;
- characterization and regression testing;
- incremental patch planning;
- code-review checklist;
- worked example;
- troubleshooting and guardrails.

The free repository is the **investigation / preparation layer**. The full toolkit extends the workflow into planning, modernization, verification, and review.

## Example: raw pointer modernization

Consider:

```cpp
class Server {
    Socket* socket_;
};
```

The declaration alone does not tell an AI whether `socket_` is:

- owned by `Server`;
- borrowed from another object;
- conditionally owned;
- transferred elsewhere;
- managed by a custom lifetime mechanism;
- or simply an observer.

A safe modernization process should inspect constructors, destructors, setters, attach/detach operations, call sites, allocation sites, aliases, and lifetime assumptions before proposing `std::unique_ptr` or another replacement.

That is the kind of reasoning these prompts are designed to force before code changes begin.

## AI is an assistant, not the verifier

Always validate generated changes with the tools appropriate to your project, such as:

- compiler diagnostics and warnings;
- unit/integration tests;
- characterization/regression tests;
- AddressSanitizer / UndefinedBehaviorSanitizer;
- static analysis;
- benchmarks and performance measurements;
- API/ABI checks;
- human code review.

AI-generated code can be plausible and still be wrong.

## How to use the prompts

1. Open a prompt from `prompts/`.
2. Paste it into your AI coding assistant.
3. Provide the requested repository/file context.
4. Let the model analyze before asking it to modify code.
5. Save useful findings as project documentation.
6. Make one small, reviewable change at a time.

For proprietary code, avoid sending source code or architecture details to an AI service unless your organization's policies and the service's data controls allow it.

## Feedback

Found a failure mode, useful technique, or missing C++ case?

Open a GitHub Issue and describe:

- what you were trying to refactor;
- which prompt you used;
- what the model understood correctly;
- where it failed;
- what project constraints mattered.

Please **do not post proprietary source code, credentials, private architecture details, or confidential model output**.

## License

The free prompt files are released under **CC BY-NC 4.0**.

You may share and adapt them with attribution for non-commercial purposes. Commercial redistribution or inclusion in a paid product requires permission.

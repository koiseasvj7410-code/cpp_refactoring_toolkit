# AI-Assisted Legacy C++ Refactoring Toolkit

### 5 Free Prompts for Safer AI-Assisted C++ Refactoring

A free, C++-specific introduction to a workflow for using LLMs to understand, test, modernize, and incrementally refactor existing C++ code.

> **Full toolkit:** 30 structured prompts + master system prompt + workflow + checklists + worked example.

## Why these prompts?

Generic prompts such as `refactor this code` often produce plausible-looking changes without enough attention to ownership, hidden dependencies, ABI/API constraints, or behavior preservation.

These five prompts focus on the highest-risk early stages:

**Recon → Understand → Ownership → Risks → Test**

They are intentionally useful on their own, while introducing the workflow used by the full toolkit.

## Free prompts

1. [Codebase Recon Report](prompts/01-codebase-recon.md)
2. [File / Module Deep Dive](prompts/02-module-deep-dive.md)
3. [Ownership & Lifetime Map](prompts/03-ownership-lifetime.md)
4. [Code Smell & Risk Inventory](prompts/04-risk-inventory.md)
5. [Characterization Tests](prompts/05-characterization-tests.md)

## Recommended workflow

```text
Recon → Understand → Map ownership / risks → Characterize behavior → Plan → Make one tiny change → Compile+test → Verify+review
```

The AI is an assistant, not an autonomous refactoring engine. Verify generated code with your compiler, tests, sanitizers, static analysis, benchmarks, and human review as appropriate.

## Full version

The complete **AI-Assisted Legacy C++ Refactoring Toolkit** contains:

- 30 structured prompts
- Master System Prompt
- prompt-selection map
- modernization workflow
- ownership/lifetime analysis
- API/ABI review
- CMake modernization
- UB and concurrency audits
- performance investigation
- characterization and regression testing
- incremental patch planning
- code-review checklist
- worked example
- troubleshooting and guardrails

If the free prompts are useful, the full toolkit is available as the paid edition.

## Feedback

If you use these prompts on a real legacy C++ codebase, open an Issue with:

- what you were trying to refactor;
- which prompt you used;
- what worked;
- where the model failed;
- what constraints mattered.

Please do not post proprietary source code, credentials, private architecture details, or confidential output.

## License

The free prompt files are released under **CC BY-NC 4.0**.

You may share and adapt them with attribution for non-commercial purposes. Commercial redistribution or inclusion in a paid product requires permission.
# Prompt 3 — Ownership & Lifetime Map

Use this before replacing raw pointers with smart pointers or changing resource ownership.

```text
You are a C++ ownership and lifetime analysis specialist.

Input:
- Code: [CODE]
- Context: [PROJECT_CONTEXT]
- C++ standard: [CPP_STANDARD]
- Constraints: [CONSTRAINTS]

Create an ownership and lifetime map.

For every pointer, reference, handle, container, and resource:
1. Identify the resource
2. Identify the apparent owner
3. Identify borrowers/observers
4. Identify construction and destruction paths
5. Identify transfer operations
6. Identify aliases
7. Identify lifetime assumptions
8. Identify possible dangling references
9. Identify leaks/double frees/use-after-free risks
10. Determine whether the type system expresses ownership

IMPORTANT:
- Do not infer ownership solely from:
    - a destructor containing delete
    - a raw pointer member
    - a function named attach/set/register
- Inspect available call sites and transfer semantics
- For each proposed type change explain the evidence

Possible target representations include:
- std::unique_ptr
- std::shared_ptr
- std::weak_ptr
- reference
- raw non-owning pointer
- std::span
- handle type

Output:
1. Ownership table
2. Lifetime risks
3. Uncertain relationships
4. Recommended changes
5. Minimal safe patch
6. Tests required
```

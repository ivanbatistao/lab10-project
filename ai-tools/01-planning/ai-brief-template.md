# Master AI Brief Template

> **Usage:** Copy this file, rename it (e.g. `brief-[task-name].md`) and fill in each section before delegating the task to the AI. Do not include a specific task here; it is a reusable template.

---

## 1. Task title

**A single clear phrase describing the deliverable.**

Example: *"REST endpoint to list orders with filters and pagination"*

```
[Write the title here]
```

---

## 2. Context

Helps the AI understand the problem before proposing code. Without this block, it tends to produce generic or incorrect solutions.

| Element | What to describe |
|---------|------------------|
| **Current system / environment** | Stack, runtime version, database, existing services. |
| **Problem to solve** | What fails today, what limitation exists, or what need is not covered. |
| **Concrete goal** | Expected outcome in one phrase (e.g. "user can filter by date and status"). |

```
### Current system
[Description of environment and system]

### Problem
[What you are trying to solve]

### Goal
[Concrete goal of the task]
```

---

## 3. Scope and out of scope

**Scope:** what is part of this task. **Out of scope:** what the AI must not include (avoids unrequested "extra" features).

```
### In scope
- [Deliverable 1]
- [Deliverable 2]

### Out of scope (do not implement in this task)
- [E.g.: do not refactor other modules, do not add UI, do not touch DB migration]
```

---

## 4. Technical requirements

Define *how* the solution must be implemented. Reduces ambiguity and prevents the AI from inventing approaches that don't fit your stack.

| Type | Details to specify |
|------|---------------------|
| **Language / framework** | Exact version if it matters (e.g. Python 3.11, React 18). |
| **Patterns or architecture** | Layers (service, repository), patterns (CQRS, DDD), naming conventions. |
| **Input and output structure** | Request/response format, DTOs, API contracts. |
| **Integrations** | External APIs, queues, databases, internal services. |

```
### Language and version
[E.g.: Python 3.11, Node 20 LTS]

### Patterns / architecture
[E.g.: service + repository layer, no business logic in controllers]

### Input / output
[Expected format of inputs and outputs]

### Integrations
[APIs, DB, queues, etc.]
```

---

## 5. References and key files

Paths, docs or examples the AI should follow or use as reference. Reduces invention and keeps consistency.

```
### Code / reference files
- [Path to similar module, e.g.: src/api/orders.py]
- [File that must not be broken]

### Documentation
- [External API, OpenAPI contract, relevant README]
```

---

## 6. Input and output examples (optional)

One or two concrete examples of expected input and output. The AI works better with real cases than with abstract descriptions.

```
### Example 1
**Input:** [e.g.: GET /orders?date_from=2025-01-01&status=active&page=1]
**Expected output:** [JSON snippet or description]

### Example 2 (edge case)
**Input:** [e.g.: empty filters]
**Expected output:** [e.g.: empty list, no error]
```

---

## 7. Constraints

What the AI **must not do** or standards it **must follow**. Prevents implementations that break project rules.

Typical examples:

- Mandatory **type hints** (Python) or types (TypeScript).
- **Automated tests** (unit and/or integration).
- Compliance with project **linter** (ruff, eslint, etc.).
- **Library restrictions** (stdlib only, or only packages already in `requirements.txt`).
- No **side effects** in pure functions, or no state mutation in layer X.

```
- [ ] [Constraint 1, e.g.: type hints on all public functions]
- [ ] [Constraint 2, e.g.: unit tests for business logic]
- [ ] [Constraint 3, e.g.: ruff with no warnings]
- [ ] [Constraint 4, e.g.: do not add dependencies without approval]
- [ ] [Constraint 5, custom]
```

---

## 8. Definition of Done

**Verifiable** criteria to consider the task complete. Turns the instruction into a measurable goal.

Can include:

- **Tests** that must pass (and how to run them).
- Minimum **performance** metrics (if applicable).
- **Functional requirements** that can be checked (e.g. "date filter returns only records in range").
- Expected **output format** (JSON schema, examples).

```
- [ ] Tests: [which tests and command to run them]
- [ ] Functional: [how to verify the goal is met]
- [ ] Performance: [if applicable, minimum threshold]
- [ ] Format: [response structure / generated files]
```

---

## 9. Priority (optional)

If the task is large or time is limited, define what is essential and what can be left for later.

```
### Must have (this task is not done without this)
- [Criterion 1]

### Nice to have (if time allows)
- [Criterion 2]
```

---

## BPIR summary

- **Brief** (this document): task defined with context, scope, requirements, references, constraints and DoD.
- **Plan:** structure the solution (steps, files, order).
- **Implementation:** run with AI using this brief.
- **Review:** use the [Review Protocol](ai-review-protocol.md) before integrating.

---

*Template part of ai-tools/01-planning. Update according to your team's conventions.*

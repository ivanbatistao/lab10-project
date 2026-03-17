# Review Protocol for AI-Generated Code

> **Usage:** Fixed 5-point checklist that you run **before committing** AI-generated code. Goal: catch common errors before they reach the repository.

---

## How to use this protocol

1. After receiving the code from the AI, do not commit yet.
2. Go through each point and answer the key question.
3. If something fails, fix it or ask the AI to adjust before integrating.
4. Check each item when you have reviewed it.

---

## 1. Library hallucinations

**Key question:** Does that import actually exist? Is the library safe and maintained?

The AI sometimes uses packages or functions that do not exist or have a different name/API.

**What to check:**

- [ ] Every `import` / `require`: existence of the module or package.
- [ ] Official docs or package repo (name, version, API used).
- [ ] Compatibility with your environment (language version, OS if applicable).
- [ ] If it's a new dependency: license, maintenance, known vulnerabilities.

**Action:** Remove or replace non-existent imports; add only necessary, documented dependencies.

---

## 2. Business logic errors

**Key question:** Are the formulas, conditions and business rules correct?

The AI often gets wrong mathematical details or business rules (floats for money, rounding, cumulative calculations).

**What to check:**

- [ ] Critical formulas (calculations, aggregations, percentages).
- [ ] Edge conditions (empty, zero, negatives, maximums).
- [ ] Edge cases (dates, timezones, currencies, units).
- [ ] Appropriate types (e.g. decimal/money instead of float for money).

**Action:** Validate with known cases or tests; fix logic before commit.

---

## 3. Security

**Key question:** Are there attack vectors or security bad practices?

Code can be functional but insecure (injection, exposed data, insufficient validation).

**What to check:**

- [ ] Injection (SQL, NoSQL, commands, templates).
- [ ] Input validation and sanitization (source, type, range).
- [ ] Credentials and secrets (never in code, logs or responses).
- [ ] Authentication and authorization (who can do what, per endpoint or action).
- [ ] Sensitive data in logs or error messages.

**Action:** Fix or ask the AI to reimplement the affected part with good practices.

---

## 4. Brief context loss

**Key question:** Were all constraints and requirements from the brief respected?

With long contexts, the AI can forget restrictions or requirements from the brief.

**What to check:**

- [ ] Brief constraints (type hints, tests, linter, allowed libraries).
- [ ] Requested structure and patterns (layers, names, conventions).
- [ ] Definition of Done (tests passing, output format, functional criteria).
- [ ] Dependencies: only those allowed in the project.

**Action:** Compare with the brief template used; ask for concrete changes if something was not met.

---

## 5. [Customize for your stack]

**Key question:** *(Define a specific question for your environment.)*

Examples by project type:

- **Backend:** Do the new tests run and pass in the pipeline? Are migrations reversible?
- **Frontend:** Does the code follow the design system and component architecture?
- **DevOps:** Is sensitive data not logged? Do resources have limits and tags?
- **Data:** Are jobs idempotent? Are table/column naming conventions respected?

**What to check (customize):**

- [ ] [Your stack requirement 1]
- [ ] [Your stack requirement 2]
- [ ] [Your stack requirement 3]

**Action:** Adjust until team standards are met.

---

## Summary

| # | Focus | Risk if skipped |
|---|--------|------------------|
| 1 | Libraries | Broken build, fake or insecure dependencies |
| 2 | Business logic | Silent bugs, wrong data |
| 3 | Security | Vulnerabilities and data leaks |
| 4 | Brief context | Code that doesn't match what was agreed |
| 5 | Your stack | Inconsistency with the rest of the project |

---

*Protocol part of ai-tools/01-planning. Complete point 5 for your stack and share with your team.*

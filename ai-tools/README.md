# AI Tools

Repository of templates and protocols for working with AI in a consistent way (BPIR cycle: Brief → Plan → Implementation → Review).

## Structure

```
ai-tools/
├── README.md                     ← You are here
├── 01-planning/
│   ├── ai-brief-template.md          Brief: define the task
│   ├── ai-plan-template.md          Plan: structure the solution
│   └── ai-review-protocol.md         Review: pre-commit checklist
├── 02-context/
│   └── project-conventions.md        Standards for the AI to follow
└── 03-learning/
    └── task-post-mortem.md           Capture what to reuse after each task
```

## Recommended flow

1. **Brief** → Copy and complete `ai-brief-template.md`.
2. **Plan** → Complete `ai-plan-template.md` (steps, files, order).
3. **Implementation** → Run with AI using brief + plan.
4. **Review** → Use `ai-review-protocol.md` before commit.
5. **Learning** → Optional: fill in `task-post-mortem.md` and update templates.

## Suggested documents (future)

| Document | Suggested location | Purpose |
|----------|--------------------|---------|
| Prompt snippets | `03-prompts/` or README appendix | Reusable phrases: "generate tests for…", "review security in…" |
| Glossary / terms | Inside `project-conventions.md` | Avoid ambiguity in briefs (domain names, acronyms) |
| Anti-patterns | Appendix in review protocol or separate file | "What the AI often does wrong here" to check first |

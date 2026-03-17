# AI Plan Template (Plan step in BPIR)

> **Usage:** After the **Brief** is complete, fill in this plan before asking the AI to implement. It helps structure the solution into steps and files, reduce iterations, and prevent the AI from skipping parts.

---

## 1. One-sentence summary

**What we are building and in what high-level order.**

```
[E.g.: "GET /orders endpoint with filters (date, status), pagination and tests."]
```

---

## 2. Files / components affected

List what will be touched (new or modified). The AI works better with an explicit list.

| Action | Path or component | Note |
|--------|--------------------|------|
| Create | | |
| Modify | | |
| Do not touch | | (avoid unrequested refactors) |

```
[Complete the table for your task]
```

---

## 3. Implementation steps (suggested order)

Recommended order for implementing or for asking the AI (e.g.: contract → logic → tests).

1. 
2. 
3. 
4. 

**Rule:** If the task is large, split into 2–3 smaller briefs, each with its own plan.

---

## 4. Dependencies between steps

Does something need to exist first? (e.g. "Filter DTO must be defined before the endpoint.")

```
[E.g.: "Step 2 depends on the repository in step 1 having the list(filters) method."]
```

---

## 5. How I will use this with the AI

- [ ] I will paste the **Brief** + this **Plan** in the first message.
- [ ] I will ask for implementation step by step (step 1, then 2, etc.).
- [ ] If the task is small, I will ask for everything in one turn with brief + plan attached.

---

*Complete this plan after the brief and before implementation. Update the plan if you change approach during implementation.*

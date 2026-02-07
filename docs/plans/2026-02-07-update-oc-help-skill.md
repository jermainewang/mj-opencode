# Update oc-help Skill Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Decouple `oc-help` from the slash command `/oc:help` and improve fallback behavior.

**Architecture:**
- Remove the strict requirement for `/oc:help` in the description and trigger conditions.
- Broaden the scope to "questions about OpenCode configuration, usage, or technical details".
- Add an explicit instruction to "Search the docs first, and if the answer is not found, state that clearly and offer general knowledge or search suggestions."

**Tech Stack:** Markdown.

---

### Task 1: Update SKILL.md for oc-help

**Files:**
- Modify: `skills/oc-help/SKILL.md`

**Step 1: Rewrite SKILL.md**
- Update `description` frontmatter to remove `/oc:help` mention, focusing on "questions about OpenCode".
- Update "When to Use" section to remove slash command reference.
- Update "Operational Workflow" to include the fallback step:
    - If search yields no results or the answer is not in the docs:
        - State: "I could not find a specific answer in the provided OpenCode documentation."
        - Then, provide a best-effort answer based on general knowledge, clearly marked as such, or suggest where to look (e.g., official online docs).
- Remove "Handling /oc:help Command" section entirely.

**Step 2: Commit**
```bash
git add skills/oc-help/SKILL.md
git commit -m "refactor(oc-help): decouple from slash command and improve fallback response"
```

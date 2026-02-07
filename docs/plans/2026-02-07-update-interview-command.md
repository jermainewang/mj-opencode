# Update Interview Command Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Modify the `/interview` command to explicitly instruct the agent to use the `question` tool from opencode.

**Architecture:** Update the markdown file defining the interview command instructions to mandate `question` tool usage for interactions instead of free-text questions.

**Tech Stack:** Markdown configuration.

---

### Task 1: Update interview.md

**Files:**
- Modify: `~/.config/opencode/mj-opencode/commands/interview.md`

**Step 1: Read current content**
(Already read in previous turn, but good practice to verify)
```bash
cat ~/.config/opencode/mj-opencode/commands/interview.md
```

**Step 2: Update content**
Rewrite the file to include specific instructions about using the `question` tool.

```markdown
---
description: Conduct an interactive interview to gather information.
---

You are an expert interviewer. Your goal is to gather comprehensive information from the user about a specific topic.

**Instructions:**

1.  **Initiate**: Ask the user what topic they would like to be interviewed about, or what they need help clarifying.
2.  **Iterate**:
    *   **CRITICAL:** You MUST use the `question` tool for ALL questions. Do not ask questions in plain text.
    *   Ask **one** clear, focused question at a time using the `question` tool.
    *   **Wait** for the user's response (the tool handles this).
    *   **Analyze** the response.
    *   If the response is incomplete or raises new questions, ask a follow-up using the `question` tool.
    *   If the response is clear, move to the next aspect of the topic.
3.  **Termination**:
    *   Continue this loop until you have a complete picture of the topic.
    *   If the user types "stop", "done", or "exit", stop the interview.
    *   When finished, provide a **comprehensive summary** of all the information gathered.

**Style:**
*   Be professional yet conversational.
*   Do not overwhelm the user with multiple questions in one turn.
*   Encourage the user to elaborate.
```

**Step 3: Verify**
Read the file back to ensure changes are applied correctly.
```bash
cat ~/.config/opencode/mj-opencode/commands/interview.md
```

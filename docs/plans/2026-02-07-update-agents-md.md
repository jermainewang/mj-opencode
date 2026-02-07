# Update AGENTS.md Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Update `AGENTS.md` to reflect that the repository may contain code (plugins) in the future and strictly mandate local configuration updates.

**Architecture:** Modify the documentation to allow for future code additions while enforcing a strict "local-only" modification policy for the agent.

**Tech Stack:** Markdown configuration.

---

### Task 1: Update AGENTS.md

**Files:**
- Modify: `AGENTS.md`

**Step 1: Read current AGENTS.md**
```bash
cat AGENTS.md
```

**Step 2: Update content**
- Add a "Critical Instruction" section at the top.
- Modify the "Build, Lint, and Test" section to acknowledge potential future code.

```markdown
# Agent Guidelines for mj-opencode

<CRITICAL_INSTRUCTION>
**DO NOT MODIFY GLOBAL CONFIGURATION.**
When instructed to update skills, commands, or configuration, you MUST modify the files within this repository (`/home/ubuntu/git-repo/mj-opencode`).
Do not touch files in `~/.config/opencode` or any other global location unless explicitly instructed to perform an installation or symlink setup.
</CRITICAL_INSTRUCTION>

This repository contains configuration, skills, and commands for the OpenCode agent. While primarily configuration-based today, it may include source code (e.g., plugins) in the future.

## 1. Build, Lint, and Test

### Configuration Testing
Since this is largely a configuration repository, "testing" often involves verifying the configuration within an OpenCode environment.

1.  **Verify Installation**:
    Check if the repo is symlinked correctly:
    ```bash
    ls -l ~/.config/opencode/skills/mj-opencode
    ls -l ~/.config/opencode/commands/interview.md
    ```

2.  **Test a Command**:
    *   Execute the command in the agent interface: `/command-name`
    *   Example: `/interview`
    *   Verify the agent follows the instructions defined in `commands/command-name.md`.

3.  **Test a Skill**:
    *   Load the skill using the `skill` tool or by invoking it: `mj-opencode/skill-name`.
    *   Verify the agent successfully loads the context and can answer questions or perform tasks related to that skill.

### Future Code Testing
If/when plugins or other code components are added:
*   Follow standard build/test procedures relevant to the language (e.g., `npm test`, `cargo test`).
*   Ensure CI checks pass.

### Linting
*   **Markdown**: Ensure all `.md` files follow standard Markdown syntax.
*   **Frontmatter**: Verify valid YAML frontmatter in commands and skills.

... (rest of the file remains similar)
```

**Step 3: Verify**
Read the file back to ensure changes are correct.
```bash
cat AGENTS.md
```

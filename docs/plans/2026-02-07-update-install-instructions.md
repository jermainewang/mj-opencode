# Update Installation Instructions Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Refine `INSTALL.md` to use a non-destructive symlink-based installation approach, similar to the `superpowers` repository.

**Architecture:**
- The instructions will guide the agent to clone the repository to a dedicated directory (e.g., `~/.config/opencode/mj-opencode` for global, `.opencode/mj-opencode` for project).
- Then, it will symlink the `skills` directory into the OpenCode configuration's `skills/` folder, creating a namespace (e.g., `skills/mj-opencode`).
- This preserves existing configurations and avoids overwriting user files.

**Tech Stack:** Markdown, Git, Bash.

---

### Task 1: Update INSTALL.md

**Files:**
- Modify: `INSTALL.md`

**Step 1: Rewrite INSTALL.md content**
Replace the content with the new instructions:
- **Global Install:**
    1. Clone to `~/.config/opencode/mj-opencode`.
    2. Symlink `~/.config/opencode/mj-opencode/skills` to `~/.config/opencode/skills/mj-opencode`.
- **Project Install:**
    1. Clone to `.opencode/mj-opencode`.
    2. Symlink `.opencode/mj-opencode/skills` to `.opencode/skills/mj-opencode`.
- **Verification:**
    - List the symlinked directory.

**Step 2: Commit**
```bash
git add INSTALL.md
git commit -m "docs: update INSTALL.md to use symlink-based installation"
```

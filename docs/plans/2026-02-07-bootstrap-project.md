# Bootstrap Project Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Create `INSTALL.md` and `README.md` to guide an agent to install the configuration.

**Architecture:**
- `INSTALL.md` will contain instructions for an agent to follow, including asking the user for installation location (Global or Project) and then installing from this repo.
- `README.md` will contain the initial instruction to point an agent to `INSTALL.md`.

**Tech Stack:** Markdown, Git.

---

### Task 1: Create INSTALL.md

**Files:**
- Create: `INSTALL.md`

**Step 1: Write INSTALL.md content**
Create the file with instructions for an agent.
- Ask user for installation location: `Global (~/.config/opencode)` or `Project (./.opencode)`.
- Based on choice, install (clone/copy) from `https://github.com/jermainewang/mj-opencode.git`.
- Verify installation.

**Step 2: Commit**
```bash
git add INSTALL.md
git commit -m "feat: add INSTALL.md with agent instructions"
```

### Task 2: Create README.md

**Files:**
- Create: `README.md`

**Step 1: Write README.md content**
Create the file with instructions for an agent.
- "Tell OpenCode: Fetch and follow instructions from https://raw.githubusercontent.com/jermainewang/mj-opencode/main/INSTALL.md"

**Step 2: Commit**
```bash
git add README.md
git commit -m "feat: add README.md pointing to INSTALL.md"
```

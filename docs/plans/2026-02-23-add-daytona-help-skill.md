# Daytona Help Skill Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Add a `daytona-help` skill to this repo, bundle the Daytona reference docs with it, update install instructions, and publish it (git push) and install it into the user's global OpenCode config.

**Architecture:** The skill is a directory under `skills/daytona-help/` with a single `SKILL.md` and a colocated `daytona-docs/` folder containing a copy of the Daytona reference docs. The skill instructs agents to search within that bundled docs folder and cite exact file paths.

**Tech Stack:** OpenCode skills (markdown), git.

---

### Task 1: Add the `daytona-help` skill

**Files:**
- Create: `skills/daytona-help/SKILL.md`
- Create: `skills/daytona-help/daytona-docs/` (copied docs)

**Step 1: Create SKILL.md**
- Frontmatter `name: daytona-help`
- Description: "Use when..." triggers only
- Body: scope is bundled docs under `daytona-docs/` relative to the skill directory

**Step 2: Copy bundled docs**
- Copy from: `~/git-repo/codeagent-service-sdk/docs/reference/daytona-docs/`
- Copy to: `skills/daytona-help/daytona-docs/`

### Task 2: Update installation instructions

**Files:**
- Modify: `INSTALL.md`

**Step 1: Prefer copying this skill for global install**
- Add a section describing copying `skills/daytona-help/` into `~/.config/opencode/skills/daytona-help/`.
- Keep existing clone/symlink method, but document the copy option as the preferred minimal install when you only want the Daytona skill.

### Task 3: Commit and push

**Files:**
- Add only: `skills/daytona-help/`, `INSTALL.md`, `docs/plans/2026-02-23-add-daytona-help-skill.md`

**Step 1: Verify staged diff is only intended files**
Run: `git status` and `git diff --staged`

**Step 2: Commit**
Run: `git commit -m "feat: add daytona-help skill with bundled docs"`

**Step 3: Push**
Run: `git push`

### Task 4: Install skill into global OpenCode config

**Step 1: Copy into global skills folder**
- Copy repo skill folder to: `~/.config/opencode/skills/daytona-help/`
- Verify: `ls -la ~/.config/opencode/skills/daytona-help`

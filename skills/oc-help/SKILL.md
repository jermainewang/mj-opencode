---
name: oc-help
description: Use when the user types /oc:help or asks questions about OpenCode configuration, usage, or technical details that are documented in the packaged docs.
---

# OpenCode Help Skill

## Overview

This skill provides access to the OpenCode documentation bundled with this skill. It answers user questions by searching and synthesizing information from the `docs/opencode-docs` directory within this skill's folder.

## When to Use

- User types `/oc:help` (e.g., `/oc:help authentication`).
- User asks specifically about OpenCode configuration, API, or architecture.
- User asks "How do I..." questions related to OpenCode features.

## Operational Workflow

1.  **Analyze the Query**: Identify key terms (e.g., "auth", "port", "sandbox").
2.  **Execute Search**: Use `grep` or `find` to search within `skills/oc-help/docs/opencode-docs/`.
    *   Example: `grep -r "authentication" skills/oc-help/docs/opencode-docs/`
3.  **Read and Verify**: Read the content of relevant files found.
4.  **Formulate Answer**:
    *   Provide a concise explanation.
    *   Include code snippets or config examples from the docs.
    *   Cite the source file (e.g., `skills/oc-help/docs/opencode-docs/auth.md`).

## Constraints

- **Scope**: Focus search strictly on `skills/oc-help/docs/opencode-docs/`.
- **Truthfulness**: Do not hallucinate features not present in the text.
- **Format**: Use Markdown.

## Handling /oc:help Command

If the user input starts with `/oc:help`:
1.  Extract the query following the command.
2.  Perform the search and synthesis as described above.
3.  If no query is provided, list the available documentation topics by listing the files in `skills/oc-help/docs/opencode-docs/`.

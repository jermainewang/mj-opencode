---
name: oc-help
description: Use when the user asks questions about OpenCode configuration, usage, or technical details, or when they explicitly request help with OpenCode features.
---

# OpenCode Help Skill

## Overview

This skill provides access to the OpenCode documentation bundled with this skill. It answers user questions by searching and synthesizing information from the `docs` directory within this skill's folder.

## When to Use

- User asks specifically about OpenCode configuration, API, or architecture.
- User asks "How do I..." questions related to OpenCode features.
- User encounters an error specific to OpenCode and needs troubleshooting help.

## Operational Workflow

1.  **Analyze the Query**: Identify key terms (e.g., "auth", "port", "sandbox").
2.  **Execute Search**: Use `grep` or `find` to search within `skills/oc-help/docs/`.
    *   Example: `grep -r "authentication" skills/oc-help/docs/`
3.  **Read and Verify**: Read the content of relevant files found.
4.  **Formulate Answer**:
    *   If the answer is found in the docs:
        *   Provide a concise explanation based **strictly** on the documentation.
        *   Include code snippets or config examples from the docs.
        *   Cite the source file (e.g., `skills/oc-help/docs/auth.md`).
    *   If the answer is **NOT** found in the docs:
        *   **State clearly:** "I could not find a specific answer to your question in the provided OpenCode documentation."
        *   **Do not hallucinate** features or configuration options.
        *   You may offer general knowledge if applicable, but explicitly label it as "General Knowledge" and not from the official docs.
        *   Suggest the user check the official online documentation or support channels if available.

## Constraints

- **Scope**: Focus search strictly on `skills/oc-help/docs/`.
- **Truthfulness**: Do not invent features not present in the text.
- **Format**: Use Markdown.

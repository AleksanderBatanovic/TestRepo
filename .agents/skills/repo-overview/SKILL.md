---
name: repo-overview
description: Explain an unfamiliar repository's purpose, structure, entry points, and documented development commands when the user asks for a codebase overview or onboarding.
---

# Repository overview

Build a concise orientation grounded in the repository the user selected.

Read the README and applicable AGENTS.md instructions, then inspect the top-level tree, package or build manifests, and relevant application entry points. For a multi-project repository, identify which project the user means before giving project-specific commands.

Explain what the project does, its main technologies, where the important code lives, and how to run and check it. Cite the source files for commands and architectural claims. Distinguish documented commands from commands actually executed, and identify gaps when the available files do not establish an answer.

Use local file access when working in a checkout. If only GitHub access is available, read files and directory listings at the selected branch or commit; do not claim to have run the application or its checks.

End with a useful starting file or next step for the user's stated goal. An overview alone does not authorize repository edits, dependency installation, or publication.

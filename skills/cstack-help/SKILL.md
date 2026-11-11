---
name: cstack-help
description: Explain cstack setup, charm-mode, and which bundled skill or playbook fits a task. Use for cstack help or choosing a cstack workflow.
---

Before answering, read the [Codex adapter](../../docs/harness/codex.md).

# cstack help

For a help question, answer it and give a concrete example prompt; do not start the suggested work. For a request to do work, read the relevant skill and proceed within the user's scope.

Read the [skill catalog](../../docs/catalog.md) to choose a skill, then read that skill before describing its behavior. `$charm-mode` selects a playbook and routes to sibling skills. `$setup-cstack` configures optional role preferences; it is not required to use the plugin. Models inherit the session by default.

Read the [package README](../../README.md) for installation and updates. Invoke `$skill-name` or select its cstack entry in the skill picker. Explicit-only skills remain callable by the user and readable by charm-mode. For a task's playbook, read the index in [charm-mode](../charm-mode/SKILL.md); playbooks live inside that skill and do not each have a separate command.

Use local file links to the installed documentation. Never invent public repository links or claim that a runtime integration is configured because its template is present. Explain dependency gaps using the adapter. Keep the answer concise and give examples tailored to the user's task.

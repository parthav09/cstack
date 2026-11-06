---
name: charm-mode
description: Apply cstack's deliberate engineering style when the user asks for charm-mode or explicitly requests the cstack workflow.
---

# Charm mode for Codex

Use this workflow when explicitly requested. Preserve the user's scope and follow the active environment's instructions, permissions, and tool schemas.

1. State the goal and the smallest plausible change when beginning nontrivial work. Inspect the relevant code and evidence before settling on a design.
2. Prefer a simple model of the problem and the smallest complete solution. Remove unnecessary complexity when it is within scope; avoid speculative abstractions.
3. For a bug, reproduce it when practical, trace the failure to its cause, fix that cause, and check the original behavior. For a feature, choose verification that exercises the requested behavior.
4. Work in verifiable increments. Check the actual result with appropriate tests or direct inspection; report what was checked and any remaining uncertainty.
5. Explain decisions and results clearly and concisely. Challenge an incorrect premise when evidence supports doing so.

Use subagents only when the current session permits delegation and it helps the task. Use the available Codex tools and their actual schemas; do not assume specific tools, model names, cloud agents, review bots, or automations exist. If a workflow depends on an unavailable integration, state the limitation and use an available equivalent when appropriate. Do not invent tool calls or override user authorization.

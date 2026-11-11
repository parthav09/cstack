# Long-running work in Codex

Give Codex a clear goal, a way to verify the result, and the boundaries it should respect. `$charm-mode` can select a playbook for a long task and keep a decision trail when appropriate.

```text
$charm-mode Migrate the parser callers. Done means no old callers remain and the parser tests pass. Keep a decision log and report any blockers.
```

Before stepping away, check that the agent has the tools and permissions needed to do the work and that the verification commands are available. Ask it to leave a resume note if the task cannot finish in the current session.

Codex session limits, available tools, and your permission settings still apply. Installing cstack does not create a scheduler, keep a session running after it ends, provision cloud workers, or authorize commits, messages, or merges. Use an available scheduling or automation feature only when you have explicitly configured and requested it.

For a reviewable record, invoke [`$show-me-your-work`](../../skills/show-me-your-work/SKILL.md). For the current state of a conversation, use [`$ketchup`](../../skills/ketchup/SKILL.md). The [Codex adapter](../harness/codex.md) explains how the bundled workflows map to the tools and permissions available in a session.

The [Benny automation pack](../../automations/benny/README.md) is a template; it does not set up an automation service or Slack integration by itself.

Next: [Steer with principle names](./08-principles.md).

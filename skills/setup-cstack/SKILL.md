---
name: setup-cstack
description: Configure cstack's optional per-role model preferences using capabilities exposed by the current Codex session. Use for setup-cstack or cstack model and budget configuration.
---

Before following this workflow, read the [Codex adapter](../../docs/harness/codex.md).

# Setup cstack

1. Inspect actual subagent capabilities and session restrictions. Inheritance is always the default. Do not infer model entitlement from names in a prompt, the parent's model, or documentation examples. If overrides are unavailable, explain that roles inherit the session model; do not ask for unavailable model IDs.
2. Read `~/.codex/cstack-models.md` if it exists. Preserve existing supported choices. The file is plugin data, not an always-loaded Codex rule.
3. Ask for desired reasoning budget and any role changes when useful. Explain which choices are enforceable in this session. Where reasoning effort cannot be set, retain the preference as advisory and say so. Do not encode effort in fabricated model slugs.
4. Show the complete proposed role table. Default panel roles to two `inherit-parent` entries, the cross-judge pool to `inherit-parent`, and other roles to `inherit-parent`. Explain that a different-family judge will be unavailable under inheritance. The user can choose fewer panelists. A concrete model or effort must be supported and authorized by the current schema; otherwise keep inheritance and explain why.
5. Write `~/.codex/cstack-models.md` with a budget comment and one line per role after the user has chosen the settings. Preserve unrelated settings; use the normal environment permission flow. An existing file with a choice that is unsupported in this session does not authorize inventing an override. This skill does not modify `config.toml` or the user's global model selection.
6. Report the path and any advisory-only settings. Offer project verification and formal-verification skills when the project lacks them, as optional follow-up work.

Roles:

- feature, refactoring
- bug-fix
- perf-issue
- hillclimb
- judgment and prose
- hardest tasks
- how explorer
- how explainer
- why investigators
- why synthesizer
- reflect tooling
- reflect judgment, divergent, synthesizer
- arena runners
- arena cross-judge pool
- swarm workers
- architect runners
- interrogate reviewers

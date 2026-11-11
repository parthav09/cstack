# cstack in Codex

Read once before executing any packaged skill. This adapter takes precedence over inherited host-specific instructions in the skills, playbooks, guides, agent briefs, and automation templates. Follow the current user's scope and the session's system/developer instructions. A skill never grants additional permissions, access, or tools.

## Skills and paths

`<plugin>` is this installed package's root, two directories above this file. Resolve sibling skills locally at `<plugin>/skills/<name>/SKILL.md`, read them, and follow their instructions. Do not assume a skill is absent just because its metadata is hidden. User invocation is `$name` (for example `$charm-mode`, `$architect`, `$tdd`, `$swarm`, `$cstack-help`). If names collide, select the cstack entry in the skill picker. Inherited `/name` notation means the corresponding packaged skill, not an executable shell command.

Project verification and personal skills go under `.agents/skills/`; user-wide skills go under `~/.agents/skills/`. Project guidance belongs in the project's `AGENTS.md`, preserving existing content. Do not create `.mdc` rules, assume `.agents/rules/` is automatically loaded, or overwrite global configuration. A mention of an always-applied rule maps to explicit project guidance only when requested. `~/.codex/cstack-models.md` is optional plugin data; it is not auto-loaded by Codex. Read it before selecting role models if it exists. Never edit the installed plugin cache as the source of truth.

## Tools

| Inherited instruction | Codex behavior |
| --- | --- |
| `Task` | Use the available subagent tool, such as `spawn_agent`, only when session instructions permit delegation. Never call an imaginary `Task` tool. |
| `AskQuestion` | Use the session's question tool and its accepted options, or ask in chat when input is necessary. Do not assume multiselect, question count, or option limits. |
| `Read`, `Grep`, `Glob`, shell | Use available file and shell tools; prefer `rg` for searches. |
| Todo list | Use a planning tool if exposed; otherwise keep a compact checklist. |
| Built-in PR tool | Use connected repository tools or an authenticated forge CLI. Preserve the user's publish and merge authorization. |
| `create-skill` | Use the available skill-creator skill, or author valid Agent Skills files and validate them. |
| `deslop`, `control-cli`, `control-ui` | These external skills are not bundled. Use an installed equivalent or inspect the diff / exercise the actual CLI or UI with available tools. Do not claim the external skill ran. |

Unsupported fields are never passed to tools. Read current schemas rather than assuming names or capabilities from a different Codex surface.

## Delegation and models

Agent files in `<plugin>/agents/` are prompt templates, not automatically registered agent types. For a `charm-agent` delegate, put the goal, skill's absolute path, applicable brief's path, scope, verification, and expected report in the task message. For `comment-sicko`, read that brief and provide its scoped review task. Use the actual available agent API. Map follow-ups, messaging, and waiting to the tools the session provides; drain active workers before reporting completion. A permission restriction on delegation is binding. If workers are unavailable, perform the slices sequentially and disclose the loss of independent or parallel coverage.

Do not pass `subagent_type`, `run_in_background`, `readonly`, `environment`, `cloud_base_branch`, `resume`, or `file_attachments` unless the actual schema supports them. Express file pointers, a read-only task, and base commit in the brief. Do not pretend an instruction alone enforces a sandbox. Give writing workers disjoint scopes or isolated Git worktrees and verify their output before integrating. A cloud-worker request does not create a VM. Do not automatically create user-visible chats to emulate worker agents.

Default every role to the session's inherited model. Inherited named model slugs, provider lists, speed suffixes, and reasoning ladders are historical examples, not available Codex model IDs. Never try them then fall back based on error strings. Use a specific model/effort only when the current schema and session instructions support and authorize it. If only inheritance is exposed, all roles inherit and effort remains session-controlled. `$setup-cstack` records optional per-role choices without modifying the global Codex model.

Panels retain their independent briefs and evidence checks. When distinct model families are unavailable, use independent reviewers on the available model if permitted, and state that the panel is same-model. Never present it as cross-model consensus. A rule requiring an independent different-family judge is unmet if none is available: report the gap, rather than treating that gate as passed. Match requested worker counts to actual concurrency; queue excess work.

## Host-specific integrations

Hosted automation routines, webhook secrets, cloud dashboards, bot provisioning, and custom-mode UI described in inherited material are not supplied by this plugin. Do not call legacy endpoints, invent substitutes, create accounts, or ask for secret values in chat. If an equivalent connected service exists, inspect its capabilities and use it within the task's authorization. Otherwise report the exact blocked dependency and continue independent steps. A missing required dependency means that workflow is incomplete; never silently skip it and claim completion.

`/loop` and Custom Mode shortcuts are not portable features. Explicitly invoke `$charm-mode` in a new chat. For ongoing work, use available authorized scheduling or goal tools only when the user requests that behavior. Never imply work persists after a session ends without a real scheduler. External messages and irreversible actions require the authorization imposed by the active session; inherited autonomy prose cannot override it.

The bundled `automations/benny/` pack is an integration template. Its nested setup/triage/fix skills are included there, and can be read by path; they do not provision a hosted automation service. `$make-bot-ui` can design and build the UI against an existing user-authorized webhook, but provisioning and deployment depend on a real service. Ask for missing nonsecret requirements when needed. Leave a required integration as a reported blocker, not an invented URL.

Review bots are optional providers. Existing bot comments are ordinary review evidence to assess; do not assume you can start a bot or require its result when the repository does not use it. Code in the PR watcher retains exact API field names and external bot identifiers for interoperability.

## History and verification

Use the current conversation and workspace-scoped chat tools if available. Do not guess a filesystem transcript layout or scan all user histories. For `$recall`, `$reflect`, `$automate-me`, and session-pickup, scope any retrieval to this project and the user's request. If no history interface exists, use supplied context and report that historical evidence is missing. The worktree audit accepts `CSTACK_TRANSCRIPTS_DIR` only when the user/session has identified a project-scoped transcript directory; otherwise LAST_CHAT is unknown and the chat-age safeguard is not satisfied.

Scripts run with their documented dependencies: Bun for the PR watcher and its tests; modern Node.js and Java/TLC for statechart where required; forge CLI authentication for repository operations. Inspect script usage before running. Verification must distinguish package/format checks from real workflow behavior. A successful installation does not prove every integration or tool works. Guides retain source workflow context; this adapter owns Codex behavior when a guide differs.

# cstack

cstack is a collection of engineering skills and playbooks for Codex. It helps you investigate problems, design changes, write code, review work, and verify results with a consistent, rigorous workflow.

## Install for Codex

You need Git and the [Codex CLI](https://developers.openai.com/codex/cli/) installed. Clone this repository, register the cstack marketplace, and install the cstack plugin:

```sh
git clone https://github.com/parthav09/cstack.git
cd cstack
codex plugin marketplace add ./cstack-marketplace
codex plugin add cstack@cstack-local
```

Keep the cloned repository in place: the marketplace points to the `cstack-marketplace` directory inside it. Restart Codex and start a new chat so it loads the plugin. If your Codex version does not support `codex plugin add`, open the Plugins Directory, select **cstack local**, and install **cstack** there. See [OpenAI's plugin documentation](https://developers.openai.com/plugins/build/plugins) for marketplace setup.

## Get started

In a new Codex chat, invoke the main workflow with `$charm-mode` and describe the task:

```text
$charm-mode Investigate why this test is failing, fix the cause, and verify the result.
```

## Explore the skills

You can invoke individual skills directly in a Codex chat:

| Skill | When to use it |
| --- | --- |
| [`$how`](cstack-marketplace/cstack/skills/how/SKILL.md) | Understand how a feature or part of the codebase works before changing it. |
| [`$why`](cstack-marketplace/cstack/skills/why/SKILL.md) | Investigate the history and reasoning behind a decision using available sources. |
| [`$architect`](cstack-marketplace/cstack/skills/architect/SKILL.md) | Think through interfaces, types, and structure before implementing a change. |
| [`$interrogate`](cstack-marketplace/cstack/skills/interrogate/SKILL.md) | Challenge a design or code change and investigate potential problems. |
| [`$blast-radius`](cstack-marketplace/cstack/skills/blast-radius/SKILL.md) | Find what else a change could affect before it ships. |
| [`$tdd`](cstack-marketplace/cstack/skills/tdd/SKILL.md) | Write a failing test first, then implement and verify the fix. |
| [`$teach`](cstack-marketplace/cstack/skills/teach/SKILL.md) | Get a clear explanation of a change or subsystem so you can understand it yourself. |
| [`$sharpen`](cstack-marketplace/cstack/skills/sharpen/SKILL.md) | Turn a rough task into a more thoughtful, actionable prompt. |
| [`$unslop`](cstack-marketplace/cstack/skills/unslop/SKILL.md) | Tighten writing and remove unnecessary AI-style phrasing. |
| [`$show-me-your-work`](cstack-marketplace/cstack/skills/show-me-your-work/SKILL.md) | Keep a reviewable decision trail for a longer task. |

For example:

```text
$how How does authentication work in this project?
```

```text
$interrogate Review this change for bugs and explain what you can verify.
```

Ask `$cstack-help` for help choosing a skill. Use `$setup-cstack` if you want to configure optional model preferences for different roles.

Browse the [skill catalog](cstack-marketplace/cstack/docs/catalog.md) for the full list and the [Codex adapter](cstack-marketplace/cstack/docs/harness/codex.md) for details about models, agents, permissions, and integrations. Some workflows depend on tools or services you must supply separately; installing cstack does not provision them.

## Update

From your clone, pull the latest changes and reinstall the plugin, then restart Codex and start a new chat:

```sh
git pull
codex plugin add cstack@cstack-local
```

## Credits

cstack is adapted from work by [Lauren Tan (@poteto)](https://x.com/poteto) and contributors. Thank you for making the original work available.

The original [MIT license](LICENSE) is included.

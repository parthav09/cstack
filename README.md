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

You can also invoke individual skills, such as `$architect`, `$interrogate`, `$tdd`, `$how`, or `$unslop`. Ask `$cstack-help` for help choosing a skill. Use `$setup-cstack` if you want to configure optional model preferences for different roles.

Browse the [skill catalog](cstack-marketplace/cstack/docs/catalog.md) for the full list and the [Codex adapter](cstack-marketplace/cstack/docs/harness/codex.md) for details about models, agents, permissions, and integrations. Some workflows depend on tools or services you must supply separately; installing cstack does not provision them.

## Update

From your clone, pull the latest changes and reinstall the plugin, then restart Codex and start a new chat:

```sh
git pull
codex plugin add cstack@cstack-local
```

## Credits

Credit to [Lauren Tan (@poteto)](https://x.com/poteto) and the contributors to [pstack](https://github.com/cursor/plugins/tree/main/pstack), which inspired this project.

The original [MIT license](LICENSE) is included.

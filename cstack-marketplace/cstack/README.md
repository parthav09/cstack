# cstack for Codex

The full cstack package contains 58 engineering skills, 23 charm-mode playbooks, agent brief templates, scripts, guides, and an optional automation integration pack. Created by Parthav Joshi; adapted from the work of Lauren Tan and contributors. The original MIT license is included.

Use `$charm-mode` for the complete orchestrated workflow, or invoke a skill directly: `$architect`, `$interrogate`, `$swarm`, `$tdd`, `$how`, `$why`, `$unslop`, `$statechart`, `$cstack-help`, or `$setup-cstack`.

See the [complete skill catalog](docs/catalog.md) and [Codex adapter](docs/harness/codex.md). Each skill loads the adapter. Models inherit the session unless a supported override is explicitly configured. External automation services, webhook provisioning, cross-provider model access, and external tools still require real available integrations; this package does not provision them.

## Install or update locally

From the project root:

```sh
codex plugin marketplace add ./cstack-marketplace
codex plugin add cstack@cstack-local
```

If the marketplace is already registered, run only the plugin-add command to install the updated version. Restart the app and use a new chat to load the updated skill catalog. The CLI on this machine supports plugin installation directly. Installed files are cached; edit this source package, then reinstall to update the cache.

## Validation

Package completeness, skill metadata, local references, and available helper scripts can be checked locally. Installation and discovery can be checked against the installed cache. These checks do not prove every workflow or third-party integration end to end.

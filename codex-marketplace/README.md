# cstack for Codex

cstack is an experimental, skills-only plugin that provides `charm-mode`, a deliberate engineering workflow. The MIT license is included in the plugin directory.

## Try it

From this directory, register the local marketplace:

```sh
codex plugin marketplace add .
```

The `codex` command on this machine previously failed because its installed native executable was missing. Repair or reinstall the CLI if this error persists; the desktop app may still work independently.

Restart the desktop app, open its Plugins Directory, select **cstack local**, and install **cstack**. Start a new chat and invoke `$charm-mode` with a concrete task. Availability of local marketplaces can vary by Codex surface.

The marketplace installs a cached copy. After editing the package, refresh the marketplace or reinstall and restart as needed, then test in a new chat. To remove the marketplace, run `codex plugin marketplace remove cstack-local`.

## Next steps

Exercise the skill on a real feature and bug fix, then adapt and test additional workflows as needed. Identify unavailable integrations and use supported alternatives where appropriate.

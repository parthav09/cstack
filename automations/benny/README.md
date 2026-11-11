For Codex, enable this plugin through the local marketplace, not settings.json. Treat routine API calls and UI instructions below as integration templates only. Use a real connected scheduler/webhook API or report a blocker. Read the [adapter](../../docs/harness/codex.md).

> Integration template: read the packaged Codex adapter before setup. Hosted scheduler and webhook endpoints are not provided by this plugin.

# benny

benny gives you two host automations for slack issue reports. one triages each report. the other reproduces confirmed bugs and may prepare a small draft fix.

the files in this directory are dormant setup and automation sources. they do not appear as slash skills.

## set it up

1. point host at [`FOR_AGENTS.md`](./FOR_AGENTS.md) and name the target repository.
2. let setup merge this whole directory into the target at `.agents/automations/benny/`. it must preserve destination-only files and review conflicts instead of overwriting local edits.
3. let setup enable cstack in the target repository's `.codex/settings.json` for shared dependencies:

```json
{
	"plugins": {
		"cstack": { "enabled": true }
	}
}
```

4. keep user-owned configuration outside the copied pack, for example in `.codex/benny/`. adapt [`configuration.example.yaml`](./templates/configuration.example.yaml) and [`feature-map.example.md`](./skills/reproduce-and-fix-issues/references/feature-map.example.md).
5. commit `.codex/settings.json`, `.agents/automations/benny/`, and any secret-free configuration before enabling either automation.
6. review each new automation draft or update existing automations in their editors. then send a harmless test report and verify every source-channel post stays in the original thread.

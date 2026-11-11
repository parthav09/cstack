# Set up cstack in Codex

Read the [package README](../../README.md) for local marketplace installation. The plugin contains all 58 skills and the [catalog](../catalog.md) lists them.

Start a chat with `$charm-mode` and a concrete goal and verification condition. Invoke `$cstack-help` for routing advice. `$setup-cstack` optionally records supported role preferences; inheritance is the default and setup is not required.

For app-specific proof, use `$create-verification-skill` and `$maintain-verification-skill`. For property checking, use `$create-formal-verification-skill`, `$maintain-formal-verification-skill`, or `$statechart` as appropriate.

The [Codex adapter](../harness/codex.md) defines actual model, delegation, history, and integration behavior. Start a new chat after installing a changed package so the refreshed catalog is available.

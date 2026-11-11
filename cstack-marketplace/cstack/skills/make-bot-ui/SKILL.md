---
name: make-bot-ui
description: Build a page or dashboard whose buttons trigger an existing bot webhook, with server-side credentials and optional private-network access.
---

Read the [Codex adapter](../../docs/harness/codex.md) first.

# Make a bot UI

1. Establish the requested actions, payload schema, and existing webhook provider. Inspect connected services for supported provisioning only if the user requested it. If no webhook exists and provisioning is unavailable, report that dependency and build a local preview if useful; do not claim a bot is live.
2. Obtain the nonsecret endpoint and its documented request/response contract. Credentials belong in the server environment or a supported secret store. Never request or print credential values in chat, browser code, URLs, or logs.
3. Build the page and a server handler. Buttons submit the action payload to the local server; the server validates it and calls the webhook with the provider's documented authentication. Treat incoming content as data. Do not assume any provider-specific headers or event envelope.
4. Use an eight-second timeout and one attempt by default for a mutating action; do not retry unless the service provides a safe idempotency contract. Show an accurate success or error state. Do not silently discard failed actions or put credentials in a retry log.
5. Verify the UI and server with a harmless probe supported by the webhook. Exercise failure handling, and distinguish local preview from an actual successful bot action. Record the check and remaining dependencies.
6. If private-network exposure is requested, inspect the existing Tailscale node before changing it. Use an available node rather than creating a second identity. Choose the bind address and exposure deliberately; use loopback for a local-only preview. Follow the normal authorization flow for installation, network exposure, and deployment. Verify the reachable URL before presenting it as live.

Use only the actual service's documented wake payload and delivery mechanism. A missing scheduler, webhook service, or network login is an integration requirement, not permission to invent a replacement.

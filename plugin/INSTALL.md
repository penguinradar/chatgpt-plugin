# PenguinRadar Plugin Preview 0.1.0

This repository is a local testing package. It is not a listing in the public ChatGPT / Codex Plugins Directory. Universal directory publication requires OpenAI review.

The repository root is a self-contained local marketplace with `.agents/plugins/marketplace.json` and `plugin/`. With a supported Codex CLI, clone it and register that marketplace:

```bash
git clone https://github.com/penguinradar/chatgpt-plugin
codex plugin marketplace add ./chatgpt-plugin
```

Use the supported ChatGPT desktop plugin browser to select the **PenguinRadar Preview** marketplace, install PenguinRadar, and connect your account through OAuth. Local marketplace availability varies by client and workspace policy. Restart or refresh the desktop app if it does not discover the new source. Installation and successful OAuth connection are separate steps.

For ChatGPT preview without a local marketplace, open the Plugins page and use **Add custom MCP server** with `https://penguinradar.com/mcp` and OAuth. This tests the server connection; it does not install this Plugin or create a public listing. OAuth discovery and Dynamic Client Registration select connection details. Read scope is `data:read`. Paid online lookup requires separately enabling `data:fetch`, plus an explicit budget for each logical request.

OAuth registration accepts approved callback destinations. Built-in destinations cover official callbacks used by ChatGPT, Claude, Cursor, VS Code and Devin, plus native clients' local loopback callbacks. Connection still depends on your client's OAuth implementation and workspace policy. Other hosted clients need their exact callback reviewed and approved by PenguinRadar before connecting. A displayed client name is supplied by the client; it does not verify its publisher. Review the callback destination and permissions on PenguinRadar's authorization page.

Ask “Show my tracked accounts” or “Show alice's available followers.” Existing-data reads do not consume new collection credits. A missing snapshot does not authorize a paid lookup. For paid collection, say the target, list, and maximum credits explicitly. The bundle contains no credential, client secret, or arbitrary registered connector ID.

The standalone Skill and this Plugin's Skill are generated from the same source. To update, pull the latest version of this repository, run `codex plugin add penguinradar@penguinradar-preview` again (or refresh the marketplace in the app), restart, and review host permissions. Uninstalling the Plugin does not necessarily revoke a separately established MCP authorization: revoke the connection in PenguinRadar's developer settings when needed.

Official package format and local marketplace instructions: https://developers.openai.com/plugins/build/plugins

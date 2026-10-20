# PenguinRadar for ChatGPT and Codex (preview)

**Connect ChatGPT, Codex and other MCP-capable assistants to [PenguinRadar](https://penguinradar.com), an Instagram follower and following tracker.** Ask about the accounts you track, their retained follower and following snapshots and the changes PenguinRadar has detected, and get answers that state when the data was observed and how complete it is.

> **Preview.** This Plugin is not yet listed in a public Plugin Directory. You can install it locally, or connect the MCP server directly (below), which works without the Plugin.

The local install shows up in the ChatGPT desktop Plugins browser with its icon, the PenguinRadar MCP server and the PenguinRadar Skill. Whether a client lists a local marketplace depends on its version and workspace policy.

## Connect over MCP (OAuth)

Remote MCP endpoint: `https://penguinradar.com/mcp`

1. In your client's connector or MCP settings, add the URL and choose **OAuth**.
2. Sign in on PenguinRadar's authorization page and review the permissions.

`data:read` covers your tracked accounts, follower and following lists and detected changes. Tick **Also allow online queries** if the assistant should be able to look up public accounts (`data:fetch`); every online query then needs an explicit credit budget. Many clients cannot request more permission later, so reconnect to change it.

## Install the Plugin locally

```bash
git clone https://github.com/penguinradar/chatgpt-plugin
codex plugin marketplace add ./chatgpt-plugin
```

Then choose **PenguinRadar Preview** in the Plugins browser, install it and connect through OAuth. To update later, `git pull`, run `codex plugin add penguinradar@penguinradar-preview` again and restart the app. In ChatGPT you can also use **Add custom MCP server** with the URL above and OAuth; that tests the connection but does not install the Plugin. Support depends on your client and workspace policy. See [`plugin/INSTALL.md`](plugin/INSTALL.md).

## Ask naturally

- "Which accounts am I tracking?"
- "Show alice's last available followers."
- "What changes did you detect for alice in the last seven days?"
- "Query bob's public followers online, at most 2 credits."

## MCP tools

| Tool | What it does |
|---|---|
| `list_tracking` | Your tracked accounts |
| `get_account` | An account's existing profile and totals |
| `list_followers` / `list_following` | Available follower or following list, one page |
| `get_account_changes` | Detected changes in a date range |
| `query_public_account` | Budgeted online lookup of a public account (needs `data:fetch` and `maxCredits`) |

## What to know

- Reading existing data never starts a scan and spends no collection credits.
- Instagram does not publish follow timestamps: PenguinRadar reports when a change was *detected*, not when it happened.
- A page or snapshot can cover only part of an Instagram list; the assistant reports `coverage` and warnings.
- No Instagram password is ever requested. The bundle contains no credentials.

## Links

[Plugin docs](https://penguinradar.com/docs/plugins) · [Agent Skill](https://github.com/penguinradar/skill) · [CLI](https://github.com/penguinradar/cli) · [Open API](https://penguinradar.com/docs/reference) · [Privacy](https://penguinradar.com/privacy) · [Terms](https://penguinradar.com/terms) · support@penguinradar.com

## License

[MIT](LICENSE)

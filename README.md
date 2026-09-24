# Keepp for AI agents

Build and run a **[Keepp](https://keepp.link)** page from an AI app or your own code: the blocks a page is made of, the copy, the theme, products and bookings, and payments through Stripe.

There are two ways in. Most people want the first.

## 1. Connect Keepp as an MCP server (recommended)

Keepp runs a remote MCP server at:

```
https://api.keepp.link/mcp
```

Add it to any app that supports MCP connectors, sign in with your Keepp account, approve what the app can do, and ask for what you want. There's no key to copy. The server carries its own guidance on building a good page, and it can create pages, products and bookable offerings, connect Stripe, Google Calendar and Zoom, and restyle the theme.

### Claude Code (this plugin)

This repo is a Claude Code plugin marketplace, and the plugin connects the Keepp MCP server for you:

```shell
/plugin marketplace add thinslatelabs/keepp-skill
/plugin install keepp@keepp
```

Then run `/mcp`, pick **keepp**, and sign in in the browser window that opens. On a machine with no browser, Claude Code prints the sign-in link instead.

Without the plugin, the same thing is one command:

```shell
claude mcp add --transport http keepp https://api.keepp.link/mcp
```

### Claude, ChatGPT and other apps

Step-by-step for each: [Connect Keepp to Claude, ChatGPT or any AI app](https://keepp.link/blog/how-to/connect-keepp-to-claude-or-chatgpt).

## 2. The HTTP API with an API key

For scripts, scheduled jobs and custom agents where nobody is there to sign in. Generate a key in your Keepp dashboard under **AI Agent** (it looks like `keepp_live_…`). The API reads and replaces your whole page and lists what your page can reference.

The skill in this repo, [`plugins/keepp/skills/keepp-page/SKILL.md`](./plugins/keepp/skills/keepp-page/SKILL.md), teaches an agent that API: authentication, the read-then-replace loop, images, errors, and where to fetch the block vocabulary and page-building guidance. If the MCP tools are available in a session, the skill tells the agent to use those instead.

### Other agent runtimes

Codex, Copilot CLI, Gemini CLI, and cross-runtime setups recognise `~/.agents/skills/`. Copy the skill folder in:

```bash
git clone https://github.com/thinslatelabs/keepp-skill.git /tmp/keepp-skill
cp -r /tmp/keepp-skill/plugins/keepp/skills/keepp-page ~/.agents/skills/keepp-page
```

### Any LLM or assistant

Hand it the skill contents, either by pasting `SKILL.md` or pointing it at the raw file:

```
https://raw.githubusercontent.com/thinslatelabs/keepp-skill/main/plugins/keepp/skills/keepp-page/SKILL.md
```

## Learn more

- Developer docs: https://keepp.link/developers
- Machine index: https://keepp.link/llms.txt

## License

[MIT](./LICENSE) © ThinSlate Labs

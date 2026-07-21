# Keepp Page Skill

An [Agent Skill](https://agentskills.io/specification) — packaged as a Claude Code plugin — that teaches an LLM to build and manage a **[Keepp](https://keepp.link)** page through the Keepp Agent API: adding and arranging the blocks a page is made of, writing the copy, placing products and bookings, and styling the theme.

The skill itself is [`plugins/keepp/skills/keepp-page/SKILL.md`](./plugins/keepp/skills/keepp-page/SKILL.md).

## What it does

A Keepp page is an ordered list of blocks on a two-column grid — links, preview links, cards, headers, text, profile, social icons, forms, maps, products, and bookings. Given a Keepp Pro API key, an agent using this skill can:

- **Build and edit the whole page** — add, remove, reorder, and restyle any block, and set the page theme.
- **Place products and bookings** the owner has created. These are read-only to the agent: it can put them on the page, but it can never create one or publish a price the owner didn't set.

It also teaches the *judgment* behind these — when a plain link beats a product card, when a page has grown long enough to need sections and nav tabs, when an on-page form converts better than a link to one — and the one rule that matters most: a write replaces the whole page, so always read it first and send every block back.

## Requirements

A **Keepp Pro** API key (looks like `keepp_live_…`). Generate one in your Keepp dashboard under **AI Agent**. Base URL: `https://api.keepp.link`.

## Install

### Claude Code (plugin)

This repo is a Claude Code plugin marketplace. Add it and install the plugin:

```shell
/plugin marketplace add thinslatelabs/keepp-skill
/plugin install keepp@keepp
```

### Other agent runtimes

Codex, Copilot CLI, Gemini CLI, and cross-runtime setups recognise `~/.agents/skills/`. Copy the skill folder in:

```bash
git clone https://github.com/thinslatelabs/keepp-skill.git /tmp/keepp-skill
cp -r /tmp/keepp-skill/plugins/keepp/skills/keepp-page ~/.agents/skills/keepp-page
```

### Any LLM / assistant

No skills directory needed — just hand it the skill contents, either by pasting the `SKILL.md` or pointing it at the raw file:

```
https://raw.githubusercontent.com/thinslatelabs/keepp-skill/main/plugins/keepp/skills/keepp-page/SKILL.md
```

## Learn more

- Developer docs (full REST reference): https://keepp.link/developers
- Machine index: https://keepp.link/llms.txt

## License

[MIT](./LICENSE) © ThinSlate Labs

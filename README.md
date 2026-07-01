# Keepp Page Skill

An [Agent Skill](https://agentskills.io/specification) — packaged as a Claude Code plugin — that teaches an LLM to build and manage a **[Keepp](https://keepp.link)** page through the Keepp Agent API: creating and updating product cards (including affiliate items with promo codes and lead-capture cards) and editing page settings.

The skill itself is [`plugins/keepp/skills/keepp-page/SKILL.md`](./plugins/keepp/skills/keepp-page/SKILL.md).

## What it does

Given a Keepp Pro API key, an agent using this skill can:

- **Manage catalog cards** — create, list, update, and delete product cards, each with a title, description, price, promo/referral code, category, images, and call-to-action behaviour.
- **Edit page settings** — the layout mode, about text, hero button, page-wide card defaults, and theme.

It also teaches the *judgment* behind these — when to send a buyer to an external link vs. capture a lead, when to show a detail view vs. fire the CTA directly, and how card defaults relate to per-card overrides.

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

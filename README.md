# Keepp Storefront Skill

An [Agent Skill](https://agentskills.io/specification) that teaches an LLM to build and manage a **[Keepp](https://keepp.link)** storefront through the Keepp Agent API — creating and updating product cards (including affiliate items with promo codes and lead-capture cards) and editing storefront settings.

The skill itself is [`SKILL.md`](./SKILL.md). Its frontmatter `name` is `keepp-storefront`.

## What it does

Given a Keepp Pro API key, an agent using this skill can:

- **Manage catalog cards** — create, list, update, and delete product cards, each with a title, description, price, promo/referral code, category, images, and call-to-action behaviour.
- **Edit storefront settings** — the layout mode, about text, hero button, storefront-wide card defaults, and theme.

The skill also teaches the *judgment* behind these — when to send a buyer to an external link vs. capture a lead, when to show a detail view vs. fire the CTA directly, and how card defaults relate to per-card overrides.

## Requirements

A **Keepp Pro** API key (looks like `keepp_live_…`). Generate one in your Keepp dashboard under **AI Agent**. The skill's base URL is `https://api.keepp.link`.

## Install

**Claude Code** — clone (or copy `SKILL.md`) into your skills directory:

```bash
git clone https://github.com/thinslatelabs/keepp-skill.git ~/.claude/skills/keepp-skill
```

**Other agent runtimes** (Codex, Copilot CLI, Gemini CLI, and cross-runtime) recognise `~/.agents/skills/`:

```bash
git clone https://github.com/thinslatelabs/keepp-skill.git ~/.agents/skills/keepp-skill
```

**Any LLM / assistant** — you don't need a skills directory. Just hand it the skill contents, either by pasting [`SKILL.md`](./SKILL.md) or pointing it at the raw file:

```
https://raw.githubusercontent.com/thinslatelabs/keepp-skill/main/SKILL.md
```

## Learn more

- Developer docs (full REST reference): https://keepp.link/developers
- Machine index: https://keepp.link/llms.txt

## License

[MIT](./LICENSE) © ThinSlate Labs

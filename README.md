# Dalton Skills

Agent skills from [Dalton](https://getdalton.com), the A/B testing platform for
online stores. The skills follow the [Agent Skills](https://agentskills.io)
format, so they work in Claude, Claude Code, Cursor, Codex, GitHub Copilot and
other agents that read `SKILL.md` files.

One plugin, `dalton`, with two groups of skills:

| Group | What it covers | Needs a Dalton account |
| --- | --- | --- |
| Dalton | Using Dalton: set it up, build and fix A/B tests, read results. | Yes, with the [Dalton MCP server](https://docs.getdalton.com/advanced/mcp-server) connected |
| CRO | General conversion rate optimisation: research and learn about a brand, audit pages, plan tests. | No |

## Install

### Any agent (skills.sh)

```bash
npx skills add DaltonAI/dalton-skills
```

Install a single skill:

```bash
npx skills add DaltonAI/dalton-skills --skill <skill-name>
```

### Claude Code

```text
/plugin install dalton --marketplace DaltonAI/dalton-skills
```

The Dalton skills need the Dalton MCP server, which is installed separately.
See the [MCP server docs](https://docs.getdalton.com/advanced/mcp-server).

## Skills

### Dalton

| Skill | Use it when |
| --- | --- |
| _coming soon_ | |

### CRO

| Skill | Use it when |
| --- | --- |
| _coming soon_ | |

## Repository layout

```
.claude-plugin/marketplace.json            Claude Code marketplace
plugins/dalton/                            The plugin (only this folder is installed)
├── .claude-plugin/plugin.json             Plugin manifest; lists both skill folders
├── README.md
└── skills/
    ├── dalton/<skill-name>/SKILL.md       Dalton-specific
    └── cro/<skill-name>/SKILL.md          General CRO
```

## License

MIT

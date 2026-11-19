# Dalton plugin

Agent skills from [Dalton](https://getdalton.com), in two groups:

| Group | Skills | What it covers | Needs a Dalton account |
| --- | --- | --- | --- |
| CRO | `cro-audit`, `cro-brand-research`, `cro-customer-voice`, `cro-page-audit`, `funnel-walkthrough`, `competitor-roadmap`, `side-by-side`, `cro-test-sizing` | General CRO: research and learn about a brand, audit pages, plan tests. | No |
| Dalton | `dalton-setup`, `dalton-usage`, `build-in-dalton`, `qa-variant`, `read-and-decide`, `dalton-review-ideas` | Using Dalton: set it up, build and fix A/B tests, read results. | Yes, with the [Dalton MCP server](https://docs.getdalton.com/advanced/mcp-server) connected |

Each skill is a folder under [`skills/`](skills/) with a `SKILL.md` file.

The Dalton MCP server is not part of this plugin. Connect it separately with
your Dalton login: see the [MCP server docs](https://docs.getdalton.com/advanced/mcp-server).

## Install

```text
/plugin marketplace add DaltonAI/dalton-skills
/plugin install dalton@dalton-skills
```

## Links

- [Dalton MCP server docs](https://docs.getdalton.com/advanced/mcp-server)
- [Repository](https://github.com/DaltonAI/dalton-skills)

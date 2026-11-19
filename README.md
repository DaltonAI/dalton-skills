# Dalton Skills: AI-powered CRO for e-commerce

Dalton Skills is a free, open-source set of agent skills for AI-powered CRO for e-commerce, meaning conversion rate optimisation for online stores run with an AI agent doing much of the legwork. They are written for e-commerce managers, CRO specialists, agencies and developers who work on online stores. Once an agent has them, it can study a store, pick what to test, draft A/B tests in [Dalton](https://getdalton.com) and read the outcome. Keep the loop going and the store turns into a self-improving website, one that tests continuously, learns from each result and holds on to what works.

Built by [Dalton](https://getdalton.com), an A/B testing platform for online stores.

## What Dalton does

[Dalton](https://getdalton.com) is an A/B testing platform for online stores with AI built in. It suggests tests worth running, builds the variants without needing a developer, splits traffic on a fixed ratio for a planned period, and picks the winner by conversion rate or revenue per visitor. The Dalton MCP server lets an AI agent read a store's analytics and test history and draft new tests. A person always decides when a test starts, pauses or goes live.

## The loop

The skills follow one cycle. Run it again and again:

1. **Find** what is costing sales: the store's data, a walk through it as a shopper, what competitors do, and what customers say.
2. **Plan** tests bold enough to show a clear result and sized for the store's traffic.
3. **Build and check** each test as a draft in Dalton, on mobile and desktop.
4. **Decide** when a test ends: ship it, extend it or stop it, and take a lesson from the losers.
5. **Keep it going**: at least two tests live, a fresh roadmap every few months, and the agent handling the weekly routine on a schedule.

## Skills

The repository holds 14 skills in two groups. Each one sits in its own folder with a `SKILL.md` file.

### CRO skills (any store, no Dalton account needed)

These run on any online store. If the Dalton MCP server is connected, they also pull in the store's Dalton data.

- [`cro-audit`](plugins/dalton/skills/cro/cro-audit/SKILL.md): a complete review of the store's data, funnel and competitors, ending in one ranked test roadmap for the months ahead.
- [`cro-brand-research`](plugins/dalton/skills/cro/cro-brand-research/SKILL.md): builds a picture of a brand before any testing: what it promises and where, its tone, visual identity, offers and the reasons people buy.
- [`cro-customer-voice`](plugins/dalton/skills/cro/cro-customer-voice/SKILL.md): groups reviews, support tickets and survey answers into counted reasons to buy, counted worries, and test ideas drawn from them.
- [`cro-page-audit`](plugins/dalton/skills/cro/cro-page-audit/SKILL.md): checks a single page (product, landing, category, cart or checkout) against the questions a shopper has at that point.
- [`funnel-walkthrough`](plugins/dalton/skills/cro/funnel-walkthrough/SKILL.md): goes through the store from homepage to checkout as a shopper would and logs each obstacle.
- [`competitor-roadmap`](plugins/dalton/skills/cro/competitor-roadmap/SKILL.md): sets one page type beside 3-5 competitors and turns the differences into ranked tests.
- [`side-by-side`](plugins/dalton/skills/cro/side-by-side/SKILL.md): lays your site and one competitor out next to each other, page by page, as visual boards.
- [`cro-test-sizing`](plugins/dalton/skills/cro/cro-test-sizing/SKILL.md): tells you whether a test can reach a clear answer on your traffic, covering the smallest change it can detect, the time it needs and how many versions to run.

### Dalton skills (need the Dalton MCP server)

- [`dalton-setup`](plugins/dalton/skills/dalton/dalton-setup/SKILL.md): the starting point for Dalton. Connects the agent, installs the tracking script, sets up purchase tracking, plans a roadmap and builds the first tests.
- [`dalton-usage`](plugins/dalton/skills/dalton/dalton-usage/SKILL.md): a week-by-week routine for an ongoing testing programme, with the agent taking on the repetitive jobs on a schedule.
- [`build-in-dalton`](plugins/dalton/skills/dalton/build-in-dalton/SKILL.md): converts a test idea or a roadmap line into a draft inside Dalton.
- [`qa-variant`](plugins/dalton/skills/dalton/qa-variant/SKILL.md): tests a draft before launch on both devices, on unusual pages and with real taps.
- [`read-and-decide`](plugins/dalton/skills/dalton/read-and-decide/SKILL.md): helps you choose between shipping, extending and stopping a test, and writes a brief for your developers.
- [`dalton-review-ideas`](plugins/dalton/skills/dalton/dalton-review-ideas/SKILL.md): works through the ideas Dalton's CRO agent has surfaced, improves their drafts and helps you choose which to run.

## Install

### Any agent (skills.sh)

```bash
npx skills add DaltonAI/dalton-skills
```

To install a single skill:

```bash
npx skills add DaltonAI/dalton-skills --skill cro-audit
```

### Claude Code

```text
/plugin marketplace add DaltonAI/dalton-skills
/plugin install dalton@dalton-skills
```

Once installed, you will find the skills under the `dalton:<skill-name>` names.

### Claude (desktop and web)

Zip a skill's folder and upload it under Settings → Capabilities → Skills, with code execution turned on.

### Connecting Dalton

The Dalton skills rely on the Dalton MCP server at `https://mcp.getdalton.com`. Sign in with your Dalton login. The [MCP server docs](https://docs.getdalton.com/advanced/mcp-server) cover setup for Claude, ChatGPT, Claude Code and Cursor. You can also ask your agent to run `dalton-setup`.

## Starter prompts

- "Run a CRO audit of our store against [competitor] and give me a test roadmap for the next three months."
- "Research our brand before we plan any tests."
- "Go through our last year of reviews: why do people buy, and what holds them back?"
- "Audit our product page on mobile."
- "Do we have enough traffic to test our cart page?"
- "Set us up with Dalton and build our first tests."
- "Every Monday, send me the new Dalton ideas worth running and how our tests are doing."

## FAQ

### What does the AI actually do here?

It handles the slow parts of conversion work: reading the store's numbers, browsing the site like a shopper, comparing it with competitors, drafting and checking A/B tests, and reading the results afterwards. People still set the goals, review what the agent produces and decide what goes live. The skills give the agent a defined method, so each finding points to evidence and each test has enough traffic behind it to produce a readable result.

### What is a self-improving website?

A site that gets better through constant testing. Something is always being tested, each result turns into a lesson or a change, and the plan gets renewed every few months. With [Dalton](https://getdalton.com) and these skills, an agent carries out most of that work on a schedule, and you approve every change before it goes live.

### Do I need a Dalton account?

Not for the 8 CRO skills, which work on any online store with any agent that can browse. The 6 Dalton skills do need a Dalton account and the Dalton MCP server. Find out more at [getdalton.com](https://getdalton.com).

### Can the agent launch tests or change my live site on its own?

No. Through Dalton the agent only ever creates drafts. You launch, pause, conclude and deploy tests yourself, inside Dalton.

### Do the skills invent results or uplift figures?

No. Each finding rests on something observed on the site, in the data or in what customers wrote. The skills do not make up uplift percentages, and they do not present general benchmarks as facts about your store.

### Which agents can use them?

Any agent that supports the open [Agent Skills](https://agentskills.io) format, including Claude, Claude Code, Codex, Cursor and GitHub Copilot. Skills that inspect a live site need a browser tool, such as Claude in Chrome or Playwright.

## Repository layout

```
.claude-plugin/marketplace.json            Claude Code marketplace
plugins/dalton/                            The plugin (only this folder is installed)
├── .claude-plugin/plugin.json             Plugin manifest
├── README.md
└── skills/
    ├── cro/<skill-name>/SKILL.md          General CRO skills
    └── dalton/<skill-name>/SKILL.md       Dalton skills
```

## License

MIT, © Firstmate BV. Made by [Dalton](https://getdalton.com), AI-powered CRO for e-commerce.

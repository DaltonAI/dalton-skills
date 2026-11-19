---
name: dalton-review-ideas
description: Go over the test ideas Dalton's CRO agent found on a store - check each finding against the live site and the account's past tests, check and fix the draft it built, and recommend which to save, which to fix first and which to discard. Use when someone asks to review, go through or triage their Dalton ideas, the CRO agent's opportunities or the Inspiration screen, asks which Dalton suggestions are worth running, or for a weekly ideas review. Needs the Dalton MCP connected. Built by Dalton (getdalton.com).
---

# Review the CRO agent's ideas

Goal: the user spends a few minutes deciding, not an hour reading. For every idea Dalton's CRO agent found: is the finding true, is the test any good, does it fit the plan, and is the draft ready. The user saves or discards; you check, fix and recommend.

## 1. Gather

- `whoami` for the account.
- `cro_agent_opportunities`: each idea's finding, the full report and the test the agent drafted. `list_ideas` gives the same ideas more briefly, plus the ideas the team saved for later.
- `get_learnings` and `list_experiments` (running, and finished): what's running now and what was tried before.
- The roadmap, if there is one (the saved ideas with their launch months, or a plan the user shares).

## 2. Check each idea

- **Is the finding true?** Open the page it's about on mobile and desktop with the browser you have (Claude in Chrome, Playwright in Claude Code, or any browser tool your agent has). Is the problem visible today, on more than one page of that type? Sites change; a finding from an older scan can be fixed already.
- **Was it tried before?** A test on the same element or idea in the learnings or finished tests. If it lost, say so; only rerun it if something is clearly different (another device, a bolder version).
- **Does it clash?** A running test on the same element, or an idea already on the roadmap.
- **Is it worth a test?** Visible on the first screen, noticed within 2 seconds, at the moment the buyer decides. Small tweaks rarely show a result. Check it fits the page's traffic (`cro-test-sizing`): the agent's expected lift is its own estimate for ranking ideas, not a forecast.
- **Is it on brand?** The change uses the site's own elements, fonts and colours, and follows Dalton's brand intelligence (`read_brand_intelligence`).

## 3. Check and fix the draft

Each idea comes with a drafted test. Open it with `get_experiment` and look at the preview links on mobile and desktop:
- Does it show where intended, and look native?
- Do prices, names and ratings come from the page, not hard-coded from one product?
- Does anything else on the page break?

Fix what's off with `update_variant`. The draft stays the agent's idea until the user saves it. For a full pre-launch check, use `qa-variant`.

## 4. Recommend

Sort every idea into one of four:
- **Save:** true, worth testing, draft works. Say which roadmap month it fits.
- **Save after a fix:** good idea, draft needed work. Say what you fixed, or what still needs fixing.
- **Later:** good idea, wrong moment (clashes with a running test, a sale, or the plan). Offer to save it for later with `create_idea` and a launch month.
- **Discard:** not true anymore, tried and lost, too small for the traffic, or off brand. One line why.

## 5. Deliver

A short message the user can act on in minutes:
1. One line: how many ideas, how many worth saving.
2. Per idea, best first: name, one line on the finding, your recommendation and why, and the editor link.
3. What you fixed in the drafts.

The user decides. Save an idea to their tests with `accept_idea` only when they ask you to. Discarding is always theirs, in Dalton. Launching stays with them too.

If this runs on a schedule (see `dalton-usage`), only report ideas that are new since the last review, and keep it to a few lines when nothing changed.

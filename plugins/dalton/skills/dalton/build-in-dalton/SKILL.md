---
name: build-in-dalton
description: Turn a test idea or roadmap line into a ready-to-review A/B test draft in Dalton through the Dalton MCP, then check it on mobile and desktop. Use when someone asks to build, set up or draft a test in Dalton, or to build the top tests from a roadmap. Needs the Dalton MCP connected. Built by Dalton (getdalton.com).
---

# Build in Dalton

Goal: a draft in Dalton that the user can preview and launch with confidence. The agent builds and checks drafts; launching, pausing and deploying stay with the user in the Dalton app.

## 1. Before building

- `whoami` to get the account id.
- `list_experiments` (running and drafts) and `get_learnings`: is a similar test already running or done? Don't build the same change on an element another running test touches.
- Agree with the user, in one short list: the change, the page group, the device, the main metric, and the name.
- Name tests like `<MON> · <Theme> <n> · <change> · <LANG>`, for example `DEC · Cart 1 · Free delivery bar in the cart · PL`. The month tag lets you see each month's tests together.

## 2. Build

1. `find_rulesets` to pick where it runs. Prefer a whole page group (all product pages, the cart) over a handful of pages. Use `add_ruleset` only when nothing fits.
2. `query_content_map` on that page to get the real sections and selectors.
3. `create_experiment` with the baseline and one variant (two only when traffic is high). Build the change from the site's own elements, fonts and colours. Read live values from the page (prices, delivery text, ratings) instead of hard-coding them, so the change stays right on every product.
4. `update_variant` to refine.

## 3. Check before handing over

Open the preview link on mobile and desktop, on at least two different products or pages of the group:
- The change shows, on the first screen where intended, and looks native.
- Nothing else on the page broke or moved (menu, buy button, cart drawer, sticky bars).
- Edge cases: a product on sale, out of stock, without reviews, a long name; the other language if the store has one.
- The variant doesn't show where it shouldn't (blog, checkout, account pages).

Fix and re-check until clean. Then give the user: the draft name, the editor link, the preview links, what you checked, and anything you couldn't check.

## 4. Reading results (for later)

- Dalton shows the measured change, a 90% range for where the real effect likely sits, and the chance the variant beats the baseline. The default bar for a winner is 90% chance to beat, adjustable in the settings.
- Let a test run its planned window (at least two full weeks) before judging it.
- How much evidence is enough is a business decision: cheap, easy-to-undo changes can go live on less certainty than costly ones.

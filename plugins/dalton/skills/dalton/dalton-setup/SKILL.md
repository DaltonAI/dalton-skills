---
name: dalton-setup
description: Get a store started with Dalton, from nothing to its first tests - connect the agent to the Dalton MCP server, install the Dalton script, make sure purchases arrive, plan a testing roadmap for the first months, and build the first batch of test drafts. Use when someone is starting with Dalton, asks to set up, install or connect Dalton, add the Dalton snippet or pixel, connect Dalton to Claude, ChatGPT or Cursor, or wants their first Dalton tests planned and built. Built by Dalton (getdalton.com).
---

# Set up Dalton

Goal: by the end, Dalton measures the store, purchases arrive, there's a roadmap for the next 2-3 months, and the first tests are drafts ready to launch. The install takes about 10 minutes; the roadmap and the first drafts take longer and can be a later session. Go one step at a time, wait for the user to confirm each click in an app, and say what's left if you stop early.

Click paths in the Dalton app change now and then. When a step depends on one, read the current docs page instead of reciting from memory: `read_docs` once Dalton is connected, or fetch `https://docs.getdalton.com/<path>.md` before that.

## 1. Where are we

Find out in one message:
- Do they have a Dalton login? If not, they sign up at getdalton.com, or ask whoever runs the store's Dalton account to invite them.
- Which platform the store runs on: Shopify, WordPress, Wix, React or Next.js, or something else.
- Can you work in the site's code (a theme or app repo open in this session), or does the user or their developer paste the snippet?

Skip the steps that are already done.

## 2. Connect the agent

The server is `https://mcp.getdalton.com` (HTTP, sign in with the Dalton login, no API keys). If you can add MCP servers yourself, do it; otherwise give the exact steps for the user's app:

- **Claude (desktop or web):** Settings → Connectors → Add custom connector. Name `Dalton`, URL `https://mcp.getdalton.com`. Needs a paid Claude plan.
- **Claude Code:** `claude mcp add --transport http dalton https://mcp.getdalton.com`, then `/mcp` → dalton → Authenticate.
- **ChatGPT:** Dalton is an app; open it from the [MCP server docs](https://docs.getdalton.com/advanced/mcp-server) and connect.
- **Cursor and other MCP clients:** add a remote server: `{ "mcpServers": { "dalton": { "url": "https://mcp.getdalton.com" } } }`.

New tools often only show in a new chat or session. Then call `whoami`: one account, use it; several, ask which store; none, their login isn't a member yet and whoever manages the account invites them.

## 3. Install the script

1. **Get the snippet:** in Dalton, Connectors → Tracking → Dalton Script → View instructions. It carries the account's id, so always copy it from there; never write one yourself. No code access? **Share with developer** makes a link with the snippet and instructions, no Dalton login needed.
2. **Paste it as high as possible in `<head>`, on every page:**

| Platform | Where |
| --- | --- |
| Shopify | Online Store → Themes → Edit code → `theme.liquid`, top of `<head>`, in the **published** theme |
| WordPress (Elementor) | Elementor → Custom Code, location `<head>` |
| Wix | Settings → Custom Code, Head, all pages |
| React, Next.js, Nuxt | The root layout (the install panel has a tab per framework) |
| Anything else | The HTML template, top of `<head>` |

If the site's code is open in this session, add the snippet yourself, show the change, and leave deploying to the user.

Watch out for: a new or duplicated Shopify theme (check the snippet is still there); single-page sites other than Next.js (turn on **Reapply changes** under Options); Google Tag Manager (works, but a tested element can flash its original); a strict Content Security Policy or firewall (two domains to allow, docs page `/technical/privacy-security`).

## 4. Make sure purchases arrive

Tests are decided on purchases and revenue, so no test should launch before this works.

- **Shopify:** add the Dalton Pixel under Settings → Customer events; Shopify's checkout runs outside the theme. Docs: `/advanced/shopify-pixel`.
- **Other sites:** add the Dalton Pixel to the order confirmation page. Docs: `/advanced/pixels`.
- **GA4 ecommerce events already in the data layer?** Nothing to do: Dalton picks up `purchase` and `add_to_cart`.

Several stores, markets or checkouts: check each one.

## 5. Verify

- **Script:** in the install panel, **Next: verify installation**; Connectors should say **Installed**. With a browser or web fetch, check the source of the homepage and a product page for `dalton-installation-script`.
- **Purchases:** the user places a test order (never place one yourself). Under Settings → Conversions, Purchase should no longer say *not detected*.
- **Not found?** Clear the site's cache, reload in a private window, check it's the published theme. `DALTON_ID has already been declared` in the console means the snippet is on the page twice. `?dalton_debug=1` on any URL logs what Dalton does. More in `/faq/troubleshooting`.

Then the Dalton Chrome extension, for everyone who builds tests (desktop Chrome): the editor shows the real store with it.

## 6. Plan the first months

Goal: a roadmap for the next 2-3 months with enough tests to keep at least two running at all times, plus a few spare.

Ask in one message: the goal for the period (for example more revenue per visit), 3-5 competitors their customers compare them with, tests they ran before, their own ideas, and anything off limits (sale freezes, pages that can't change, who approves).

Dalton has little data of its own yet, so draw on:
- **The store's own analytics** (Shopify, GA4): visits per page type and device, to size the tests.
- **The live site:** walk it as a shopper on mobile and desktop (`funnel-walkthrough`).
- **Competitors:** what they do at the same buying moments (`competitor-roadmap`, `side-by-side`).
- **Dalton:** the brand and competitor scan (`read_brand_intelligence`) and any ideas the CRO agent already found (`cro_agent_opportunities`).
- **Customer voice:** reviews, support questions, what the ads promise.

For the full process use `cro-audit`. The roadmap's shape:
- 3-4 themes, each a buyer problem in plain words ("what will I really pay, delivered?").
- Under each, tests that are bold (noticed on the first screen within 2 seconds), native (the site's own elements, fonts and colours) and sized to traffic (whole page groups; two versions on quieter pages).
- Each test: change, why (the evidence), where, what it's measured on, and the month it runs. Two tests can share a page if they don't touch the same element.
- The store's own ideas first where they fit. Broken things go on a separate "just fix" list.

Save the roadmap in Dalton, so the plan lives where the tests get built: one idea per test with `create_idea`, its launch month (`JAN`-`DEC`, or `LATER`) and the why in the notes. Plan to revisit it after 4-6 weeks, once Dalton has its own data.

## 7. Build the first batch

- Pick 2-3 tests from the first month: on the page groups with the most traffic, and on different pages or different elements, so they can all run at once.
- Build each one as a draft with `build-in-dalton`, then check it with `qa-variant`.
- Hand over the editor and preview links for each. Launching is the user's, in Dalton, and only once purchases show as detected (step 5). Suggest launching them together, so the store has at least two tests running from the start.

## 8. Hand over

Tell the user, in a few lines:
- What's set up and verified, and anything you couldn't check.
- The roadmap: themes, and the tests per month.
- The drafts ready to launch.
- What's theirs to do now: the test order if it's still open, launching the drafts.
- How to keep it going: the `dalton-usage` skill covers the weekly and monthly routine.

Settings in the Dalton app (team, conversions, the snippet itself) and launching, pausing and deploying tests have no tools; those are the user's clicks.

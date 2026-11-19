---
name: qa-variant
description: Check a Dalton test draft before launch the way a careful QA person would - on mobile and desktop, on several kinds of products or pages, with real taps through the flow - and report what's broken with screenshots. Use when someone asks to QA, check or test a draft or variant before launching, or after a customer reports a bug in a running test. Built by Dalton (getdalton.com).
---

# QA a variant

Goal: launch only tests that work everywhere they run. A preview that renders once is not QA. A broken variant loses the test before it starts, and a hidden bug makes the result worthless.

## 1. Know what you're checking

- From Dalton (`get_experiment`, or the editor): the page group it runs on, devices, the variant's changes (selectors, html, css, js), and the preview links for baseline and each variant.
- `list_experiments` (running): other tests on the same page group. Two tests on one page are fine unless they touch the same element or break each other.
- Ask the user for anything special: sale prices running, other languages or markets, logged-in states, a checkout flow.

## 2. Pick the test pages

Not one page, a spread across the page group:
- A bestseller, a product on sale, one out of stock, one without reviews, one with a long name, one with variants (size, colour).
- Every language or market the test runs in.
- For cart and checkout tests: a basket under and over the free-delivery threshold.
- One page that should NOT show the change (blog, account, checkout, another category), to check the targeting.

## 3. Check each page, baseline and variant

Use the browser you have (Claude in Chrome, Playwright in Claude Code, or any browser tool your agent has). Mobile at iPhone size (390 px) and desktop at 1440 px. Accept the cookie banner. Never place an order or enter payment details.

For each page and device:
- **It shows:** the change appears where intended, on the first screen if that's the point, without a visible flash of the old version.
- **It's right:** prices, delivery text, ratings and names match the page they're on (not hard-coded from one product). Text fits, no cut-off or overlap, correct language.
- **It's native:** same fonts, colours and buttons as the site; it looks like part of the store.
- **Nothing else broke:** menu, search, image gallery and zoom, size picker, add to cart, cart drawer, sticky bars, pop-ups, chat widget. Compare the whole page with the baseline, top to bottom.
- **Real taps:** tap the new element and the main buttons around it; add to cart and open the cart. Links go where they should.
- **Tracking:** add to cart and other events still fire (no console errors from the variant).

Take a screenshot of baseline and variant for every check, named `<page>-<device>-<base|var>.png`.

## 4. Report

A table, one row per page and device: OK, or what's wrong with a screenshot. Then:
- **Blockers:** must be fixed before launch.
- **Fix if easy:** small visual issues.
- **Not checked:** what you couldn't reach (logged-in only, payment step), so someone else can.

If the Dalton MCP is connected and the user agrees, fix blockers in the draft with `update_variant` and check again. Launching stays with the user in Dalton.

---
name: competitor-roadmap
description: Compare one part of an online store (product page, cart, checkout, homepage, category page) with 3-5 competitors on mobile and desktop, then turn the gaps into a ranked A/B test roadmap. Use when someone asks to benchmark their site against competitors, wants test ideas for a page, or asks for a CRO roadmap for a page type. Built by Dalton (getdalton.com).
license: MIT
---

# Competitor roadmap

Goal: a short roadmap of tests the store can actually run, each one backed by what was seen on their own site and on competitor sites. Not a list of best practices.

## 1. Ask first (one message, then wait)

- The store URL and the page type to look at (for example: mobile cart).
- 3-5 competitors their customers compare them with. If they don't know, propose 3-5 and let them pick.
- Roughly how many visits that page gets per month, and their main conversion goal (orders, add to cart). If they use Dalton, read this from Dalton instead of asking.

## 2. Capture matched screens

Use the browser you have (Claude in Chrome, Playwright in Claude Code, or any browser tool your agent has).

- Same page type, same device, same state for every store. For a cart: one similar product in the basket, first screen and full page. For a product page: a comparable bestseller, first screen and buy box.
- Mobile at iPhone size (390 px wide) and desktop at 1440 px.
- Accepting the cookie banner is fine. Close other pop-ups. Never place an order or enter payment details.
- Go slowly (one page every few seconds). Some stores block fast automated browsing; if a site shows a captcha, ask the user to open the page in their own browser and share a screenshot.
- Save each screenshot with a clear name: `<store>-<page>-<device>.png`.

## 3. Compare per buyer question

Make a table with one row per question the buyer has at that moment, and one column per store. For a cart, for example:

- What will I pay in total, delivery included?
- How far am I from free delivery?
- When will it arrive?
- Can I trust this shop (reviews, returns, payment options)?
- Is the checkout button easy to reach?
- Is there anything worth adding?

In each cell write what the store does, in a few words, from the screenshot. Mark where the user's store is behind, equal or ahead. Only write what you can see; if something isn't visible, say "not shown".

## 4. Turn gaps into tests

For each clear gap, write one test:

- **Change:** what the visitor will see differently, in one sentence.
- **Why:** the evidence (for example "3 of 4 competitors show delivery cost in the cart, we show it only at checkout").
- **Where:** page group and device.
- **Measure:** the step it changes (add to cart, checkout started, orders), with orders as a check.

Rules for good tests:
- Visible on the first screen and noticed in 2 seconds. A small tweak below the fold rarely shows a result.
- Built from the store's own elements, fonts and colours, so it looks native.
- Sized to traffic: on low-traffic pages, test one bold change on the whole page type (all product pages, all carts) rather than one page, and two versions rather than three.
- Copying a competitor is a starting point, not proof. What works for them may not work for this store's customers; that's why it's a test.
- Fixes that are clearly broken (a missing button, a wrong price) go in a separate "just fix" list, not in the roadmap.

## 5. Rank and deliver

Score each test 1-5 on impact, confidence and ease, and sort. Deliver:

1. The comparison table.
2. The ranked roadmap (top 5-10 tests).
3. The "just fix" list.
4. The screenshots, so every claim can be checked.

Don't invent uplift percentages. If the user has the Dalton MCP connected, offer to build the top tests as drafts with the `build-in-dalton` skill.

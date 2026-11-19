---
name: cro-audit
description: Run a full CRO audit of an online store - data, funnel walkthrough, side-by-side with a competitor, competitor scan - and turn it into one ranked test roadmap for the next months. Use when someone asks for a CRO audit, a conversion review of their site, or a test plan for the coming months. Combines the side-by-side, competitor-roadmap and funnel-walkthrough skills. Built by Dalton (getdalton.com).
---

# CRO audit

Goal: one audit someone can act on: where the store loses buyers, what competitors do at those moments, and a ranked list of tests for the next 2-3 months that fits the store's traffic.

## 1. Ask first (one message)

- Store URL, markets and languages.
- The main competitor, plus 2-4 others.
- Goal for the period (for example more revenue per visit) and anything off limits (sale freezes, parts of the site that can't change, who approves).
- Tests already run or planned, so the audit builds on them.

## 2. Data (if the Dalton MCP is connected)

- Last 6-8 normal weeks: sessions, conversion, revenue per visit, per device and per traffic source. Read sale and campaign weeks separately.
- The funnel: product page views, add to cart, checkout, orders. Find the step that loses most.
- Page groups with the most traffic, and past tests with `list_experiments` (finished) and `get_learnings`: what won, what was flat, per device where possible.
- Check that purchases are tracked. If not, fixing tracking comes before testing.

Without Dalton data, say so and base the audit on the site and competitors only.

## 3. Walk the site

Run the `funnel-walkthrough` skill: homepage to checkout on mobile and desktop, friction log with screenshots. Always include the cart and checkout screens, with a basket under and over the free-delivery threshold.

## 4. Compare

- Run `side-by-side` with the main competitor on the page types that matter most (usually product page, cart, category).
- Run `competitor-roadmap` across 3-5 competitors on the weakest step from the data.

## 5. Build the roadmap

- Group the findings into 3-4 themes, each a buyer problem in plain words ("what will I really pay delivered?", "is this right for me?").
- Under each theme, tests that are visible on the first screen, native to the site, and sized to the page's traffic (whole page groups, two versions on low traffic).
- Each test: change, why (evidence: data, walkthrough, competitors), where, metric, and the month it runs. Two tests can share a page if they don't touch the same element.
- Put the store's own ideas first where they fit.
- A separate "just fix" list for things that are broken.
- Score with impact, confidence and ease; no invented uplift percentages.

## 6. Deliver

1. A short summary: the 3 biggest findings and the plan in one line each.
2. The data read (if available).
3. The friction log and the side-by-side boards.
4. The roadmap as a table (theme, test, why, where, metric, month), easy to paste into a sheet.
5. The "just fix" list.

Offer to build the first month's tests as drafts with `build-in-dalton`, and to QA them with `qa-variant`.

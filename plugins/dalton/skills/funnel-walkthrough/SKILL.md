---
name: funnel-walkthrough
description: Walk an online store like a shopper, from homepage to category, product page, cart and checkout, on mobile and desktop, and log every point of friction with a screenshot. Use when someone asks to check their funnel, audit their site end to end, or find where shoppers get stuck. Built by Dalton (getdalton.com).
license: MIT
---

# Funnel walkthrough

Goal: a friction log of what a real shopper runs into, step by step, with evidence. You browse the site yourself; don't ask the user to describe each step.

## 1. Ask first

- The store URL, and the market or language to check.
- Which product to use as the example (a bestseller), or pick one yourself.
- If they use Dalton with the MCP connected: read conversion per step and per device from Dalton (sessions, add to cart, checkout, orders for the last 30 days) so the walkthrough can focus on the step that leaks most.

## 2. Walk the funnel

Use the browser you have (Claude in Chrome, Playwright in Claude Code, or any browser tool your agent has). Do it twice: mobile at iPhone size (390 px) and desktop at 1440 px.

1. Homepage: first screen. Is it clear what they sell and where to start?
2. Category page: can you filter and compare? Are price, reviews and stock visible on the cards?
3. Product page: first screen. Where are photo, price, delivery, reviews and the buy button? What's missing?
4. Add to cart: what happens (drawer, toast, page)? Which next step is the obvious one?
5. Cart: total with delivery, free-delivery threshold, trust signals, position of the checkout button. Try once under and once over the free-delivery amount.
6. Checkout: go as far as you can without an account (guest checkout, address step). Never submit payment or place an order.

Accepting the cookie banner is fine; close other pop-ups. Go slowly; if a captcha appears, ask the user for screenshots of that step instead.

## 3. Log friction

For each problem, one row:

| Step | Device | What happens | Why it costs sales | Screenshot |
|---|---|---|---|---|

Only log what you saw. Separate real friction from taste. Note what works well too, so it isn't changed by accident.

## 4. Deliver

- The friction log, sorted by step.
- The top 3 problems, each with one test idea (change, why, where, what to measure).
- A "just fix" list for things that are broken rather than worth testing.
- The screenshots.

No invented benchmarks or uplift percentages. To compare a step with competitors, use the `competitor-roadmap` skill; to build tests, use `build-in-dalton`.

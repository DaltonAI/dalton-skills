---
name: cro-page-audit
description: Audit one page of an online store on its own - a product page, landing page, category page, cart or checkout - on mobile and desktop, by checking how it answers each question a buyer has at that moment, including trust, price and delivery, and the mobile first screen. Returns the problems by severity with screenshots, the tests worth running, and a just-fix list. Use when someone asks to audit, review or improve a specific page or page type, asks why a page doesn't convert, or wants test ideas for one page without a competitor comparison. Built by Dalton (getdalton.com).
license: MIT
---

# Page audit

Goal: for one page, what stops a buyer from taking the next step, backed by screenshots, and what to test or fix first. It reviews a template, not one URL: findings should hold for the other pages of that type.

## 1. Ask first (one message)

- The page or page type, and one typical example (a bestseller for a product page). For a landing page: the ads that send traffic to it.
- What the page should lead to (add to cart, checkout, sign-up).
- Roughly how many visits it gets per month, and the split between mobile and desktop, if they know. If the Dalton MCP is connected, read this from Dalton.

## 2. Capture

Use the browser you have (Claude in Chrome, Playwright in Claude Code, or any browser tool your agent has).

- Mobile at iPhone size (390 px wide) and desktop at 1440 px. First screen and full page.
- Accepting the cookie banner is fine; close other pop-ups. Never place an order or enter payment details.
- Check one or two other pages of the same type (another product, another category), so a finding isn't a one-off.
- For a landing page, open it through the ad's own link, with its parameters: that's the page visitors actually see.

## 3. Go through the buyer's questions

At each page type, the buyer has a few questions. For each one, note whether the page answers it, where (first screen, further down, or not at all) and how clearly.

| Page | The buyer's questions |
| --- | --- |
| Product page | What is it, exactly? Is it right for me (size, fit, compatibility, how it looks in real life)? What will I pay, delivered? When will it arrive? Can I trust this shop and this product (reviews, returns, guarantees)? How do I buy, and is the button easy to reach? |
| Landing page | Is this what the ad promised? What's on offer, and why here? What do I do next? |
| Category page | Can I find what I want (filters, sorting, search)? Can I compare (price, rating, stock, colours on the cards)? |
| Cart | What's the total, delivery included? How far am I from free delivery? When will it arrive? Can I still trust this (payment options, returns)? Is checkout one obvious tap away? |
| Checkout | Can I buy as a guest? Are there surprises (extra costs, forced account, long forms)? Do I see the payment methods I use? |

Then look at four angles across the whole page:
- **First screen on mobile:** list what's on it, top to bottom, and what got pushed below it. Where do the photo, price, delivery and buy button sit?
- **Trust:** reviews (count, rating, where), returns, guarantees, payment options, contact. Shown where the buyer decides, or tucked away?
- **Price:** how it's shown: discounts, the delivery cost, totals, payment in instalments. Any surprise later in the flow?
- **Things that are broken:** missing images, errors, buttons that don't respond, elements jumping as the page loads, text cut off.

Only note what you can see on the screenshots. Separate real friction from taste, and note what works well, so it isn't changed by accident.

## 4. Rate and turn into actions

For each problem, one row:

| Question or angle | What the page does | Why it costs sales | Severity | Screenshot |
| --- | --- | --- | --- | --- |

Severity: **blocks** (stops people buying), **slows** (makes buying harder or less sure), **minor**.

Then:
- **Tests:** for the biggest problems, one test each: change, why (the evidence), where, what to measure. Visible on the first screen and noticed within 2 seconds, built from the site's own elements and style, on the whole page type rather than one page.
- **Just fix:** things that are plainly broken go on their own list. They don't need a test.

## 5. Deliver

1. Three lines: the biggest problems on this page.
2. The table, sorted by severity.
3. The top 3-5 tests.
4. The just-fix list.
5. The screenshots.

No invented uplift percentages or benchmarks. To see how competitors handle the same page, use `competitor-roadmap`; to check the test is big enough for the page's traffic, `cro-test-sizing`. If the Dalton MCP is connected, offer to build the top test with `build-in-dalton`.

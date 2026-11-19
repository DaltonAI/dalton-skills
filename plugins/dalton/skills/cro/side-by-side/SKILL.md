---
name: side-by-side
description: Build a page-by-page visual breakdown of an online store next to one competitor, like a Figma board - full-page phone screenshots side by side, numbered callouts on what each one does differently, desktop first screen below, one test line per page. Use when someone wants to compare their site with a competitor visually, show a team or manager what a competitor does better, or prepare a CRO audit. Built by Dalton (getdalton.com).
---

# Side-by-side breakdown

Goal: one board per page type (homepage, category, product page, add to cart, cart, checkout) that someone gets in 10 seconds: two phones next to each other, numbered notes on what differs, and the test it leads to. It's an analysis, not a verdict: what works for the competitor still has to be tested on this store.

## 1. Ask first

- The store and the one competitor to compare with (one is clearer than five; use `competitor-roadmap` for a wider scan).
- The market and language, and which page types (default: all six above).
- One comparable product to use on both sites (same category, similar price), and for category pages the same category.
- The language the boards should be in.

## 2. Capture matched screens (this makes or breaks it)

Every pair must be apples to apples. Before anything else, check each pair on:
- **Same page type and same product or category.**
- **Same device:** mobile at iPhone size (390 px wide, high resolution) and desktop at 1440 px.
- **Same state:** both at the top, cookie banner accepted, other pop-ups closed, same login state, same basket contents for cart and checkout (one item, under the free-delivery threshold unless that's the point).
- **Same depth:** full-page mobile screenshots, plus a mark where the first screen ends (the fold, 844 px on an iPhone 13).

Use the browser you have (Claude in Chrome, Playwright in Claude Code, or any browser tool your agent has). Go slowly; if a site shows a captcha, ask the user for screenshots. Never place an order or enter payment details; checkout goes as far as guest/address without submitting.

If one pair isn't matched (one site scrolled, a banner didn't load), recapture it. Don't explain it away in text.

## 3. Annotate

For each page type, list what each site shows, top to bottom, then keep only the differences that matter to a buyer deciding (price, delivery, reviews, stock, help choosing, trust, the main button). 3-6 callouts per side.

- Number the callouts per side (1, 2, 3...), each a short line of 3-8 words: "Delivery date next to the price", "Reviews: 0 shown as 0".
- Place each callout outside the screenshot, with a thin line to the exact spot, left of the store's phone and right of the competitor's.
- Write only what is visible. If something didn't load, say so in the callout ("banner didn't load in our capture").

## 4. Build the boards

One page per page type, landscape or tall, in this order:
1. Small page-type label, then a plain factual title that names the difference: "They help you choose, we show specs". No subtitles, no slogans.
2. One grey line on what's compared: "Mobile, same product, same moment. The dashed line is where the first screen ends."
3. The two phones side by side, full page, same width, store left and competitor right, with the callouts.
4. Desktop first screen of both below, smaller.
5. One line at the bottom: **Tests:** the 1-2 tests this page leads to.
6. Source line in small grey: device, date, URLs.

Keep body text under about 30 words per page. Caveats go in the source line, never in paragraphs. Use the store's brand colours sparingly; a neutral background lets the screenshots carry it.

Build it as HTML (one page per board) and print to PDF; a deck tool or Figma works too.

## 5. Close

Add one opening page (what was compared, how, and the 3 biggest differences in one line each) and one closing page with the tests, ranked. Then check every board once more: matched screens, every callout true on the screenshot, no text a reader has to work for.

If the Dalton MCP is connected, offer to build the top tests as drafts with the `build-in-dalton` skill.

---
name: cro-brand-research
description: Learn an online store's brand before changing anything - what it sells and to whom, what it promises and where those promises actually show on the site, its voice, its look, its offers, why customers buy and what worries them - and write it up as a one-page brand profile that tests and copy can follow. Use when someone asks to research or get to know a brand or store, to onboard a new store, to write a brand profile, or before planning tests or writing copy for a store you don't know yet. Built by Dalton (getdalton.com).
---

# Brand research

Goal: a one-page brand profile someone can work from: tests that look and sound like the brand, and ideas that start from what the brand promises and its customers care about. Everything in it is either seen (with where) or marked as your inference.

## 1. Ask first (one message)

- The store URL, the markets and languages.
- What it's for: a test plan, new copy, onboarding a new store.
- Anything you should read that isn't public: brand guidelines, a tone-of-voice document, customer research. Don't wait for it if there's none.
- 2-3 competitors their customers compare them with, if they know.

## 2. The store itself

Use the browser you have (Claude in Chrome, Playwright in Claude Code, or any browser tool your agent has), on mobile (390 px wide) and desktop (1440 px). Visit the homepage, a category page, a bestseller's product page, the cart, and the about, delivery and returns pages. Never place an order or fill in forms.

Write down:
- **What and for whom:** what they sell, the price level, who it's clearly for (and who it isn't).
- **Promises:** every claim the brand makes about itself: free delivery, fast shipping, returns, guarantees, handmade, sustainable, best price, expert advice, ratings. For each, where it shows (homepage banner, product page, cart, checkout, footer only) and where a buyer would need it but doesn't see it. A promise that's on the homepage but missing in the cart is the most useful thing you'll find.
- **Voice:** formal or casual, "you" or "we", short or long sentences, words they use often, words they avoid. Copy two or three typical lines as examples.
- **Look:** fonts, colours, button style, photo style, how badges and labels look. A test has to use these to look native.
- **Offers:** discounts, bundles, free-delivery threshold, subscriptions, codes, loyalty, payment in instalments. Which ones show where.

## 3. Outside the site

- **Ads:** what the brand's ads promise (Meta Ad Library, Google Ads Transparency Center). Open the pages the ads link to: does the page keep the ad's promise?
- **Reviews:** the main reasons people buy and the main complaints, from the reviews on the site and on review sites. For a proper count, run `cro-customer-voice`.
- **Elsewhere:** marketplaces, social profiles, press, if they say something the site doesn't.

## 4. Next to competitors

In a few lines: how the brand differs from the 2-3 competitors on price, range, promise and tone, and one thing each competitor says that this brand doesn't. For a full comparison, use `competitor-roadmap` or `side-by-side`.

## 5. Write the profile

One page, in this order:
1. **The brand in two sentences:** what, for whom, why them.
2. **Why people buy, and what worries them:** top reasons and top worries, with where each came from.
3. **Promises and where they show:** a table: promise, where it shows now, where it's missing.
4. **Voice:** do and don't, with the example lines.
5. **Look:** the rules a new element must follow.
6. **Offers:** what exists and where it shows.
7. **Against competitors:** the differences that matter to a buyer.
8. **Open questions:** what you couldn't check.

Mark each point as seen (with the page) or inferred. Don't fill gaps with guesses that read like facts.

## 6. Use it

- Every promise that's missing where a buyer decides (product page, cart) is a test candidate. So is every common worry with no answer on the site.
- Hand the voice and look rules to whoever builds the tests, so variants look and sound like the brand.
- If the Dalton MCP is connected, compare the profile with Dalton's brand intelligence (`read_brand_intelligence`) and list what Dalton has wrong or misses, so the user can correct it in Dalton. To turn the findings into a test plan, use `cro-audit`.

---
name: cro-customer-voice
description: Turn what customers say - reviews, support questions, chat logs, survey answers, return reasons - into counted reasons to buy and worries, in their own words, then check where the store answers each one and turn the gaps into test ideas and copy. Use when someone asks to analyse reviews, support tickets or survey results, wants to know why customers buy or hesitate, needs voice-of-customer research, or wants test ideas or copy grounded in what customers say. Built by Dalton (getdalton.com).
---

# Customer voice

Goal: a short, counted list of why people buy and what makes them hesitate, in their own words, with the place on the site where each one should be answered. Counts come from the data, not from guesses.

## 1. Ask first (one message)

- Which sources they have: product reviews, a review site (Trustpilot, Google), support tickets or chat logs, survey or post-purchase answers, return reasons, comments on ads.
- Exports are best (CSV or text). Public review pages you can read yourself. Don't log in to anything on their behalf.
- The period (the last 6-12 months works well) and whether to look at the whole store or certain products.

## 2. Read and tag

- Read everything if it's a few hundred items. If it's more, take a fair sample (all of the last few months, or the same number per star rating) and say how you sampled.
- Tag each item with one or more themes. Let the themes come from what people write; typical ones are quality, fit or size, price and value, delivery cost and speed, returns, service, how it looks in real life, comparisons with other brands.
- Keep three groups apart:
  - **Reasons to buy:** what people liked, chose it for, or tell others.
  - **Worries before buying:** questions and doubts that come before the order ("does it run small?", "when will it arrive?"). These are what the site can answer.
  - **Problems after buying:** damage, late delivery, wrong item. These are for the team that can fix them, not for a test.
- Note the exact words customers use. Their phrasing is often better copy than the store's.
- Leave out names, emails, order numbers and anything else that identifies a customer.

## 3. Count

For each theme: how many items mention it, the share of the total, and whether it's mostly positive or negative. Split by product or category where it differs. Say the total and the period, so the counts can be read ("41 of 380 reviews, last 12 months").

## 4. Check the site

For the top reasons and the top worries, look at where the store addresses each one: product page, cart, checkout, delivery page, or nowhere. Use the browser you have (Claude in Chrome, Playwright in Claude Code, or any browser tool your agent has), on mobile and desktop.

- A strong reason to buy that the product page barely mentions is a test candidate: put it where people decide.
- A common worry with no answer near the buy button is a test candidate: answer it there.
- A worry the site answers but in the wrong place (only in the FAQ, below the fold) is a candidate too.

## 5. Deliver

1. Two or three lines: the main reasons people buy, the main worries.
2. The table: theme, group (reason, worry, problem), count and share, a typical quote, where the site answers it now.
3. The top 3-5 test ideas: change, why (the count and the quote), where, what to measure.
4. Copy lines in the customers' own words, ready to use in tests.
5. A "pass on" list: problems after buying, for the team that can fix them.

No invented percentages or benchmarks: every number comes from the items you read. If the Dalton MCP is connected, offer to save the test ideas as ideas in Dalton, or build the best one with `build-in-dalton`.

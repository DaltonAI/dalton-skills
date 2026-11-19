---
name: read-and-decide
description: Read an A/B test result in Dalton and decide what to do - ship, extend or stop - keeping what the data shows apart from the business decision, then write a short developer brief to build a winner into the site. Use when someone asks "did this test win?", "should we ship / extend / stop this?", "what does this result mean?", or needs to explain a result to their team. Needs the Dalton MCP connected. Built by Dalton (getdalton.com).
license: MIT
---

# Read and decide

Goal: a clear call on a test, with the reasoning a manager can follow. Two things are kept apart: what the test shows (evidence) and what we do with it (decision). The evidence is never a pass/fail; the decision is a business call.

## 1. Get the facts

- `get_experiment` for the test: plan (planned window, days run), per-variant sessions and conversions, measured change, 90% range, chance to beat, revenue per session and order value.
- `get_learnings` and `list_experiments` (finished): earlier tests on the same page or idea.
- Note when the test ran (sale weeks, Black Friday and campaigns behave differently) and which devices and page group it covered.
- If Dalton holds back the figures, the test hasn't reached its planned window or minimum data yet. Say so and stop at "keep running"; don't judge on a mid-run read.

## 2. Say what the test shows (evidence)

Explain the three numbers in plain words, with this test's figures:
- **Measured change:** what we saw so far, for example +22.6% conversion.
- **90% range:** where the real effect most likely sits, for example -1.1% to +51.4%. A wide range means we know the direction better than the size.
- **Chance to beat:** how likely the variant is better at all, for example 94%.

Read them together, in one sentence: "Very likely better, size still uncertain, worst plausible case about flat." Also check:
- Conversion and revenue per session pointing different ways (more orders but smaller baskets, or one very large order). Say which one carried the result.
- The step the change affects (add to cart for a product page change) next to orders.
- Devices: if a device split is available, a win on one device and a loss on the other is a partial winner. Treat a one-device win as a lead to retest on that device, not as proof.

## 3. Make the call (decision)

Weigh three costs, using this test's numbers:
- **Cost of being wrong:** the low end of the range, and how easy it is to undo.
- **Cost of waiting:** while the test runs, half the visitors see the version that's probably worse, and the next test on that page waits.
- **Cost of keeping it:** running it in Dalton is free; building it into the site costs developer time.

Then pick one:
- **Ship:** clears the account's bar (90% chance to beat by default) or is close, with a worst case near zero and a cheap change.
- **Extend:** promising, but the planned window isn't complete, it covers fewer than two full weeks, or the range is very wide and the change is costly to build. Say how many more days and why.
- **Stop:** flat after the full window, or clearly worse. Write down the lesson; a flat result is a learning too.

Bigger, harder-to-undo changes need more evidence than small, reversible ones. Lower-traffic stores often decide at 80-90%, high-traffic stores can wait for 95%. When shipping on thinner evidence, don't count the measured uplift in forecasts; plan on the low end of the range.

## 4. Developer brief (when shipping)

Winners often stay "concluded" and never reach the site. If the winner should be built in permanently, write a brief from the variant's changes in `get_experiment`:
- What changes, where (page group, devices, selector), with a before/after description.
- The exact copy, styles and behaviour, and the code from the variant as a reference.
- Edge cases seen in the test (sale prices, out of stock, other languages).
- Until it's built: keep it deployed in Dalton, so visitors already get the winning version.

Deploying a winner in Dalton is done by the user in the app, not by the agent.

## 5. Deliver

1. One line: the call (ship / extend X days / stop) and why.
2. The evidence in plain words with the numbers.
3. The trade-off in 2-3 lines.
4. The lesson for the next test.
5. The developer brief, if shipping.

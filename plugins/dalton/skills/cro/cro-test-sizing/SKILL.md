---
name: cro-test-sizing
description: Work out whether an A/B test can give an answer on a page's traffic - the smallest change it can detect, how long it needs to run, how many versions it can afford, and which step to measure - from the store's own visits and conversion rates. Use when someone asks how long a test should run, whether they have enough traffic to test, how many variants they can test, why their tests end without a result, or wants a test plan sized to their traffic. Built by Dalton (getdalton.com).
---

# Test sizing

Goal: before a test is built, know whether it can give an answer in a few weeks, and if not, change the test (wider, bolder, fewer versions, another step) rather than run it anyway. A test that's too small for its page ends flat, whatever the idea was worth.

## 1. Get the numbers

For the page group the test runs on, over the last 4-8 normal weeks (leave sale and campaign weeks out):
- **Visitors:** sessions or visits that see the page group. Not page views: one visitor viewing five product pages counts once. Mixing them up makes a test look twice as feasible as it is.
- **Conversion rate of the step the test changes**, counted on those same visitors:
  - reach a product page (for homepage and category tests),
  - add to cart (for product page tests),
  - start checkout or order (for cart and checkout tests).
- **Mobile and desktop separately**, if the test runs on one device only.

Take them from the store's analytics (Dalton, GA4, Shopify). If the user only has site-wide figures, say the estimate is rough.

## 2. Work it out

This is a standard approximation, good enough for planning. With:
- `n` = visitors per version over the test's run (total visitors in that period ÷ number of versions, baseline included),
- `p` = the conversion rate of the measured step, as a fraction (2.5% = 0.025),
- `K` = 9 for a winner bar of 90% chance to beat, which is about 80% confidence in classic terms; 12 for 95% chance to beat; 16 for classic 95% confidence,

the **smallest change the test can reliably detect**, relative to the current rate, is:

```
smallest change ≈ √( K × (1 − p) ÷ (n × p) )
```

And the visitors each version needs to detect a given relative change `c` (10% = 0.10):

```
visitors per version ≈ K × (1 − p) ÷ (p × c²)
```

Example, K = 9: a product page group gets 20,000 visits in 4 weeks; two versions, so 10,000 each.
- Measured on orders, at 2.5%: the smallest detectable change is about 19%.
- Measured on add to cart, at 8%: about 10%.

Same traffic, a much better chance of an answer, because add to cart happens more often. Compute it; don't guess.

## 3. Read the result

- **Compare the smallest detectable change with what the idea could plausibly do.** Copy tweaks and small visual changes rarely move a step by more than a few percent. If the page can only detect 20%, the test needs a bold change, or a different setup.
- **Run whole weeks, at least two**, so every weekday counts equally. Plan for 2 to 6 weeks (Dalton picks a window of 2, 4 or 6). If the numbers need much longer, the question is too small for the page.
- **Each version needs enough conversions on its own:** below roughly 100 conversions per version, a result is fragile whatever the formula says.

## 4. If it doesn't fit

In order of what usually helps most:
1. **Widen the page group:** all product pages instead of one, every collection instead of a few. A change that works on one product page usually makes sense on all of them.
2. **Measure an earlier step:** add to cart instead of orders, with orders as a check that nothing got worse.
3. **Make the change bolder:** something visitors notice on the first screen within 2 seconds.
4. **Fewer versions:** A/B rather than A/B/C. Each extra version splits the traffic further.
5. **Both devices instead of one,** if the change makes sense on both.
6. Still too small: make it a change you just make on the site without a test, or drop it.

Tests on quiet pages can also take a lower winner bar (80% chance to beat) if the change is cheap and easy to undo; say so explicitly when you suggest it.

## 5. Deliver

For each test: the page group, visitors per week, the measured step and its rate, versions, weeks, and the smallest detectable change. Then a verdict: **fits**, **fits if** (what to change), or **too small** (and what to do instead). Show the inputs, so anyone can redo the sum.

In Dalton, the targeting picker shows the expected time to results before launch; check it against your estimate.

---
name: dalton-usage
description: How to work with Dalton week to week and month to month - keep at least two tests live, learn from the tests that lose, build winners into the site, plan a new roadmap every few months, keep going over ideas and competitors, and put that routine on a schedule. Use when someone asks how to get the most out of Dalton, what to do in Dalton this week or month, how often to test or plan, what to do after a test wins or loses, wants a check-in on their testing program, or wants the agent to run recurring Dalton work (a weekly ideas review, a performance report, preparing the next tests). Built by Dalton (getdalton.com).
---

# Working with Dalton

Goal: a testing program that keeps learning. Something is always running, every finished test becomes a lesson or a change on the site, and the plan is refreshed every few months. The agent can plan, draft, check and read; launching, pausing and deploying stay with the user.

If Dalton is connected, look at the account first (what's running, the drafts, the ideas, what finished lately) and give advice about that store, not in general.

## The habits

1. **Always at least two tests live.** A week without a running test is a week nothing is learned. Two tests can run at once on different pages, or on different elements of one page. Run more when traffic allows.
2. **Keep the next tests ready.** Have a draft waiting for each slot, so a finished test is followed by a new one the same week.
3. **Not everything wins.** Many tests end flat or lose. That's normal, and it's why you test instead of just changing the site. A program that only produces winners is testing changes that are too safe.
4. **Learn from what loses.** A losing or flat test says something about the buyers: what they don't care about, or what the change got wrong. Write the lesson down in one sentence and let it shape what comes next: a bolder version, the other device, another buyer problem. Don't quietly rerun the same idea.
5. **Build winners into the site.** Deploy the winner in Dalton, so every visitor gets it right away, and have it built into the site within a few weeks. The deployment in Dalton is a bridge, not the final home. Once it's in the site's code, end the deployment in Dalton so the change isn't applied twice. A winner that never reaches the site is the most common way to lose one.
6. **Test big enough to learn.** Small tweaks below the fold rarely show a result. Test what visitors notice on the first screen or at the moment they decide, on whole page groups rather than single pages.

## The rhythm

### Every week (15 minutes)

- Are at least two tests running? If a slot is empty, launch the next draft, or build one with `build-in-dalton`.
- Anything stuck: a draft waiting for review, a test that doesn't show on the site, a draft about to be archived for age.
- New ideas from Dalton's CRO agent: save the ones that fit the roadmap, discard the rest.
- Leave running tests alone until their planned window is over. Judging them mid-run leads to wrong calls.

### When a test finishes

- Make the call (ship, extend or stop) with `read-and-decide`.
- **Won:** deploy it in Dalton, brief the developer to build it in, and write down why it won. Then look for the follow-up: the same idea on other pages, the other device, a bolder version.
- **Lost or flat:** write the lesson. Decide whether it points to a follow-up or settles the question.
- Launch the next test in that slot the same week.

### Every month

- Look back in a few lines: what ran, what won, what lost, what was learned. Share it with the team.
- Re-order the roadmap with what you learned: move up tests that build on a win, drop or park the ones a loss made unlikely.
- Chase winners that are deployed in Dalton but not yet built into the site.

### Every 2-3 months: a new roadmap

Plan the next period from:
- Everything learned so far: wins, losses, flat results, per device.
- The store's data for the last normal weeks: which steps and pages lose the most.
- Competitors again: what changed on their key pages since last time.
- What Dalton knows about the brand and its competitors.
- The ideas waiting in Dalton, the team's and the CRO agent's.
- Customer voice: reviews, support questions, what the ads promise.
- The calendar ahead: sales, launches, code freezes.

Use `cro-audit` for the full process. Every new test should build on a result or a finding. Save the roadmap in Dalton as ideas with their launch months.

### Around sales and peak season

- Sale weeks convert very differently from normal weeks. Finish tests before a sale, or plan tests made for the sale, and read sale weeks on their own.
- Launch tests for peak season early enough that they finish before it. Respect code and sale freezes.
- High-traffic weeks fill tests fast, which makes them a good time for the questions quiet weeks can't answer.

## Keep the ideas coming

- **The team:** customer service hears the questions, marketing knows the ads, the buyers know the products. Anyone can add an idea to Dalton, with a month or "later".
- **Competitors:** go over the key pages of 3-5 competitors every roadmap round (`competitor-roadmap`, `side-by-side`). What they do is a starting point, not proof; that's why it's a test.
- **Customers:** the top reasons people buy, and the top worries, from reviews and support. Every common worry is a test candidate.
- **Dalton's CRO agent:** it keeps scanning the store, and its ideas come with a draft already built.

## Who does what

Agree once, and write it down:
- Who plans and builds drafts (the agent can), who checks them before launch (`qa-variant`), and who launches.
- Who builds winners into the site, and how soon.
- Who gets Dalton's notifications (email or Slack), so finished tests don't go unnoticed.

## A check-in

When the user asks where things stand, report on the store as it is:
- Tests running, and whether there are at least two.
- Drafts ready for the next slots.
- Tests finished since the last check-in, and what was decided.
- Winners deployed in Dalton but not yet built into the site.
- Ideas waiting for a decision.
- When the next roadmap is due.

End with the one to three things to do this week.

## Put the routine on a schedule

Most of the rhythm can run without the user asking each time. If the agent can run on a schedule (scheduled tasks, routines or cron jobs, depending on the app), offer to set up the jobs that fit the store:

| Job | When | What it does |
| --- | --- | --- |
| Ideas review | Weekly | Goes over new ideas from Dalton's CRO agent and the saved ones; sends the few worth doing next, with why, and the ones to discard |
| Performance report | Weekly or monthly | The store against the previous period, per device; tests running, finished and waiting; empty slots; winners not yet built in. The monthly one adds the lessons and where the roadmap stands |
| Finished tests | Weekly | For each test that ended, the evidence and a proposed call with `read-and-decide`, for the user to decide |
| Next tests | When a slot frees up, or before each month | Builds the next tests on the roadmap as drafts (`build-in-dalton`), checks them (`qa-variant`), and sends the links to launch |
| Draft watch | Weekly | Drafts waiting for review, and drafts about to be archived |
| Competitor watch | Monthly | Competitors' key pages: what changed that's worth a test |
| Roadmap | Every 2-3 months | Gathers the inputs above and drafts the next roadmap for review |

These are a start, not the full list. Suggest other schedules that fit the store and how the team works, for example:
- a daily check that visits and purchases still arrive, which catches a script or pixel broken by a theme change;
- a reminder six weeks before a sale or peak season, to plan and launch tests that finish in time;
- a nudge two to three weeks after a winner is deployed in Dalton, until it's built into the site;
- a monthly scan of new reviews and support questions for buyer worries worth a test;
- a quarterly summary of the testing program for management.

Combine the weekly jobs into one message (for example Monday morning) rather than several. The weekly report is the check-in above, on a schedule.

To set one up:
- Agree with the user: which jobs, which day and time, where the message goes (this chat, Slack, Teams, email or another channel they use), and who it's for.
- Write each job's instructions so they stand on their own: a scheduled run doesn't see this conversation. Name the store's Dalton account, what to check, the format, where to send it, and the limits below.
- Check the scheduled run has what it needs where it runs: the Dalton connection, and a connection to the channel it sends to.
- Run each job once straight away, so the user sees the first message and can adjust it.

Limits for scheduled runs:
- The same as always: drafts only. Never launch, pause, conclude or deploy, and don't change the code of a running test on a schedule.
- Don't make the call on a finished test, or save or discard ideas, on your own; prepare the decision and send it.
- Keep messages short: what changed, what needs the user, and the links. When there's nothing new, one line, or nothing if the user prefers.

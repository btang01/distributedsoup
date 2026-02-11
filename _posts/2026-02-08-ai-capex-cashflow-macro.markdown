---
layout: post
title:  "AI Capex, Cash-Flow Timing, and Why Markets Aren't Celebrating Beats"
date:   2026-02-08
categories: [strategy, technology]
---

Over the last earnings cycle, a familiar pattern emerged across large U.S. technology companies. Earnings beat expectations, revenue growth remained solid, guidance was generally positive, and yet equity market reactions were muted to even downright negative.

The dominant explanation circulating on LinkedIn, YouTube, and earnings recaps is that investors are growing uneasy about the scale and persistence of AI-driven capex. Across a small group of incumbents, annualized investment is now approaching or exceeding **$600B** on a run-rate basis, and markets are questioning whether or not this spending will earn an adequate return.

I started digging into this because the market reaction, and the explanations people were giving, didn’t sit right with me. It felt like everyone was pointing at “AI capex” in a vague way without actually explaining the mechanism.

The way I’ve come to think about it is less about AI “working” or “not working,” and more about timing. Large, front-loaded AI capex pulls cash forward and pushes free cash flow further out, at a moment when cash is expensive and risk capital is picky. In that setup, earnings beats still matter, but they don’t force a re-rating. Markets seem to be waiting for the cash to arrive.

## Capital Expenditure: Evidence of a Step-Change
The current AI buildout represents a huge step-change in capital intensity across a small set of firms. To anchor the discussion, consider the scale:

1. **Amazon.com, Inc.:**
Capex accelerated sharply through FY2024–FY2025, with management signaling an annualized investment run-rate approaching **$200B in FY2026**, driven by data centers, custom silicon, logistics automation, and AI infrastructure.

2. **Alphabet Inc.:**
Capex increased from roughly **$50B in 2024** to approximately **$90B in FY2025**, with management guiding **$175–185B for FY2026** as AI infrastructure build-out continues.

3. **Microsoft:**
Capex approached **$85–90B in FY2025**, reflecting aggressive investment in cloud and AI capacity tied to Azure and Copilot. Microsoft reported **$37.5B in Q2 FY2026 alone**, putting it roughly on pace for **~$145B in FY2026**.

4. **Meta Platforms, Inc.:**
Capex rose from roughly **$40B in 2024** to **~$70B in 2025**, with anticipated FY2026 capex in the **$115–135B** range as AI workloads and data center expansion continue.

5. **NVIDIA:**
NVIDIA stands apart. It benefits directly from this capex wave without bearing it at the same scale. Its customers, hyperscalers, spend while NVIDIA monetizes quickly.

Taken together, these companies are committing **well over half a trillion dollars** in capital to AI-related infrastructure over a short window centered around FY2026. This alone is enough to change how markets think about valuation, even before asking whether this spending eventually pays off.

## Earnings Great, Valuations Muted - What Gives?
So we know there is a huge step change in capex, but how did the companies do? In short, across the board, the tech firms delivered strong, double-digit revenue and net income growth. Performance was objectively good, no matter how you slice and dice it (YoY, QoQ, full year, month comparisons, etc). For reference, I highlighted the performance for the big tech firms below. 

1. **Amazon.com, Inc.:**
Reported Q4 2025 revenue of $213.4B, up 14% YoY. AWS (cloud) net sales grew 24% YoY with strong backlog growth (+40%). Net income increased 6% YoY to ~$21.2B for the quarter. **Free cash flow fell despite operating cash flow growth due to heavy capex.**

2. **Alphabet Inc.:**
Q4 2025 revenue grew 18% to ~$113.8B, net income rose ~30% YoY to ~$34.5B. Cloud revenue surged ~48% YoY. **These strong results were accompanied by the unusually large capex guide.**

3. **Microsoft:**
Q4 numbers showed double-digit net income growth, strong cloud performance, net income up ~23% YoY.

4. **Meta Platforms, Inc.:**
Q4 2025 revenue grew ~23.8% YoY with earnings also up ~9.3% during this period. Growth was tied to strong ad demand and AI features monetization.

This makes the market reaction feel counterintuitive, until you separate the **earnings** from the **cash flow**. Think of earnings as just an accounting construct, whereas capex is your cash reality. It becomes a lot clearer when we understand how this capex hits the three financial statements: the **income statement**, the **balance sheet**, and the **cash flow statement**.

A useful grounding question is: **How does capex flow through the balance sheet first, distort the income statement later, and only show up immediately in cash flow (which is what valuations actually care about)?**

To begin, all equity valuation collapses to the same framework.

$$
\text{Value} =  \sum \frac{\text{Future Free Cash Flow}_t}{(1+r)^t}
$$

What changed in this earnings cycle was the timing and visibility of their cash flows, not the long-term viability of these companies. 

For the formula above, this means the inputs change. Front-loaded capex reduces free cash flow in the near term and shifts more of it into later years — increasing the effective *t* in the denominator. Because each future dollar is divided by (1+r)^t, cash that arrives later is worth materially less today. And the further out the cash flows sit, the more sensitive the valuation becomes to small changes in *r* or delays in execution.

This explains why earnings beats can coexist with valuation compression.

## Where the Adjustment Actually Happens
Capex affects the three financial statements very differently:

1. **Income statement:**
On the income statement, capex does not hit all at once. Instead, it’s capitalized on the balance sheet and expensed gradually through depreciation over time. That smooths reported earnings and keeps metrics like EPS and P/E ratios relatively stable in the near term. Revenue, margins, and operating profit can all look healthy even while the company is spending aggressively. Depreciation does eventually flow through EBIT, but it’s a slow, accounting-driven effect rather than a reflection of the immediate cash outlay. In short: the income statement mostly reflects execution, not cash strain.

2. **Balance sheet:**
The balance sheet is where capex shows up immediately as commitment. Cash goes down, and **property, plant, and equipment (PP&E)** goes up by the same amount. This is the moment when capital becomes less reversible. Once cash is converted into data centers, custom silicon, or infrastructure, future returns depend on utilization and demand that hasn’t yet been proven. The company has effectively locked in a long-dated bet. The balance sheet captures what the company has committed to, not whether it will pay off.

3. **Cash flow statement:**
Capex is an immediate cash outlay that hits your cash flows in the near term.

$$
\text {Free Cash Flow} = \text {Operating Cash Flow} - \text{Capex}
$$

When capex ramps faster than operating cash flow, free cash flow compresses — even if earnings look strong. This doesn’t imply failure. It means cash returns are being pushed further out in time.

This is the statement valuations care about most, because equity value ultimately discounts future free cash flow, not reported earnings.

Valuation uses a required return (discount rate) which reflects the cost of capital and perceived risk. For a deeper breakdown of WACC and how it's used in investment decisions, see my earlier post: Vibes vs. Numbers in Tech Investments [^1].

## Why Re-Rating Doesn't Happen Immediately
A logical question to ask is: **if capex eventually stabilizes, why not just reprice the companies now and get that stock price way up there?**

Backlogs, guidance, and early revenue signals matter, but they’re weaker evidence than sustained, bounded reinvestment and structurally higher free cash flow. 

Investors want evidence that incremental AI revenue converts into high marginal cash flow, with capex intensity normalizing and free cash flow recovering structurally over multiple quarters.

By **high marginal cash flow**, I don’t mean high revenue growth or even high accounting margins. I mean that each additional dollar of AI-driven revenue generates a large amount of incremental free cash flow without requiring proportional reinvestment. In other words, revenue growth that scales on existing infrastructure rather than demanding another round of heavy capex. Markets are looking for evidence that AI workloads can move from capacity-building to utilization-driven economics, where incremental usage drops through to cash rather than pulling more spending forward.

This actually helps explain the divergent results within Big Tech.
1. **NVIDIA** monetizes quickly and has short cash-flow duration. Its valuation remains near all-time highs without needing any heroic assumptions.
2. **Meta** reinvests heavily but its core ad engine throws off high-margin core cash flows. That cash subsidizes their AI investment, which keeps near-term cash flow resilient even as they increase capex.
3. **Microsoft** blends fast monetization (software, Copilot, enterprise contracts) with longer-dated infrastructure bets. 
4. **Amazon** and **Alphabet** carry heavier, more irreversible infrastructure exposure. A larger share of their current cash is being pulled forward to fund assets with longer, less certain payback periods.

Companies with more visible cash conversion retain premium valuations while those pushing cash further into the future see muted valuation response until the free cash flow proves itself.

Another way to frame this is as an AI investment loop. Capital is deployed first to build capacity, which enables usage, which then drives monetization, cash flow, and eventually reinvestment. Markets tend to re-rate after this loop visibly closes, not while it is still in progress. Today, most large incumbents are somewhere in the middle: capacity is expanding rapidly, usage is ramping, but durable free cash flow has yet to fully materialize. Until that final step becomes visible, valuation expansion remains deferred, even if earlier stages look strong.

## Macro Factors: Not the Driver, but Reinforces the Signal
All of this investment and waiting isn't happening in a vacuum. The current AI capex cycle is unfolding against a macro backdrop that makes cash-flow timing matter more than usual.

At a high level, the Federal Reserve can influence financial conditions with two distinct levers:
1. **Policy rates** (raise or lower the price of money)
2. **Liquidity** (increase or decrease the quantity of money in the system)

These two are often conflated, but they don’t move together.

In recent years, rising unemployment (visible through rising jobless claims, softer job openings, moderating wage pressure) has acted like a short-term tailwind for equities. The logic seems straightforward (if not unjust): weaker labor data increases the likelihood of Fed rate cuts, pushing investors out of low-yielding safe assets like Treasuries and toward risk assets. 

All else equal, lower rates reduce the discount applied to future cash flows, but this "all else equal" rarely holds true.

With inflation still sticky and fiscal deficits large, the Fed can cut short-term interest rates while still keeping liquidity constrained (not injecting the system with cash by performing QE). In other words, the price of money can fall even as the supply of risk capital stays limited. This is the environment we’re closer to today.

In that setup, borrowing costs may ease modestly, but the pool of capital stays selective, especially for long duration or uncertain returns. Without the liquidity tailwind from QE, markets are less willing to reward growth and earnings beats on their own.

## Bonds Tell the Same Story
The bond market reinforces the same cash-flow timing signal.

A key macro indicator is the **yield curve**, which shows the cost of borrowing across different maturities. Its shape conveys market expectations for growth, inflation, and cash flow timing.

**Short-term yields** (3-month, 6-month, 1-year, 2-year Treasuries) are closely linked to Fed policy and reflect current inflation and funding conditions. **Long-term yields** (10-year, 20-year, 30-year Treasuries)  reflect expected growth, inflation and risk over time. These are less directly controlled by the Fed. When people say "yield curve" they are talking about yields across these maturities plotted together.

Usually, long-term yields exceed short-term yields because lending money for longer is riskier, so investors demand more return for inflation uncertainty, growth uncertainty and opportunity cost. The slope is positive. 

Today, the curve is inverted, where short-term yields exceed long-term yields. This signals expectation of slower future growth and lower inflation relative to current conditions. It also signals that cash today is expensive while cash further in the future is discounted less aggressively.

A brief clarification, since bond pricing is often misunderstood: bonds pay a fixed coupon. When demand rises, bond prices increase but the coupon stays the same, so the yield falls. When demand weakens, prices fall and yields rise.

In an inverted yield curve, short-term yields are high because policy remains tight, while long-term yields are lower because markets expect slower growth and eventual rate cuts. Investors are effectively signaling that today’s cash is expensive, but future cash will be cheaper as policy eases.

For equities, the implication is consistent with the broader thesis. High near-term discount rates and constrained liquidity raise the opportunity cost of cash spent today. Companies investing heavily now for returns far in the future face skepticism, even if current earnings are strong, until cash-flow realization becomes more visible.

## The Connecting Thread
At this point, the pieces fit together. Large AI investments pull cash forward and push returns further out, increasing the duration of future free cash flows. In a different macro environment, markets might be willing to look through that timing shift. 

Today’s backdrop is different. Elevated short-term rates, constrained liquidity, and an inverted yield curve all increase the opportunity cost of cash spent now and raise skepticism toward cash promised far in the future. 

None of this means the AI investment cycle is broken. It may end up looking obvious in hindsight. But from where we are now, the market is placing more weight on realized cash flows than on forward narratives. Whether that happens smoothly or whether these investments overshoot before they pay off is still very much an open question.

## Disclosure

I hold a diversified equity portfolio primarily through broad market ETFs, with exposure to several of the companies discussed above. My investment horizon is long-term, and this analysis reflects my own thinking on capital allocation and cash-flow timing rather than any short-term trading view. This is not investment advice.

[^1]: [Distributed Soup: Vibes vs. Numbers in Tech Investments](https://distributedsoup.com/blog/2025/01/16/vibe-driven-tech-invest.html){:target="_blank"}

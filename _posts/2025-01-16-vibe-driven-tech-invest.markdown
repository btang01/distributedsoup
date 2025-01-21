---
layout: post
title:  "Vibes vs. Numbers in Tech Investments"
date:   2025-01-16
categories: strategy technology
---


## **Introduction**
Over the past 14 years, I've collaborated with at least a dozen multi-billion dollar organizations in a wide array of industries[^1]. One recurrent theme stands out: tech project investments often feels more vibes-driven than being grounded in rigorous financial analysis. 

This post will explore why I think it happens, why this is a problem, and offer an approach that tries to account for the idiosyncracies unique to tech and business - to balance intuition and analytics to drive better decisions.

Since this is potentially a controversial topic and I run the risk of upsetting both technical and business-oriented people (maybe even artists as well), I'll caveat that all the opinions in this blog are my personal observation and don't reflect the views of my employer. Let's jump in...

## **Why Vibes-driven Investments are Common**
It's not that calculations are completely absent, but arguments for projects typically go like this: “We’ll increase revenue by releasing features faster, innovate more, boost customer experience, and cut costs by improving productivity and reducing overhead.” 

There are also a wide array of tools that can pull extensive metadata right out of your data centers and run some calculations that help you estimate how much you might save by getting out of pricy licenses or right-sizing your compute resources (based on industry benchmarks). There are cloud calculators that can incorporate assumptions and nail down estimated costs of each particular service down to thousandths (and beyond) of decimal places. 

Though the claims are valid and the data is detailed, these components are usually only brought together for the initial pitch and lack the structure you need to measure long-term value or guide strategy.

I think there are 3 main reasons for this:

1. **Complexity and Uncertainty Inherent in Technology:**
Real-world IT systems and modern applications are extraordinarily complex - it's tough to precisely model the cost and value of every single existing and future component (since the data usually isn't collected in an easily consumable way), let alone dial in every risk and benefit of actually executing the project. A McKinsey study found that 70% of digital transformations fail[^2], and I've been around long enough to see what a monumental effort it takes to prevent that failure. The consequences of breezing over execution can be total failure and a leadership overhaul[^3]. On top of all of this, tech moves fast: innovation cycles and competitive pressures cause leaders to make decisions under tight time constraints - there is a high risk of being disrupted or counter-positioned so leaders also need to rely on a certain amount of vision and intuition to quickly make a decision. In the time it takes to conduct a thorough due diligence analysis of thousands of workloads, you might miss a market window and the juice (the results of the analysis) may not be worth that squeeze. As an SA, one of the most asked questions I get is: what are other similar customers doing and how is it going? It's a good question, and an attempt at shortcutting this painful process.

2. **Vendor-driven Projects:** Many projects I see are selected based on whichever vendor can pitch most persuasively. This is a bit of a roll of the dice since a lot hinges on the vendor's ability to sell and if it is selected based on pure cost-competitiveness, presents risks. A good partner should be able to explain assumptions clearly, does the hard work to collaborate with customers to align to strategy and create as rigorous a model as possible. Without this type of expectation (a kind of negotiation really) it's difficult to arrive at a realistic solution and you risk overpromised benefits and underdelivered results. During my time in consulting, I saw plenty of pre-sales dreams that turned into implementation nightmares - it was not uncommon for me to be the third or later wave in a revolving door of consultants trying desperately to right the ship.

3. **Fear of Accountability:** Given the dangers inherent in 1 and 2, vendors live on a knife edge of trying to win the project but also trying to avoid committing to concrete projections since they could be held accountable for unpredictable outcomes and factors that are hard to measure to begin with. The pain the customers and vendors are trying to avoid is finger-pointing if the project fails to deliver on those promises. The result is a lot of ambiguity and an environment more full of vibes than locked-in numbers (besides available budget) and this can limit future innovation, investments, and a strong foundation to pivot from when strategies evolve.

Deciding to live with these reasons and accepting this ambiguity means that your organization doesn't improve its decision-making mechanism when you **inevitably have to make another tech investment in the future**.

## **Financial Modeling Basics**
In contrast, when a company generally makes an investment, they apply some financial tools or metrics to appraise whether or not something is worth pursuing. From buying a soccer team (don't do this[^4]), to purchasing a factory or acquiring another company, this is typically what is done. Here's a crash course from a business standpoint (and across my interactions from developers to managers to directors to VPs to the C-suite, something I've surprisingly never seen). Could be that I'm too low on the totem pole though.

The first basic concepts are using **cost of equity** and **cost of debt** to come up with a **Weighted Average Cost of Capital (WACC)**. What the company needs to return from an investment to satisfy shareholders (those that bought shares of your company) is **cost of equity** and what they need to satisfy debtholders (those who lent you money) is **cost of debt**. The company should use both of those to calculate **WACC** or the hurdle rate, which is the average rate that the company should earn on any new project to figure out if you are adding or destroying value. You can factor in taxes to make this even more accurate.

$$
WACC = \frac{E}{V} \cdot Re + \frac{D}{V} \cdot Rd \cdot (1 - Tc)
$$

Where:
- \( E \): Market value of equity  
- \( D \): Market value of debt  
- \( V = E + D \): Total value of capital (equity + debt)  
- \( Re \): Cost of equity  
- \( Rd \): Cost of debt  
- \( Tc \): Corporate tax rate

And voilà - in this simple example you have **WACC**, your hurdle rate, or minimum acceptable rate of return. Typically any project that can return more than this WACC percentage number should create value for the company.

WACC will be the basis of your **discount rate** used in calculating the value of your tech investment.

If you are a finance nerd, you might adjust this **discount rate** if the risk is higher (add a risk premium!) or lower (discount this further!), but if you have a standard WACC as the benchmark, you can just use that as a baseline. However, this is just one piece of your investment puzzle.

So what about the project itself? To understand the value, you can figure out the expected yearly **cash flows** of the project, then discount them with a **Net Present Value (NPV)** calculation.

To get the **cash flows**, this is where you make a lot of assumptions about how much revenue you would generate (and how) as well as what costs you would reduce. Combine that altogether to estimate the yearly **cash flows** of your project.

You can then apply the **NPV** formula to figure out what all those cash flows are worth in today's dollars over a period of time. You have to remember to factor in your up-front investment, and if you want to be really specific, bake in growth assumptions during the initial year(s) and the terminal value near the end of the period of your project (if it makes sense to do so). 

The basic Net Present Value (NPV) formula is:

$$
NPV = \sum_{t=0}^{n} \frac{C_t}{(1 + r)^t}
$$

Where:
- \( C_t \) = Cash flow at time \( t \)
- \( r \) = Discount rate
- \( t \) = Time period
- \( n \) = Total number of periods

After you set up your NPV formula, you still have to figure out if the **Internal Rate of Return** (**IRR**, the rate that makes the NPV = 0) is greater than or less than your **WACC**. 

- If **IRR > WACC**, then your project beats the company's average **cost of capital** (other way to call **WACC**) so it makes sense to go ahead. 
- If **IRR < WACC**, your project will probably not make sense, unless there is some other intangible strategic goal that you haven't factored into your calculation.

By the way, trying to set **NPV = 0** just means that you imply that the cash inflow and outflows will be equal. So that would represent the project's intrinsic rate of return. 

Additionally, you might want to calculate some top-level numbers like **Return on Investment (ROI)** over a certain period of time and understand when your investment breaks even. At this point you're slicing and dicing similar concepts.

Clearly there are a lot of assumptions involved, especially due to the complexity/uniqueness of tech projects, so in the next section, I'll propose a balanced, step-by-step analysis approach.

All of this to say... pure business analyses is not sufficient - if you treat technology projects and teams as widgets, you ignore factors like tech debt, execution risk, and have a glaring hole that can lead to failure, regardless of your model. Not treating tech debt seriously often comes because you are paralyzed by how much to invest in fixing things (seen as low value) versus releasing new features to the point where your operations slows (or as I have seen) grinds to a halt. There's a great article about the importance of tackling debt[^5] and worth a discussion, but outside the scope of this current post. 

And when it comes to just building these financial models, there are a lot of pitfalls[^6] you need to avoid and ultimately you still need to weave this all together in a narrative that is built on an informed vision and intuition[^7].

## **Balancing Analysis and Vibes for Tech Decisions**
So if the soft tech estimate is not enough and the pure business calculation is too in-the-weeds and falls apart under the weight of assumptions, what can we do?

Ultimately, the core question when it comes to valuation is: **do I invest or not?** And this is based on the question: **if I invest, what do I expect to return from this investment?**

And in addition to just the pure valuation, you also have to take into account whether this **aligns with a good strategy**[^8]. What problem will this solve for me at an organizational level - and based on competitive dynamics, will this help me in the long run? For instance, how might it reduce my costs, grow my revenue, improve my moat? 

Many pitches fall short of addressing these fundamental questions. The costs are too broadly assumed, revenue gains are glossed over and the ties to strategy are vague. While it's reasonable to expect that the immediate benefits are hard to measure, I do agree with the sentiment that, ultimately, "if there are no benefits, then the investment is not strategic".[^9]

# **The Idea of Option Value Over NPV**

I came across an article by Rita McGrath, a Columbia Business school professor, who advocates for an approach where you focus on **option value**[^10] and flexibility instead of trying to project cash flows too far out in the future right off the bat. She calls out the shortcomings of NPV analysis in tech projects which can be too rigid since it can omit uncertainty and strategic potential.

What she calls out actually resonates with the way I've seen my colleagues and go-to-market teams position tech projects, which is to start with a pilot, which reduces risk by capping your initial investment losses, then using your learnings to make subsequent decisions. Additionally, Rita applies the concept of **Expected Value (EV)** to assign probabilities to those decisions. 

The key principles are to:

1. **Start small and scale** - pilot smaller projects with a targeted set of personas, scope, and well defined goals to demonstrate value and then expand to other use cases or teams
2. **Measure leading indicators of success** - non-financial metrics as proxy to show that value: this could be adoption rates, increased customer retention, reduced churn, higher Net Promoter Scores (NPS) or Customer Satisfaction Scores (CSAT) that can be tied to the project, etc.
3. **Prioritize investments that allow you to adapt** - aim solutions that allow you scale and pivot

After the pilot phase, you should be in a better place to take a stab at the cash flow projections. Although leaning on EV is great for flexibility, I still think the rigor of NPV analysis can be effectively combined with this approach to validate a project's long term potential and to  create a data-backed narrative to hold it all together. You can continue to scale incrementally to minimize risks, creating insights along the way to validate your approach. And I think the only way you can consider your potential options over time as you scale up is to model what you know, so you need this foundation and data collection process.

# **Example: Applying Real Options Thinking to a Cloud Migration**
Bringing these complex ideas in a simple example helps, so suppose your company is thinking about migrating to the cloud.

The first step might be to consider a small pilot project - for example, spending $200k to migrate a business critical application to the cloud. You might have to do a bit of bottoms-up estimation to break down cost of database workloads, application hosting costs, etc. to try to estimate value. 

You can try to lean on industry analyses as benchmarks from sources like the IDC[^11] - for instance, 10-15% revenue uplift and 30% faster time-to-market from cloud migrations is nice to know. Benchmarks can show that you are moving in the right direction, but it's still important to put a plan in place to track data points and detect improvements because **you are not necessarily the industry average**. From the top-down you use the industry benchmarks and tools that lean on those benchmarks to serve as a sanity check[^12]. 

The pilot phase mitigates risks by letting you test without committing your full budget up front. During this time, you can assess the app performance in the cloud and see how your leading **Key Performance Indicators (KPIs)** are doing. You can use this information to extrapolate the long term benefits and find concrete ways to determine a mid-term and long-term NPV. 

Data points that inform the initial model include the cost of running the on-premises data center (DC). For example, $500,000 per year in energy, maintenance, staffing, depreciation costs. Perhaps there is a hardware refresh of about $1M every 5 years or so. 

Understand the cash flows from the project by using the savings between on-premises cost and the annual cloud cost. The first cut at this may be tough but should include factors like:
- Initial migration costs for year 0
- Cost of cloud cost growth in the near term and long-term (terminal). 
- Consistent efficiency savings (X% in tasks and calculate savings in $/hour of salary)
- Potential revenue generating tasks

After the pilot stage (and really at every subsequent stage), you have 3 different decision points/options:
1. **Scale** out your initiative: pick another group, business unit, etc. to expand (assign some cash flow value to this)
2. **Adjust** the approach: you determine that you could benefit from taking a different approach to the migration[^13] and this has a different assigned cash flow value
3. **Terminate** the project: in this case, you've capped your initial investment losses.

You can use the **real options** approach using probabilities to calculate an Expected Value (EV). The benefit of this is that you can use this knowledge in the future for more decisions.

Example:
- Success Probability could be 60%
- Partial Success Probability could be 30% and you learn how to adjust
- Failure probability might be 10%

So:

$$
EV = (60\% \times $240,000) + (30\% \times $100,000) + (10\% \times (-$200,000))
$$

Simplifying:

$$
EV = $144,000 + $30,000 - $20,000 = $154,000
$$

You have the ability to expand or adjust based on the information. As part of this exercise, you'll likely identify areas where you do not have the data, but then this is time to get those processes and tools in place. 

This approach balances NPV and EV with some flexibility. It helps you manage risks and also better link the project to your business goals and this staged investment is based on data which cap your downside risks. Beyond the pure financials, the pilot and scale approach gives you the opportunity to learn, to build your capabilities and create a baseline to scale sustainably in the future. You now have the opportunity to make informed decisions based on probabilities instead of rigid projects so that you have room to maneuver.

As you get better data using all the tools and metrics at your disposal, construct the NPV and the narrative to create a better tie to long-term value. 

## **Closing Thoughts**
Customers struggle with performing their own exhaustive modeling (IRR, NPV, ROI) in-house because it takes a lot of effort, time, requires deep-expertise, and might still fall short of the accuracy that they want, versus taking a quick cut at some estimates, looking at the benchmarks and then just "doing the thing". The nature of tech means that some drawbacks of pure NPV analysis[^14] are amplified. I'll admit that what I propose seems tough to do and I don't blame anyone for not trying.

For truly big acquisitions (valued in the billions), companies will bring in a third party to conduct the transaction (valuation, due diligence, arbitration/negotiation, etc). However, even tech projects can benefit from a similar type of discipline. By blending strategic alignment, all the analytical tools at your disposal, and incorporating flexibility with real options thinking, I think there is a way forward to minimize uncertainty and to realize measurable value for tech projects.

I believe that there is a sweet spot that exists where you can combine strategic thinking, financial rigor and flexibility through real options thinking. If you start with pilots, track carefully designed metrics, and iterate based on information and insights you pick up along the way, you can set up a roadmap towards sustainable success. For additional information, there's a great resource on Educause that goes through a similar framework in great detail[^15].

What are your experiences with tech investments? Do you rely more on intuition, financial models or mix both?

[^1]: *If you really want to know: automotive, industrial manufacturing, e-commerce, consumer electronics, aviation, state entities, non-profits, education, healthcare (admittedly, some of these industries overlap)*
[^2]: [McKinsey: Why do most transformations fail?](https://www.mckinsey.com/capabilities/transformation/our-insights/why-do-most-transformations-fail-a-conversation-with-harry-robinson){:target="_blank"}
[^3]: [Bloomberg: Sonos CEO Leaving After Failed App Revamp Led to Customer Revolt](https://www.bloomberg.com/news/articles/2025-01-13/sonos-ceo-patrick-spence-leaving-after-failed-app-revamp-led-to-customer-revolt){:target="_blank"}
[^4]: [Modern MBA: Why Football is Bad Business](https://www.youtube.com/watch?v=s7N-xXGgdE4){:target="_blank"}
[^5]: [McKinsey: Breaking Tech Debt's Vicious Cycle](https://www.mckinsey.com/capabilities/mckinsey-digital/our-insights/breaking-technical-debts-vicious-cycle-to-modernize-your-business){:target="_blank"}
[^6]: [Aswath Damodaran: Myth 1 - DCF If you Have a Discount Rate](https://aswathdamodaran.blogspot.com/2015/02/dcf-myth-1-if-you-have-ddiscount-rate.html){:target="_blank"}
[^7]: [Aswath Damodaran: Myth 2 - DCF is Exercise in Modeling](https://aswathdamodaran.blogspot.com/2015/08/dcf-myth-2-dcf-is-exercise-in-modeling.html){:target="_blank"}
[^8]: [DistributedSoup: What is Strategy?](https://distributedsoup.com/strategy/2025/01/01/strategy1.html){:target="_blank"}
[^9]: [CFO.com: When Projects Have a Zero or Negative NPV ](https://www.cfo.com/news/when-projects-have-a-zero-or-negative-npv/660037/){:target="_blank"}
[^10]: [Rita McGrath: NPV Doesn't Work... Here's a better approach](https://www.linkedin.com/pulse/npv-doesnt-work-risky-high-potential-projects-heres-better-mcgrath/){:target="_blank"}
[^11]: [IDC Whitepaper: The Business Value of AWS](https://pages.awscloud.com/rs/112-TZM-766/images/IDC-Whitepaper-The-Business-Value-of-AWS-Global.pdf){:target="_blank"}
[^12]: [AWS: Create a Data-driven migration business case](https://aws.amazon.com/blogs/mt/create-a-data-driven-migration-business-case-using-aws-cloud-value-framework/){:target="_blank"}
[^13]: [AWS: 6 Strategies for Migrating Applications to the Cloud](https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/){:target="_blank"}
[^14]: [Investopedia: NPV Disadvantages](https://www.investopedia.com/ask/answers/06/npvdisadvantages.asp){:target="_blank"}
[^15]: [Educause: IT Infrastructure Projects a Framework for Analysis](https://library.educause.edu/-/media/files/library/2014/7/erb1408-pdf.pdf){:target="_blank"}


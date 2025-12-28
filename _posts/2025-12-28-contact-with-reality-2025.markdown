---
layout: post
title:  "What Survived Contact with Reality in 2025"
date:   2025-12-28
categories: [reflection, career]
---

The past year was a pretty intense reset that forced me to stress-test my belief that advisory credibility can naturally preserve execution sharpness. I paused writing for a while to absorb what part of this actually held up and sit with what changed.

## Execution First, Abstraction Later
I began my career with a heavy execution bias. Over the past few years in sales engineering, my work shifted closer to advisory conversations. That distance improved my leverage, but I wanted a real test to prove I could still ship the things I was recommending.

When I found an opportunity to perform rapid prototyping work at AWS, I jumped in with small team that moved fast, broke things, and delivered working protoypes. The pace stripped away abstractions quickly. Ideas that sounded clean in decks immediately ran into reality: security constraints, integration debt, unclear ownership, and edge cases that made AI systems behave unpredictably. 

Most high-level conversations about AI and systems aren't bottlenecked by interesting ideas (though shaping the approach is critical), but by unglamorous details required to actually make the systems work reliably.

This work was rewarding, but I also realized high-intensity prototyping, for me, is better as a powerful learning mode than as a place where I can sustain assymetric, long-term impact.

I continued pushing discomfort by taking on more interviewing roles and booting up an AWS Twitch program where I and a small team designed IoT systems at enterprise scale while answering live questions on the fly within our open-ended format.

## Interviews, Gaps, and a Forcing Function
After that stretch, I entered a long, harrowing and humbling interview process that exposed real gaps but also rebuilt parts of my foundation.

I hadn't interviewed seriously in over four years and assumed my experience could carry me. That was not the case. I flopped out of the gate, whiffing questions I should have cleanly handled. It was a reminder that I needed to be intentional about how I articulate things, not just understanding them. Interviewing skills can atrophy without deliberate practice.

One prompt was open-ended: *build something interesting with AI.* 

I started by building a functional chatbot combining Salesforce and Jira data, deployed via containerized MCP servers. I cut off the prototype once I hit the core use cases, and reasoned how this could be productionized (https://github.com/btang01/mcp-sf-jira). 

After that, I slowed down and hand coded agentic loops from scratch to understand how schemas, memory, and control flow actually influence LLM behavior  
(https://github.com/btang01/claude-basics).

In one interview, I stumbled when asked to reason clearly about concurrency: how async systems behave, how work is scheduled, where coordination breaks down. It wasn’t a trick question but it exposed a gap between intuition and explanation. I also stumbled on system design and realized that I needed to reboot my design rigor.

Rather than hand-wave it away, I turned it into a forcing function. I put together a small reference repository (https://github.com/btang01/asyncio-basics) to make concurrency explicit instead of implicit. I walked through patterns end-to-end: sequential execution, task-based concurrency, gather, structured concurrency with TaskGroup (Python 3.11+), futures, and synchronization primitives like locks and semaphores. 

Doing this forced me to slow down and answer questions that I'd previously glossed over including what concurrency is, what it looks like, common failure modes and why this matters so much for AI systems. Agents aren't just interesting because of reasoning or tokens they generate - they run concurrently, share resources, fail independently and require coordination without collapsing into chaos.

In the end, this work mattered more than interviewing. It sharpened how I think about security, orchestration, reliability, and memory. This helped in two ways: I was able to help my customers navigate ambiguity in a new space, and now I know what frameworks like Strands SDK and ADK can effectively abstract versus what they don’t.

## Moving On
When the GCP Customer Engineer role came together, I took a brief pause. I kept things intentionally ambiguous so I could offload knowledge, close loops and leave cleanly. This period reminded of how many people at AWS that I learned from, worked alongside, and genuinely respect.

When a travel window opened up, I had access to unstructured freedom for the first time in years with no destination constraints, timing or pace. Surprisingly, I found out that there’s always a reason not to go anywhere. Weather forecasts always felt bad, plans always felt suboptimal and waiting or even doing a staycation seemed more optimal. It surprised me that unlimited optionality actually created more unexpected friction.

In the end, I stopped optimizing, ignored the forecasts and booked a trip to Southeast Asia anyway. I chose motion over endless evaluation and was really happy with the result. This reminded me how easily freedom can just turn into inertia when every option is open and how progress only happens if you accept imperfect conditions and just choose to do something.
 
## Wandering, Then Hitting Limits
I spent time wandering without much agenda, walking streets and parks in Hanoi, watching daily routines unfold, eating street food, sitting longer than necessary. It wasn’t profound in a cinematic way and it was a reminder that most of life runs without demanding commentary or analysis.

That calm contrasted sharply with what followed. I rode motorcycles through Ha Giang and swam in waterfalls, which is a beautiful, chaotic experience. Being the “older guy” on the backpacking trail, singing karaoke badly, and playing pickup soccer in flip-flops all landed the same way: letting go of optimization and choosing participation instead. 

After that I immersed myself in training Muay Thai hard twice a day, pushing myself and re-igniting old mechanics and my love for the sport.

When I came back, I didn’t really rest until a staph infection forced stillness. No lesson there beyond a simple one: limits exist whether or not you acknowledge them.

I'm excited about my new role and tried to hit the ground running, bringing together past experience but also trying to respect a new culture. My working definition of Googliness, for now, is simple: be intellectually honest, rigorous, and collaborative so we can build meaningful outcomes for customers.

## What to Hit in 2026
There are a few things I want to put into motion next.

### Agentic systems closer to reality

I want to build beyond isolated Docker demos toward Kubernetes-based patterns—fleet-level services, hybrid deployments, and ADK-style frameworks that support long-running, resilient AI workloads without becoming fragile or prohibitively expensive.

### Tackling hidden infrastructure constraints

Many of the customers I work with operate in the physical world. Cloud-only narratives break down when latency, bandwidth, autonomy, and resilience matter. Running intelligence closer to where the business operates forces clearer thinking about tradeoffs. Reality punishes hand-wavy diagrams, and tooling hasn’t fully caught up yet.

### Finance as an Explanatory Layer
I also want to spend more time writing about finance. Rather than hot takes, lean on first-principles thinking. Balance sheets, equity, leverage, cash flows, and how capital structure shapes which companies get to survive long enough for their ideas to matter. That kind of grounding feels increasingly necessary, especially in cycles dominated by memes, financial nihilism, and simplistic narratives. 

## Why Write?
I’m writing again because it helps me distinguish productive complexity from unnecessary friction. This blog is a way to finish thoughts instead of carrying them around half-formed. Writing is how I test whether an idea survives contact with reality. If it doesn't, it probably shouldn't guide decisions, whether it's mine or anyone else's.

<style>
  ul, ol {
    margin-left: 1.2em;
    list-style: initial;
  }
</style>
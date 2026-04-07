---
layout: post
title:  "Productionizing AI, Starting with Identity"
date:   2026-04-06
categories: [tech]
---

From what I've observed working with multiple enterprise customers, the biggest gap for AI adoption is converting proof-of-concepts into production workloads. 

This isn’t a hot take, but if you spend a few minutes on this, I think there’s useful field insight here if you plan on generating business value out of your AI project.

Productionizing AI spans security, scaling, resilience, performance, observability, memory, and cost tradeoffs. Each of these is a beast in its own right.

All of these matter, but I want to focus on the most common and central problem that explains why your AI system may never make it past your security review: **How do you let the AI run autonomously while preserving the level of governance that enterprises need to prevent unintended, negative actions?**

AI systems fail here because identity gets lost somewhere between the user and the actual actions that need to be taken. If that is messy, then everything breaks: governance, auditability, and trust in the system. 

The key to overcoming this challenge is to design a system that supports the basic security principle of least privilege. Each action the AI system takes should be easily auditable, and at the point an action needs to be taken, it should only be able to do exactly what it's allowed to do without god-mode access across all services.

I believe that once you've designed a scalable, auditable way to handle identity, you can set the AI loose and have the functional guardrails you need to ramp with confidence. 

However, this becomes especially challenging in enterprise environments, where governance has to span a fragmented landscape of existing systems, APIs, and data boundaries. At a minimum, we need a **unified identity layer** where users can authenticate once, and access is consistently enforced across downstream systems through a central identity provider.

## What Goes Wrong in the Field
If you look at reference implementations from frontier AI companies and hyperscalers today, they're optimized to get a proof-of-concept working quickly. You’ll often see patterns like “just use this API key.” That’s fine for a demo, but it breaks down immediately in real systems that need to support hundreds or thousands of users across multiple services. To be fair, teams have noticed and are starting to move away from this, even if it hasn't shown up in public repos yet.

It's a solvable problem that I think is often underemphasized right now. Some might also say this is a trivial, solved problem, but it's also not that easy since very few (if any) companies have a perfect identity setup. Building an agentic solution on top of this is bound to result in some headaches.

The full benefits of AI are realized when you give it the ability to understand provided business context, a massive library of tools to let it do things, and let the creativity and intelligent logic of the LLM figure out what order to use those tools in to solve complex problems. The more up-to-date and rich pool of information you expose to the service, the better the results. But this level of autonomy and access requires trust first.

## Starting Assumptions
Every business has its own slightly different variation of identity management, but the baseline usually looks something like this:
- You already have an **identity provider** (**IdP** like Entra, Okta, etc.)
- You use the **IdP** to **single-sign on (SSO)** across SaaS apps
- Your **IdP(s)** serve as the source of truth for users, groups, roles (for access)

If you're building an agentic AI system, you need that identity to carry through into your cloud environment where your app likely lives, your AI orchestration layer and also every downstream system that this AI system touches. That cloud-based system needs to be able to sync up the access so that the AI service can act **on behalf of (OBO)** each user with the right actions and the right level of access to complete the job.

For the AI system, I'm thinking of a more straightforward, intuitive chat UI with users that in the backend could support retrieval augmented generation (RAG), access to tools to make text-to-SQL calls to other systems, or API calls to retrieve the right up-to-date data from data warehouses or SaaS applications. Let's leave other use cases, like agentic coding harnesses out of the discussion for now.

## Five Rules that Matter the Most
From what I've seen, there are a few principles you can't compromise on here. Most of these are well-tread security principles.

1. **No shared API keys** - a scalable AI service in the cloud should follow a cloud native design and generally that means that each request should be tied to a user or a service acting on behalf of a user.

2. **On-behalf-of (OBO) or delegated access** - the AI should act as the user not as itself so you always know who authorized an action and which part of the system executed it.

3. **Per-tool authorization** - the AI can only do the thing that the user is allowed to do in a particular system. This prevents the god-mode access that people should rightly be nervous about. It limits blast radius of actions.

4. **Short lived, scoped credentials** - this is a common one, but by granting ephemeral, limited-access tokens, we are able to limit lateral movement if something goes wrong.

5. **Audit everything** - with your design above, you should log all actions with the user, tool, timestamp and outcome. Not only does this help with troubleshooting, collecting the data well can allow you to feed machine learning models to improve the AI system.

## A Common Identity Scenario
Most customers I work(ed) with run their cloud workloads on a single hyperscaler and already have an existing identity provider that is used as a way to SSO across systems like ServiceNow, Jira, Salesforce, etc. 

Since I also interface with manufacturers and logistics companies, the surface area changes a lot. They'll require people in factories and warehouses, beyond corporate users, to access this AI system. This includes operators in these sites, as well as external partners accessing a public web interface to, for example, chat to get insights about their relevant inventory. 

The point is, if you've built a valuable service that can quickly help operators limit downtime by troubleshooting or detecting problems faster, then you want it to roll out as fast as possible to as many operators and sites as possible to maximize its impact.

As a result, you're managing external and temporary identities for partners and operators on top of your corporate identities. Sounds overwhelming maybe, but let's dive in.

## Start with the Identity Provider
The **IdP** is usually already set up as the anchor. It handles authentication, centralizes access control, and gives you a consistent way to manage users and groups, but it doesn't solve the full problem.

What you actually need is for that identity in the IdP to become enforceable inside your cloud environment. This means you have to map the users and groups from the IdP into the cloud's IAM system so that the permissions are evaluated at request time and not inferred somewhere upstream.

On Google Cloud, this is typically done with **Workforce Identity Federation**, which lets you map external identities cleanly into IAM without needing to duplicate them. 

It's also worth it to be clear about the boundary between **authentication** and **authorization** here. IdPs handle authentication well, which tells you who the user is. Authorization determines what they can do, and that's what still needs to be enforced across your systems.

At a high level, the goal is simple: users authenticate once, access is managed centrally, and group membership becomes the source of truth for what actions are allowed. This is convenient, but more importantly, it derisks the company by providing control and consistency.

For AI systems, this matters even more because identity can’t just stop at login. The system needs to carry that identity through, act on behalf of the user, and enforce permissions wherever actions are executed.

That’s why you don’t want to constantly reach back into the IdP at runtime. Instead, identity needs to be translated into something the cloud platform can enforce directly. Once the user is authenticated, their identity should be tied to real, enforceable permissions in every system the AI interacts with.

## A Side Note on Other Google Identity Topics
You may also come across Google Cloud's **Workload Identity Federation**, which is useful for allowing external services or infrastructure to securely access cloud resources without long-lived credentials. While important, it solves a different problem of service-to-service authentication rather than user-driven, on-behalf-of access, so I’m intentionally leaving it out here to stay focused on user identity and delegated execution.

You might also reach for **Google Identity Platform**, especially if you’re dealing with external users or multi-tenant access. It’s great for handling login and normalizing identity across providers. But it doesn’t solve the harder problem of how that identity is enforced when the AI starts taking actions, so I’ll keep the focus away from this. This acts as an application-facing identity layer and it handles login, user management, and federation across multiple identity providers. But it’s important to understand what it does and what it doesn’t do. It handles authentication. It does not enforce permissions across your systems. That still needs to be handled by your underlying IAM layer.

## A Practical Architecture
The pattern that tends to work here is modular. This is partly opinion, but the more hyperscalers build this into managed services, the easier this gets over time.
At a high level, you can think about it this way: **UI → Auth boundary → Orchestrator → Credential Access Broker → Services → Agents → Tools**

Each layer has a clear responsibility:
- **UI:** receives the user request and carries user identity/session context
- **Auth/App Boundary:** establishes who the user is (e.g. via Workforce Identity Federation) and gives the rest of the system a validated identity to work with.
- **Orchestrator:** decides workflow of which domain service, which agent, which tool should field the request. It may even interact with a RAG service to refine the question before passing it downstream. It can determine things like which LLM to use to start with the question. It coordinates multi-step execution to serve good responses to the user. It should not own long-lived credentials.
- **Credential Access Broker:** this is the service that owns access by taking user context and turning it into narrowly scoped, short-lived credentials for specific actions. Basically it centralizes all the messy authorization logic.
- **Domain Services / Service Abstractions:** this is just a way to organize business logic, hide backend complexity, and give the orchestrator a cleaner interface than talking to every agent/tool directly. Early on, you'll likely skip this and use agents. Introduce this layer as things grow.
- **Agents:** these perform reasoning, serving as experts in their own domain with customized system prompts and other agent-y enhancements. They decide which tools they need. This should not be the place where broad authority lives and because we use a CAB, we're able to achieve this separation.
- **Tool Servers:** execute concrete actions and receive only temp scoped access tokens, thus enforcing narrow action boundaries
The important detail is what happens at the boundary. The user logs in once, identity is validated, and from that point on you’re not passing that identity token everywhere. Instead, at runtime, the system derives short-lived credentials for each action based on stored authorization grants.

For internal users on Google Cloud, this typically builds on your existing IdP setup using Workforce Identity Federation. That lets you map enterprise identities directly into IAM without duplicating users, and enforce permissions at the resource level.

## The Credential Access Broker (CAB)
It makes sense to split this out into a separate service that I'll call a **Credential Access Broker** service or **CAB**. This is where the real work happens.
Instead of letting every agent figure out authentication on its own, you centralize it in one place. The CAB holds the authorization grants for downstream systems and is responsible for turning those into usable credentials at runtime.

In practice, that means:
- You have a **user identity token** from the **IdP** that proves who the user is
- You store an **authorization grant** per downstream system (like an **OAuth refresh token** or some equivalent trust)
- At runtime, the **CAB** exchanges that for a short-lived scoped **temp access token**
- Only that **temporary access token** is passed to the system actually doing the work.

The original user token stops at the boundary. It’s validated once to establish identity context, and everything after that runs through controlled token exchange.

This avoids spreading credentials across the system, keeps authorization logic consistent, and makes the whole thing much easier to audit.

There’s also a practical UX benefit. You don’t want users clicking through a dozen OAuth consent screens just to get basic functionality. In most enterprise setups, you register the AI system once as a trusted integration, approve scopes at the org level, and assign access via groups and roles. Tokens are still issued, but the consent is pre-approved, which makes multi-system workflows actually usable.

## An Example
**Workforce Identity Federation** lets Entra/Okta users access GCP without separate Google Identities. It maps users/groups into **GCP IAM** so permissions can be enforced directly on resources like **BigQuery, Cloud Storage** or internal APIs. If your AI system touches a GCP service, those services will respect user-level permissions.

On the SaaS side, you typically register your AI system as a trusted integration. For example, in Salesforce you create a Connected App, define OAuth scopes, and establish trust so the system can request access on behalf of users.

In parallel, you’ll often configure Salesforce (or similar systems) in your IdP for SSO, so users can log in directly and their identity remains consistent across systems.

The **CAB** sits in the middle of all of this. It holds the authorization grants, like OAuth refresh tokens or equivalent enterprise trust, and uses them to mint short-lived, scoped access tokens at runtime. Those are the only credentials that ever get passed to the systems doing the work.

This is what keeps authorization centralized. Instead of every agent handling auth on its own, all access relationships are managed in one place, with consistent enforcement and clear auditability. Without that, you end up duplicating logic, spreading credentials across services, and losing control of who can do what.

A Salesforce workflow might look like this:
1. User asks AI to update a record
2. Orchestrator routes request
3. CAB looks up Salesforce grant
4. CAB mints short-lived token
5. Tool server calls Salesforce
6. Action logged with user + AI + tool + timestamp

## Open Standards
My proposed architecture, particularly the **CAB**, can be implemented on top of open standards like **OpenID Connect (OIDC)** and **JSON Web Tokens (JWTs)**. These standards already have a strong foundation for identity, allowing systems to issue cryptographically verified tokens that carry user identity and claims.

In a mature system, downstream tools would be able to directly trust and validate tokens issued by your system through standard OIDC discovery and JWKS endpoints. Instead of managing API keys or bespoke integrations for every tool, systems could rely on short-lived, verifiable credentials that encode both identity and scoped permissions for a specific action.

In this design, the **CAB** effectively acts as an OIDC-compliant **Security Token Service (STS)**. When the orchestrator determines that an agent needs to call a tool, it requests a token from the **CAB**. The **CAB** uses the underlying user authorization grants to mint a short-lived **JWT**, scoped to the specific action.

The downstream tool can then:
- validate the token cryptographically using standard OIDC discovery mechanisms
- verify the issuer and signature via JWKS
- inspect claims to determine the user, the calling service, and the allowed scope

This creates a clean, interoperable model where identity and authorization are portable and verifiable across systems.

In practice today, this pattern is only partially supported. While OIDC and JWTs are widely used, most SaaS systems still rely on their own OAuth flows and don't natively accept externally issued tokens for delegated access. As a result, parts of this architecture, particularly the credential broker and token exchange, are often implemented manually as a control layer on top of existing standards.

## Final Thought
I realize we don't live in a perfect world where if everything locks in like described here, the code is straightforward (you're implementing syncs and token handshakes).

Focus on the golden path instead of trying to support every variation of identity upfront. Start with a defined subset of users and a limited set of systems where identity, authorization, and auditability can be implemented cleanly end to end. From there, you expand coverage incrementally rather than waiting for the entire enterprise identity landscape to be perfect.

Lastly, now that you understand the principle of this design, hopefully you can appreciate why hyperscalers are investing heavily in identity-aware agent frameworks and OIDC-based patterns. The goal is to make this entire layer of identity propagation and enforcement something you don’t have to rebuild from scratch, or to maintain. 

These opinions are my own and do not reflect the opinions of my employer.

<style>
  ul, ol {
    margin-left: 1.2em;
    list-style: initial;
  }
</style>
---
layout:     post
title:      "Who Is Your Customer?"
subtitle:   "Customer relief is impact"
description: "Engineering impact should be measured by customer relief, not only dashboards, migrations, or cost savings."
date:       2026-05-24 00:00:00 -0700
author:     Xiao
header-img: "img/post-bg-universe.jpg"
catalog: true
tags:
    - Engineering
---

More engineers are learning to measure impact. That is a good thing.

We should not define engineering value only by code quality, technical difficulty, or how much complexity we can handle. Craftsmanship matters. Leadership matters. Execution matters. But engineers should also be able to answer: what changed because of this work? Did we save money? Reduce latency? Fix incidents? Support growth?

The problem is that impact metrics can look good while customers are still suffering.

A platform can save millions and still make every user take a detour. A system can reduce P0s and still be impossible to debug. An internal tool can show great adoption while the people using it need ten pages of docs, three owners, and five layers of abstraction to do something simple.

That is when we need to ask a more basic question:

**Who is your customer?**

## Impact is not customer value

Engineering impact is often measured by what is easy to count: cost saved, latency reduced, traffic migrated, incidents closed, users onboarded.

These metrics matter. But they are not the same as customer value.

This is especially true for internal systems and infrastructure. The real customer is often not the person approving the roadmap or reading the quarterly review. It is the engineer who must use the system every day, the on-call engineer paged at night, or the product team trying to ship through a platform they did not choose.

Internal tools have a monopoly by default. If an external product is painful, users leave. If an internal platform is painful, users usually endure it. The pain becomes hidden organizational tax: Slack threads, debugging sessions, onboarding delays, meetings, exceptions, and local workarounds.

The infrastructure team suffers too. Many internal infra teams are treated as cost centers. They are understaffed, yet asked to support more products, more legacy systems, more migrations, more edge cases, and more on-call burden every year. They must deliver visible impact while spending most of their time keeping the lights on.

So a team can be busy, important, and objectively delivering impact, while both the team and its customers become more miserable over time.

## How systems drift

Most internal platforms are not designed from first principles. They grow under time pressure, business pressure, and historical constraints.

To deliver impact quickly, teams often build on open source software. That is usually the right move. But each project comes with its own assumptions and failure modes.

When multiple systems that were designed separately are stitched together and plumbed into legacy infrastructure, many trade-offs collapse into one sentence:

**Make it work.**

At the beginning, this is reasonable. The migration needs to happen. The incident needs to stop. The cost needs to come down. The MVP needs to launch.

But if the system never returns to the design question, it begins to drift.

The first integration gap gets covered with glue code. The next gap gets wrapped in an adapter. The next gap gets hidden behind an abstraction. Eventually, nobody really understands what is happening underneath.

Abstractions are necessary. Good abstractions reduce complexity. Bad abstractions move complexity somewhere else.

Every layer has a cost: users learn more concepts, maintainers remember more exceptions, performance takes more hops, and every moving piece needs owners, docs, SLOs, and incident playbooks.

After enough layers, the system stops scaling, not because any single component is weak, but because the whole thing has become too hard to understand, predict, and change.

## The human layer of technical debt

Technical debt is also about people and memory.

At the founding stage, the original engineers know why the system exists, which choices were intentional, which were MVP shortcuts, and which parts were meant to be revisited later.

Then people move on. Teams reorganize. The project shifts from build mode to maintenance mode. The new owners inherit the code but not the full context or mandate. They can fix bugs and support users, but they often cannot rethink the design.

Temporary workarounds become permanent architecture. Short-term decisions lose their historical explanation and become constraints. The system becomes harder to change not because nobody cares, but because the people maintaining it are trapped inside decisions they did not make.

## The 80/20 trap

Internal platforms also have a strange 80/20 problem.

Teams naturally optimize for the first 80 percent of users. Serve the common path. Cover the main workloads. Prove adoption. Show impact.

But the remaining 20 percent does not vanish. It becomes support tickets, custom integrations, manual migrations, exception policies, and one-off fixes. Each item is small. Together, they compound.

Every new initiative repeats the same pattern. Each project solves its own 80 percent, and the leftover 20 percent keeps accumulating in the same platform teams and the same internal users. The people who launched the original project may have moved on. The people left behind inherit the compound interest.

This is not an individual failure. It is an incentive problem. We reward launches, migrations, adoption curves, and cost savings. We rarely reward the people who close the long tail and remove the pain that remained after launch.

## Feedback without market pressure is fragile

Internal systems lack strong feedback loops.

Because users cannot easily leave, pain does not show up as churn or lost revenue. Teams rely on surveys, office hours, support channels, tickets, and stakeholder meetings.

These signals help, but they are fragile. The most frustrated users may not fill out surveys. The busiest users may not complain. Feedback often describes symptoms rather than root causes. And even accurate feedback still competes with migrations, compliance work, cost targets, reliability goals, and leadership requests.

So platform teams often know their users are suffering. They just lack a strong mechanism to turn that suffering into priority.

## Build from the customer backward

The answer is not simply “write more docs” or “hire more people,” though both may help. The deeper answer is to combine AI builder speed, platform thinking, and a global view of the system.

Here are a few principles.

**Define the real customer.** The stakeholder approves the project. The customer lives with the consequences. For internal infra, the customer may be the on-call engineer, the product engineer integrating with the platform, the new hire trying to deploy safely, or the team that has no alternative.

**Measure pain, not just output.** Alongside cost, latency, reliability, and adoption, measure time to onboard, time to debug, number of concepts required, number of teams needed to resolve an issue, support load per user, manual exceptions, and self-service success.

**Remove complexity instead of hiding it.** An abstraction is valuable only if it reduces total system complexity. If it hides complexity from users while creating more mappings, exceptions, and state drift for maintainers, it has only moved the problem.

**Treat integration as product design.** Stitching open source software into legacy systems is not only integration work. Every adapter, gateway, workflow, CLI, UI, and API shapes how users understand the system. Users care whether they can build a stable mental model and debug failures without learning the entire history of the platform.

**Design for the long tail early.** You do not need to support every edge case on day one. But you do need to admit the long tail exists. A healthy 80/20 strategy defines what is unsupported, gives those users an escape hatch, records why exceptions exist, and regularly turns repeated exceptions into productized paths.

**Preserve context.** Important design decisions should explain the goal, the alternatives, the trade-off, and the condition under which the decision should be revisited. When founding engineers leave, the organization should transfer intent, constraints, known debt, and future repair plans, not just dashboards and repositories.

**Give maintenance teams product authority.** A team that only has permission to keep the lights on will keep adding patches. Maintenance teams need authority to deprecate interfaces, redesign workflows, remove bad abstractions, and say that a migration goal should not only be adoption, but user relief.

**Use AI to reduce toil, not amplify complexity.** AI builders can generate prototypes, migration scripts, debug tools, tests, docs, and custom workflows quickly. But AI should not become another layer on top of a confusing system. It should help find repeated support patterns, summarize user pain, assist legacy refactors, reduce debugging cost, and accelerate deletion of old abstractions.

The goal is not to help humans tolerate more complexity. The goal is to reduce the complexity humans must tolerate.

## Customer relief is impact

“Who is your customer?” sounds like a product question. For engineers, it is also an engineering question.

Once you know the customer, your standard changes. You do not only ask whether the system works. You ask whether it makes the user’s life easier. You do not only ask whether the metric improved. You ask whether the pain disappeared. You do not only ask whether 80 percent of users onboarded. You ask what happens to the remaining 20 percent.

Customer relief should be promotion-worthy impact.

Making a user read one less doc is impact. Preventing one on-call escalation is impact. Helping a new engineer deploy without understanding five legacy concepts is impact. Removing one unnecessary abstraction is impact. Moving a team from constant maintenance back into build mode is impact.

Impact should not live only in dashboards. It should show up in the customer’s day.

If the metrics improved but the customer is still suffering, the work is not done.

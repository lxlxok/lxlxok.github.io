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

The problem is that impact metrics can look good while customers are still suffering.

That is when we need to ask a more basic question:

**Who is your customer?**

<figure class="post-diagram impact-diagram" aria-label="Impact metrics can improve while customer relief remains missing">
  <figcaption>Impact metrics can improve while customer relief is still missing.</figcaption>
  <div class="diagram-split">
    <div class="diagram-panel">
      <div class="diagram-title">metrics improved</div>
      <ul>
        <li><span>cost saved</span></li>
        <li><span>latency reduced</span></li>
        <li><span>adoption up</span></li>
        <li><span>incidents down</span></li>
      </ul>
    </div>
    <div class="diagram-arrow" aria-hidden="true">!=</div>
    <div class="diagram-panel diagram-panel-warn">
      <div class="diagram-title">customer relieved</div>
      <ul>
        <li><span>fewer manual steps</span></li>
        <li><span>clear debugging path</span></li>
        <li><span>less context required</span></li>
        <li><span>lower on-call pain</span></li>
      </ul>
    </div>
  </div>
</figure>

## Impact is not customer value

Engineering impact is often measured by what is easy to count: cost saved, latency reduced, traffic migrated, incidents closed, users onboarded.

These metrics matter. But they are not the same as customer value.

This is especially true for internal systems and infrastructure. The real customer is often not the person approving the roadmap or reading the quarterly review. It is the engineer who must use the system every day, the on-call engineer paged at night, or the product team trying to ship through a platform they did not choose.

The infrastructure team suffers too. Many are treated as cost centers, understaffed, and asked to support more products, migrations, edge cases, and on-call burden every year.

So a team can be busy, important, and objectively delivering impact, while both the team and its customers become more miserable over time.

## How systems drift

Most internal platforms are not designed from first principles. They grow under time pressure, business pressure, and historical constraints. Teams build on open source software, stitch together systems with different assumptions, and plumb everything into legacy infrastructure.

Many trade-offs collapse into one sentence:

**Make it work.**

At the beginning, this is reasonable. The migration needs to happen. The incident needs to stop. The cost needs to come down. The MVP needs to launch.

But if the system never returns to the design question, it begins to drift.

The first integration gap gets covered with glue code. The next gap gets wrapped in an adapter. The next gap gets hidden behind an abstraction. Abstractions are necessary, but bad abstractions move complexity instead of reducing it.

After enough layers, the system stops scaling, not because any single component is weak, but because the whole thing has become too hard to understand, predict, and change.

## The human layer of technical debt

Technical debt is also about people and memory.

At the founding stage, the original engineers know which choices were intentional, which were MVP shortcuts, and which parts were meant to be revisited later.

Then people move on. Teams reorganize. New owners inherit the code, but not always the context or mandate. Temporary workarounds become permanent architecture. The system becomes harder to change because maintainers are trapped inside decisions they did not make.

## The 80/20 trap

Teams naturally optimize for the first 80 percent of users. Serve the common path. Cover the main workloads. Prove adoption. Show impact.

<figure class="post-diagram tail-diagram" aria-label="The first 80 percent looks complete while the remaining 20 percent accumulates as support burden">
  <figcaption>The first 80% looks complete. The remaining 20% becomes compound support burden.</figcaption>
  <div class="tail-bar" role="img" aria-label="80 percent common path and 20 percent long tail">
    <div class="tail-main">
      <span>80%</span>
      <small>common path shipped</small>
    </div>
    <div class="tail-edge">
      <span>20%</span>
      <small>tickets, exceptions, manual work</small>
    </div>
  </div>
  <div class="tail-stack" aria-hidden="true">
    <span>custom integration</span>
    <span>manual migration</span>
    <span>exception policy</span>
    <span>one-off fix</span>
  </div>
</figure>

But the remaining 20 percent does not vanish. It becomes support tickets, custom integrations, manual migrations, exception policies, and one-off fixes. Each item is small. Together, they compound.

Every new initiative repeats the same pattern. Each project solves its own 80 percent, and the leftover 20 percent keeps accumulating in the same platform teams and the same internal users.

This is not an individual failure. It is an incentive problem. We reward launches, migrations, adoption curves, and cost savings. We rarely reward the people who close the long tail and remove the pain that remained after launch.

## Build from the customer backward

The answer is not simply “write more docs” or “hire more people,” though both may help. The deeper answer is to build from the customer backward.

Here are a few principles.

**Define the real customer.** The stakeholder approves the project. The customer lives with the consequences: the on-call engineer, the product engineer, the new hire, or the team with no alternative.

**Measure pain, not just output.** Alongside cost, latency, reliability, and adoption, measure time to onboard, time to debug, concepts required, support load, manual exceptions, and self-service success.

**Remove complexity instead of hiding it.** An abstraction is valuable only if it reduces total system complexity. Every adapter, workflow, CLI, UI, and API should help users build a stable mental model, not create more mappings and exceptions.

**Design for the long tail early.** You do not need to support every edge case on day one. But you do need to admit the long tail exists, define what is unsupported, and turn repeated exceptions into productized paths.

**Give maintenance teams product authority.** A team that only has permission to keep the lights on will keep adding patches. They need context, authority to deprecate bad interfaces, and room to define success as user relief.

## Customer relief is impact

“Who is your customer?” sounds like a product question. For engineers, it is also an engineering question.

Once you know the customer, your standard changes. You do not only ask whether the system works. You ask whether it makes the user’s life easier. You do not only ask whether the metric improved. You ask whether the pain disappeared. You do not only ask whether 80 percent of users onboarded. You ask what happens to the remaining 20 percent.

Customer relief is impact.

Making a user read one less doc is impact. Preventing one on-call escalation is impact. Helping a new engineer deploy without five legacy concepts is impact. Removing one unnecessary abstraction is impact.

Impact should not live only in dashboards. It should show up in the customer’s day.

If the metrics improved but the customer is still suffering, the work is not done.

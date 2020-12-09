---
layout: post
title: Collective knowledge
date:   2020-12-09 20:26:58 -0700
categories: highlights work
---

![simpsons-group-huddle](https://raw.githubusercontent.com/svvchen/nervxious/gh-pages/assets/images/simpsons-all-hands.png?style=centerme)

When I was a kid, my friends and I would trade candy after we finished trick-or-treating. We'd do this because each of us would trick-or-treat in a different neighborhood, and as a result, get different types of candy. We didn't all like the same candy though, so we'd trade to get more of what we wanted.

Each person would lay out their mound of treats, and we'd each let each other know what our preferences were. Based on the each person's haul, and what they liked, we started trading. The end result: I got my reese's peanut butter cups, and my friend got his skittles.

This only worked because we knew what each other had and liked.

The mechanism behind the scenes that made this work was **collective knowledge: knowledge known to the entire group**. It applies in any situation where there are multiple people are working towards the same goal.

--

Here's an example: imagine you're working in a product, design, and engineering team. You kick a project off, with everyone having the same collective knowledge.

![same-collective-knowledge](https://raw.githubusercontent.com/svvchen/nervxious/gh-pages/assets/images/ck1.png)

Now — what would happen if product and engineering had a whiteboarding session, in which they discovered something relevant to the project? The knowledge they gain from the session has not been shared with everyone, **meaning the collective knowledge is still the same**. But now **unshared knowledge is non-zero**.

![same-collective-knowledge-unshared](https://raw.githubusercontent.com/svvchen/nervxious/gh-pages/assets/images/ck2.png)

Now that design is behind, your team risks marching out of step.

Say you don't inform your designer, and they continue to work in a silo. At the design review, they present a UI that both product and engineering know won't work. Your designer realizes they sunk time into something that shouldn't have even been considered, and becomes frustrated with the project.

To prevent situations like this, remember this rule: **maximize collective knowledge; minimize unshared knowledge**.

![same-collective-knowledge](https://raw.githubusercontent.com/svvchen/nervxious/gh-pages/assets/images/ck3.png)

If unshared knowledge is 0, you de-risk the project. In the same example, had you told design about the outcomes of the whiteboarding session, they could have course corrected far earlier.

## In practice
If you are trying to deliver on a goal, incorporate these best practices. Each of them helps maximize collective knowledge, and minimize unshared knowledge.

* Pairwise conversation creates for unshared knowledge, especially if your team doesn't over-communicate. In the product, design, engineering scenario: 
  * Product and engineering could talk about feature priority, find something out, and not relay to design. Design could start mocking up certain features that product and engineering have already punted on.
  * Engineering and design could talk about a UI interaction that allows for easier buildout. Product finds out later, only to realize that it allows for a breach in requirements from compliance.
  * Design and product could brainstorm a UI that can't be built given the current data model. Once engineering finds out, they are be blocked on execution.
* Start documents with a "current state of the world" section. Provide your context, and invite others to add comments and contribute to the group’s understanding.
* Start meetings with ample context, and ask if others have any questions. Be vigilant here — people can underestimate the importance of understanding details.

And the most important of them all — convey these practices to your team. Emphasize the importance of keeping everyone on the same page, and celebrate the times when team members keep each other well informed. After some practice, it'll be second nature, and you'll start shipping faster than ever before. 🍬🍬🍬

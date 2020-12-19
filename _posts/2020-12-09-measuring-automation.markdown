---
layout: post
title: Measuring automation
date: 2020-12-19 20:26:58 -0700
categories: highlights work
---

My team was attempting to automate a task that was completely manual. After some research, we estimated that in a single quarter, we could reduce the time needed to complete the task by half, from 5 to 2.5 minutes.

We decided to make it a key result, and confidently took it into a planning review with stakeholders.

...only to have a VP of Operations immediately shoot it down.

Her reasoning:

- **Time measurements are tricky, especially those derived from day-to-day product usage.** Time metrics come with baked in confounding variables — things like user expertise, focus, experience using the product, etc — that make it hard to measure impact.
- **Focusing on a time average makes it worse.** Time averages are a good way of lying with data. Instead, look at the distribution of time, and derive insight from that.

I had no good response to these. It was an opportunity for learning, though — I took the feedback and thought about it, eventually coming up some lessons for measuring automation. Below are my notes.

--

## Time measurements

Don't focus on average time to complete a task. The distribution of time spent is far more meaningful. Take the below examples — in distribution on the left, the total time spent by operations would be far lower than that in the distribution on the right, even though their average time spent are the same. By focusing on the average — as we were planning on doing — there would be opportunities to lie with data, and never save operations time in doing the task.

![time-distributions](https://raw.githubusercontent.com/svvchen/nervxious/gh-pages/assets/images/time.png)

## Human dependent vs independent metrics

I tried deriving the same understanding as this VP on time measurements by starting from business motivations — here are my notes.

- Operations heavy businesses typically want to automate to reduce cost to serve/operational overhead.
- In order to automate, a company can either **improve the operational efficiency of people, or reduce the complexity of a task.**
- There are metrics that measure the effect of both these collectively: time to complete task, task output per person, etc. I think of these as **human dependent metrics**. They are not great measures of operational optimizations, or reductions in task complexity. *Rather, they're indicators of the end goal of the business (more tasks done in less time).*
- There are also **human independent metrics** — things like the number of steps, required clicks, and screens, in a product workflow. These are directly related to reducing the complexity of a task, meaning they're fantastic success metrics for teams building towards automation. As these approach 0, you get closer and closer to full automation (e.g. 0 steps, or clicks, means no human).

Our stakeholder was keeping us accountable by mentioning that we were using a human dependent metric. Even if we made improvements, we wouldn't be able to tell whether the task got easier, or if the people just became more efficient. 

Understanding the nuance here is essential for any product manager that is focused on gradually removing a human in the automation loop.

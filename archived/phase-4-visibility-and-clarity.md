---
title: "Phase 4: Making Failures Visible"
description: "Why screenshots and video matter more than a green checkmark."
pubDate: 2026-02-15
---

A failing test that just says "failed" is only half useful.

I knew tests were running. I knew when they turned red. But a red status by itself doesn't tell you whether the application broke, the test broke, or something in the environment shifted. Diagnosing it meant going back to my machine, opening the form manually, and trying to reproduce what the automated run had seen. That was time I was supposed to be saving.

I added a proper test reporter and wired failure notifications into the team's messaging platform. When a test fails now, the report captures a screenshot of exactly what was on screen at the moment of failure, along with a video of the entire test run. I can see the state of the form, where the cursor was, what was filled in, and what the page looked like when it stopped.

That level of detail changed how quickly I could triage. Most failures became obvious within thirty seconds of looking at the report. Either the form had changed and a selector needed updating, or the system itself had returned an unexpected error, or a timing issue had caused a field to be missed. Each of those required a different response, and the screenshots made the distinction clear immediately.

The notifications changed something else. Other people started seeing test results without me having to relay them. When a test failed overnight, I'd sometimes arrive to find someone had already looked at the report and formed their own opinion about whether the failure was real. That was new.

It also shifted the nature of questions I got. Before, people would ask me to explain what the tests were detecting. After, they'd ask about specific failures they'd already read. The conversation became more grounded. The work stopped being invisible.

There's something worth noting about what visibility does to trust. When results are opaque, people trust them less or ask for more reassurance. When people can see exactly what happened and why, they evaluate it themselves. That self-service quality is what made the reports more valuable than the status alone.

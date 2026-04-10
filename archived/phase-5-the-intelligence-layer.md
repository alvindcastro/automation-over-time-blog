---
title: "Phase 5: Adding a Memory Layer"
description: "Why I built a database before I added AI."
pubDate: 2026-04-06
---

Screenshots and logs tell you what happened in a single run. They don't tell you whether it's happened before.

After enough test cycles, I started noticing a pattern in how I processed failures. I'd look at a report, recognize something vaguely familiar, and then spend time digging through old results trying to find the previous occurrence. That search was always manual, always slow, and often inconclusive. The history existed, but it wasn't connected to anything.

Before adding any intelligence, I needed to add memory.

I built a database to persist every test run and every failure. Each record captured the test name, the failure message, the timestamp, and enough context to make it searchable later. I used schema migrations to manage the structure so it could evolve without losing historical data. That foundation came first, before any AI was involved.

Once the history was structured and queryable, I layered in semantic search. Instead of exact keyword matching, the system could find failures that were conceptually similar — the same root cause described in slightly different error messages across different runs. That kind of pattern matching is what makes history useful rather than just archived.

The AI reporting came on top of that. When a test fails, the system pulls the failure details, finds relevant historical matches, and sends the full context to a language model for analysis. The model produces a plain-language explanation of what happened, whether it looks like a regression or a fluke, and what category of issue it most likely represents. That summary gets attached to the test report and pushed to the team channel.

The important distinction is sequencing. I didn't start with AI and figure out the data layer later. The database came first because AI without context produces confident-sounding guesses. AI with a well-structured history of past failures produces something closer to a diagnosis.

The system isn't trying to be clever. It's trying to remember well enough that the analysis can be grounded in something real.

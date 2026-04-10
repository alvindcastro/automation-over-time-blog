---
title: "When Manual Validation Stops Scaling"
description: "Why I couldn't keep clicking the same buttons every Tuesday."
pubDate: 2025-05-15
phase: 1
visibility: "Public"
---

It didn't start with ambition. It started with exhaustion.

Every Tuesday morning I ran the same set of smoke tests against the ERP system. Log in, navigate to a form, submit something, verify the result, move on to the next one. Repeat that across a dozen forms. The whole thing took about four hours, and the expected outcome was almost always the same: nothing is broken.

That's the nature of smoke tests. They exist to confirm the obvious. After a system upgrade or a configuration change, someone needs to verify that the basic workflows still work. The checks aren't interesting. But they need to happen, and they need to happen consistently.

For a while, doing it manually felt reasonable. I knew the system. I knew what to look for. The rhythm was familiar.

After the fiftieth time, something shifted.

I stopped noticing things. Not because the system had stopped changing, but because my attention had quietly recalibrated. I'd seen the same screens so many times that subtle differences stopped registering. I was going through the motions. The quality of the check was degrading even though I was technically still doing the work.

That's the hidden cost of repetition. It doesn't announce itself. It just slowly replaces judgment with muscle memory.

At that point, continuing to do those checks manually wasn't responsible. I wasn't adding real value. I was borrowing the appearance of diligence while the actual signal got weaker each week.

The initial goal wasn't to build something impressive. I just needed a script that could log in and click through those forms so I didn't have to. No framework, no test suite, no reporting pipeline. Just something that would do the boring part so I could focus on work that actually required a human.

Everything else that followed grew out of that narrow, honest starting point.

---
title: "Phase 3: Moving to the Server"
description: "Automation is useless if you have to remember to run it."
pubDate: 2025-12-15
---

A test suite that only runs when someone remembers to start it is still a manual process. The trigger is just different.

I'd built stable page objects and a test structure I trusted. But I was still running the tests on my own machine, on my own schedule. If I was busy, or away, or simply forgot, nothing ran. The consistency I had built into the tests didn't extend to how often they actually executed.

The fix was moving everything to a dedicated build server. Tests ran at 3:00 AM every night. They also ran after any meaningful change. I stopped being the scheduler. The server was.

That shift felt small but it wasn't. Once tests run on their own, the relationship with them changes. You stop thinking about when to run them and start focusing on what they're telling you. The results became something I checked in the morning rather than something I had to initiate.

There was one problem that took real effort to solve: authentication. The system uses enterprise single sign-on. Every time the tests ran in a fresh browser context, they'd hit the login screen and stall. I couldn't hardcode credentials and I couldn't automate the multi-factor flow interactively.

The solution was to save the authenticated browser state after a real login session and reuse it on subsequent runs. The tests would load that saved state and skip the login entirely, landing directly inside the application as if already authenticated. That worked well, but sessions expire. A session that was valid today might not be valid in two weeks.

To handle that I added a second scheduled job — a separate pipeline that ran on a weekly cadence specifically to refresh the saved session. It triggered a real login, saved the new state, and made it available to the nightly test runs. The main pipeline didn't need to know anything about authentication. It just consumed a valid session that was always kept current.

The result was a system that ran without being asked, authenticated without intervention, and reported back before the workday began. The quiet kind of infrastructure that only gets noticed when it stops working.

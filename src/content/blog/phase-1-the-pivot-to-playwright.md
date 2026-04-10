---
title: "Phase 1: Beyond Manual Validation: The Case for Playwright"
description: "How a failed legacy Selenium project and manual fatigue led us to build a reliable automation baseline with Playwright and MFA integration."
pubDate: 2024-03-15
phase: 1
tags: ["playwright", "mfa", "selenium", "manual-testing"]
---

### The Manual Wall

At the beginning, validation was an entirely manual process. As the institution’s core
operation records and workflows grew in complexity, each upgrade cycle required a
predictable but exhausting set of smoke and sanity checks. We reached a point where manual
validation was no longer a viable strategy for maintaining high-level operability. The
bottleneck wasn't just time; it was the cognitive load of repeating the same checks
without error.

### The Selenium Trap

We didn't start from zero. There was an inherited Selenium project, but it had become a
liability. It was fragile, difficult to debug, and most importantly, it failed to provide
the "trust signal" required for a production-ready environment. The maintenance cost of
keeping the Selenium scripts running was higher than the value they provided.

### Choosing a Modern Stack

When we pivoted, the goal was clear: we needed a tool that prioritized reliability and
speed. After a period of exploration, we landed on **Playwright**. Its ability to handle
modern web architecture, its auto-waiting mechanisms, and its superior developer
experience made it the natural choice.

Our initial implementation prioritized clarity and consistency, focusing specifically on
two key areas that had previously caused significant friction. We established a baseline
of tests that could be run quickly and reliably by anyone on the team:
1.  **Smoke Tests**: High-level checks to ensure the system was "up."
2.  **Sanity Tests**: Deeper validation of critical operational paths.

### The Identity Hurdle: MFA Integration

One of the most significant early wins was integrating **Multi-Factor Authentication (MFA)**
into the automated flow. In an institutional environment where security is non-negotiable,
automation often stops at the login screen. By solving the MFA challenge within our
Playwright scripts, we unlocked the ability to run truly end-to-end tests without manual
intervention.

This wasn't just about automation; it was about building a foundation that we and the
institution could finally trust. By moving away from manual reliance, we established a
more resilient process that allowed for more frequent and confident deployments.

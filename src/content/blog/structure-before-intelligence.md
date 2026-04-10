---
title: "Structure Before Intelligence"
description: "Why I stay flexible with my tools."
pubDate: 2026-04-15
phase: 10
visibility: "Public"
---

The AI landscape moves fast enough that any specific model or vendor you commit to today might not be the right choice in six months. I've watched tooling choices become liabilities before, and I wasn't interested in building that problem into the intelligence layer of this system.

The decision I made early was to avoid using an official SDK for AI calls. A vendor SDK was already available when I started adding AI features, but I never used it. Instead, I made raw HTTP calls to the model endpoint directly. The API is just JSON over HTTP. You don't need a library for that.

That turned out to be the right call, but not just for the obvious reasons. The real benefit became clear when I started thinking about switching providers. Moving from one AI service to another doesn't require changing service classes or swapping SDKs. It requires changing a URL, a couple of headers, and a configuration value. The rest of the code stays exactly the same.

I also built a test generator into the system. It takes a browser recording — the raw output from the recorder that was too brittle to use directly — and converts it into a proper Page Object Model test class. It reads the recording, extracts the intent behind each action, and produces code that follows the same conventions as the hand-written tests. The generated code still gets reviewed before it's used, but it dramatically compresses the time from "new form to test" to something that can be reviewed in an afternoon.

The underlying principle in both cases is the same: don't let today's best tool become tomorrow's constraint. Use abstractions thin enough to replace. Keep the logic in your code, not in the library. Make switching providers a configuration change, not a migration.

This phase isn't finished. It probably never will be. The tools will keep changing, and the right response is to keep the foundation simple enough that the system can change with them.

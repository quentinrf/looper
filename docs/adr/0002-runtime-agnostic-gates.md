# Gates and policy live outside the agent runtime

Everything that judges work (gates, the review policy, merge rules) lives in git hooks, Go scripts and GitHub Actions, never inside an agent runtime. Launching an agent on a ticket is a thin adapter, and its default is to generate a prompt and handoff for a human to start in the Cursor editor. The reason is that Cursor is the mandated runtime at work and the Cursor API key needed for headless launching may never be granted. If it is, or the runtime changes, only the adapter changes.

## Consequences

- Runtime hooks (e.g. `.cursor/hooks.json`) are convenience guardrails only. They fail open by default, so CI gates are the real enforcement.

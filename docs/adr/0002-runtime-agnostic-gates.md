# Gates and policy live outside the agent runtime

Everything that judges work (gates, the review policy, merge rules) lives in git hooks, Go scripts and GitHub Actions, never inside an agent runtime. Launching an agent on a ticket is a thin adapter, and its default is to generate a prompt and handoff for a human to start in the Cursor editor. The reason is that the work models (DeepSeek, GLM) are reachable only through the Cursor editor's OpenAI base-URL override, which the Cursor CLI and Cloud Agents API reportedly do not support, and a Cursor API key may never be granted. If headless launching becomes possible, only the adapter changes.

## Consequences

- Runtime hooks (e.g. `.cursor/hooks.json`) are convenience guardrails only. They fail open by default, so CI gates are the real enforcement.

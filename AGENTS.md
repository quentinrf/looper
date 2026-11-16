# Looper

Looper is a public, generic harness for agent-driven software delivery: agent definitions, policies, gates and skills that let agents run implementation loops while a human reviews specs, scenarios and behaviour. Read `GLOSSARY.md` for the vocabulary and `docs/adr/` for decisions before changing anything.

## Rules

- **Keep it generic.** No employer names, service names, account IDs, internal URLs or other work-specific detail. A leak is a bug (ADR 0001).
- **Gates live outside the agent runtime.** Anything that judges work belongs in Go scripts, git hooks or GitHub Actions, not in Cursor or Claude Code configuration (ADR 0002).
- **Small, coherent commits and PRs.** One ticket is one branch and one PR.
- **Use the glossary's terms** in code, tests, issues and commit messages.

## Agent skills

Skills live in `.agents/skills/` (vendored from mattpocock/skills, see `.agents/skills/UPSTREAM.md`); `.claude/skills` points at the same directory.

### Issue tracker

Issues, specs and tickets live as GitHub issues in this repo. See `docs/agents/issue-tracker.md`.

### Triage labels

The five default triage labels (`needs-triage`, `needs-info`, `ready-for-agent`, `ready-for-human`, `wontfix`). See `docs/agents/triage-labels.md`.

### Domain docs

Single-context: `GLOSSARY.md` and `docs/adr/` at the repo root. See `docs/agents/domain.md`.

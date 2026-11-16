# Looper

A reusable harness for agent-driven software delivery: the agent definitions, policies, gates and skills that let agents run implementation loops while a human reviews specs, scenarios and behaviour.

## Language

**Harness**:
The set of agent definitions, policies, gates, skills and workflow templates that looper provides. Looper is the harness; it is not a service.
_Avoid_: framework, platform, toolkit

**Consumer repo**:
A repository that adopts the harness to have agents deliver work in it.
_Avoid_: service repo, target repo, client repo

**Gate**:
A deterministic check that work must pass before it can proceed, such as tests, lint or a commit-size limit.
_Avoid_: check, guard, validation

**Agent runtime**:
The tool that executes an agent session, such as Cursor or Claude Code.
_Avoid_: harness, IDE, agent platform

**Review workspace**:
A terminal layout that opens in Rex for a human to inspect and correct an agent's work.
_Avoid_: dashboard, review session

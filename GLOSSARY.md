# Looper

A reusable harness for agent-driven software delivery: the agent definitions, policies, gates and skills that let agents run implementation loops while a human reviews specs, scenarios and behaviour.

## Language

**Harness**:
The set of agent definitions, policies, gates, skills and workflow templates that looper provides. Looper is the harness; it is not a service.
_Avoid_: framework, platform, toolkit

**Consumer repo**:
A repository that adopts the harness to have agents deliver work in it.
_Avoid_: service repo, target repo, client repo

**Example consumer**:
A small consumer repo kept inside looper, used to prove reusable parts of the harness before they are adopted elsewhere.
_Avoid_: sample app, demo, fixture

## Loop

**Ticket**:
A single, small unit of work tracked as a GitHub issue, delivered by one implementer run as one pull request.
_Avoid_: issue, task, story

**Implementer**:
The agent that delivers a ticket test-first.
_Avoid_: author, coder, builder

**Reviewer**:
The agent that judges an implementer's work against the review policy. It is never the same agent or model family as the implementer.
_Avoid_: evaluator, critic, checker

**Review policy**:
The written standard every reviewer judges work against.
_Avoid_: guidelines, checklist, rubric

**Launcher**:
The thin, runtime-specific adapter that starts an implementer or reviewer on a ticket.
_Avoid_: runner, dispatcher, orchestrator

**Gate**:
A deterministic check that work must pass before it can proceed, such as tests, lint or a commit-size limit.
_Avoid_: check, guard, validation

## Tooling

**Agent runtime**:
The tool that executes an agent session, such as Cursor or Claude Code.
_Avoid_: harness, IDE, agent platform

**Review workspace**:
A terminal layout that opens in Rex for a human to inspect and correct an agent's work.
_Avoid_: dashboard, review session

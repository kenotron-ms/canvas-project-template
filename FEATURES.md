# Amplifier Features

This template enables the following Amplifier features out of the box:

## Behaviors

- **amplifier-expert** — Built-in consultant for the Amplifier ecosystem. Ask it anything about modules, bundles, or configuration.
- **agents** — Automatically spawns specialist sub-agents for heavy tasks like code exploration, debugging, architecture design, git operations, and web research.
- **streaming-ui** — Responses stream in real time instead of appearing all at once.
- **status-context** — The assistant always knows your current git branch, working directory, and the date — no need to tell it manually.
- **todo-reminder** — Keeps the assistant on track during multi-step work with a visible task list.
- **redaction** — Scrubs secrets and API keys from output before they can leak.
- **recipes** — Reusable multi-step workflows with approval gates, ideal for full feature development cycles.
- **modes** — Behavioral overlays you can toggle on demand: `/brainstorm`, `/debug`, `/execute-plan`, `/verify`, `/finish`.
- **skills** — Domain knowledge packages that load on demand, bringing structured best practices into any session.
- **apply-patch** — Enables precise multi-file edits in a single operation.
- **engram** — Persistent memory so the assistant remembers context across sessions.

## Sub-Agents

These specialist agents are invoked automatically when needed:

- **explorer** — Surveys large codebases across many files.
- **file-ops** — Handles targeted file reads, writes, and searches.
- **git-ops** — Manages commits, PRs, branch operations, and the GitHub API.
- **bug-hunter** — Performs systematic debugging.
- **modular-builder** — Implements features from a spec.
- **zen-architect** — Handles architecture design, code review, and planning.
- **web-research** — Conducts multi-source web research.

## Session Configuration

| Setting | Value |
|---------|-------|
| Orchestrator | `loop-streaming` (real-time output) |
| Extended thinking | Enabled |
| Max context | 200,000 tokens |
| Auto-compact | Yes — long sessions stay running automatically |

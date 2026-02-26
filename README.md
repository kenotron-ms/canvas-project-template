# amplifier-template

An opinionated [Amplifier](https://github.com/microsoft/amplifier) starter configuration — cherry-picked behaviors, no bloat. Designed to work out of the box with tools like [`amplifier-app-cli`](https://github.com/kenotron-ms/amplifier-app-cli) while staying lean enough to extend without fighting the defaults.

## Usage

### As a GitHub Template

Click **Use this template** at the top of this repo to create your own copy, then clone it and run:

```bash
amplifier run
```

### With amplifier-app-cli

```bash
amplifier-app-cli init --template kenotron-ms/amplifier-template
```

---

## What's Included

### Behaviors

| Behavior | Source | What it gives you |
|----------|--------|-------------------|
| **amplifier-expert** | `microsoft/amplifier` | Expert consultant for the full Amplifier ecosystem — modules, repos, governance, and best practices |
| **agents** | `amplifier-foundation` | Multi-agent orchestration: spawns specialist sub-agents (explorer, builder, bug-hunter, etc.) via a `delegate` tool |
| **sessions** | `amplifier-foundation` | Session lifecycle awareness and management |
| **streaming-ui** | `amplifier-foundation` | Streaming output with live progress rendering |
| **status-context** | `amplifier-foundation` | Auto-injects git status, working directory, and current date/time into every turn |
| **todo-reminder** | `amplifier-foundation` | Keeps the agent on track — prompts use of the todo tool for multi-step work |
| **redaction** | `amplifier-foundation` | Scrubs secrets, API keys, and sensitive tokens from output before they leak |
| **recipes** | `amplifier-bundle-recipes` | Declarative multi-step workflows with approval gates, resumability, and context accumulation across agent handoffs |
| **modes** | `amplifier-bundle-modes` | Runtime behavior overlays: `/brainstorm`, `/debug`, `/execute-plan`, `/verify`, `/finish` and more |
| **skills** | `amplifier-bundle-skills` | Loadable domain knowledge packages — bring structured best practices into any session on demand |
| **apply-patch** | `amplifier-bundle-filesystem` | `apply_patch` tool for surgical multi-file edits and new file creation from a single operation |
| **engram** | `kenotron-ms/engram` | Persistent memory — the agent can remember context across sessions |

### Tools

| Tool | What it does |
|------|-------------|
| `tool-filesystem` | Read and write files on the local filesystem |
| `tool-bash` | Execute shell commands |
| `tool-web` | Fetch web pages and call HTTP endpoints |
| `tool-search` | Search the web |

### Sub-Agents (via `delegate`)

The `agents` behavior makes these specialist agents available for delegation:

| Agent | Best for |
|-------|----------|
| `foundation:explorer` | Deep codebase surveys across many files |
| `foundation:file-ops` | Targeted file reads, writes, and searches |
| `foundation:git-ops` | Commits, PRs, branch ops, GitHub API — with safety guardrails |
| `foundation:bug-hunter` | Systematic debugging with hypothesis-driven methodology |
| `foundation:modular-builder` | Implementation from a complete specification |
| `foundation:zen-architect` | Architecture design, code review, and planning |
| `foundation:web-research` | Multi-source web research and documentation lookup |

### Session Configuration

| Setting | Value | Notes |
|---------|-------|-------|
| Orchestrator | `loop-streaming` | Streaming output, real-time token delivery |
| Extended thinking | `true` | Deeper reasoning on complex problems |
| Context module | `context-simple` | |
| Max tokens | 200,000 | |
| Auto-compact | `true` at 80% | Keeps long sessions running without manual intervention |

---

## Extending This Template

Add more behaviors to the `includes:` section of `.amplifier/bundle.md`, following the same pattern:

```yaml
includes:
  - bundle: git+https://github.com/your-org/your-bundle@main#subdirectory=behaviors/your-behavior.yaml
```

See the [Amplifier Foundation Bundle Guide](https://github.com/microsoft/amplifier-foundation) for authoring your own behaviors and bundles.

---

## License

MIT

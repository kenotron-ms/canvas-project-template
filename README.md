# amplifier-template

A project starter that works with **two AI tools** — use whichever fits your workflow, or both:

- **[Amplifier](https://github.com/microsoft/amplifier)** — a powerful AI CLI with multi-agent capabilities, structured workflows, and persistent memory
- **[Claude Code](https://docs.anthropic.com/en/docs/claude-code)** — Anthropic's VS Code extension, now with the same persistent memory via Engram

Both tools share Engram for memory, so project knowledge accumulates regardless of which tool you're using.

---

## Getting Started with Amplifier

Two prerequisites, then four commands. That's it.

### Prerequisites

- **[uv](https://docs.astral.sh/uv/getting-started/installation/)** — Python package manager

  ```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ```

- **[gh](https://cli.github.com/)** — GitHub CLI (and run `gh auth login` if you haven't already)

  ```bash
  # macOS
  brew install gh

  # Windows / Linux: https://cli.github.com/
  ```

---

### Step 1 — Install Amplifier

```bash
uv tool install git+https://github.com/microsoft/amplifier
```

---

### Step 2 — Create your project from this template

```bash
gh repo create my-project --template kenotron-ms/amplifier-template --public --clone
cd my-project
```

Replace `my-project` with whatever you want to call your repo. Use `--private` if you prefer.

---

### Step 3 — Initialize

```bash
amplifier init
```

The wizard will ask for your AI provider and API key (Anthropic, OpenAI, Azure, Gemini, or Ollama) and wire everything up automatically.

---

### Step 4 — Start chatting

```bash
amplifier
```

That's it. You now have a fully configured AI assistant with persistent memory, multi-agent capabilities, structured workflows, and more — all scoped to your project.

---

## Getting Started with Claude Code

If you use the [Claude Code](https://docs.anthropic.com/en/docs/claude-code) VS Code extension, this template pre-configures the [Engram](https://github.com/kenotron-ms/engram) plugin so persistent memory works from day one.

### Step 1 — Create your project from this template

```bash
gh repo create my-project --template kenotron-ms/amplifier-template --public --clone
cd my-project
```

### Step 2 — Open in VS Code

Open the project folder in VS Code with Claude Code installed. The Engram plugin is registered in `.claude/settings.json` and loads automatically.

### Step 3 — Initialize personal memory (first time only)

```bash
mkdir -p ~/.canvas/memory
```

That's it. Claude Code will now remember context across sessions for this project.

---

## What's Included

### Amplifier Behaviors

| Behavior | What it gives you |
|----------|-------------------|
| **amplifier-expert** | Built-in consultant for the Amplifier ecosystem itself — ask it anything about modules, bundles, or configuration |
| **agents** | Spawns specialist sub-agents automatically for heavy tasks (code exploration, debugging, architecture, git operations, web research) |
| **streaming-ui** | Responses stream in real time instead of appearing all at once |
| **status-context** | The assistant always knows your current git branch, working directory, and the date — no need to tell it |
| **todo-reminder** | Keeps the assistant on track during multi-step work with a visible task list |
| **redaction** | Scrubs secrets and API keys from output before they can leak |
| **recipes** | Reusable multi-step workflows with approval gates — great for things like full feature development cycles |
| **modes** | Behavioral overlays you can toggle: `/brainstorm`, `/debug`, `/execute-plan`, `/verify`, `/finish` |
| **skills** | Domain knowledge packages that load on demand — bring structured best practices into any session |
| **apply-patch** | Lets the assistant make precise multi-file edits in a single operation |
| **engram** | Persistent memory — the assistant remembers context across sessions |

### Amplifier Sub-Agents (called automatically when needed)

| Agent | What it handles |
|-------|----------------|
| `explorer` | Surveying large codebases across many files |
| `file-ops` | Targeted file reads, writes, and searches |
| `git-ops` | Commits, PRs, branch management, GitHub API |
| `bug-hunter` | Systematic debugging |
| `modular-builder` | Implementing from a spec |
| `zen-architect` | Architecture design, code review, planning |
| `web-research` | Multi-source web research |

### Amplifier Session Configuration

| Setting | Value |
|---------|-------|
| Orchestrator | `loop-streaming` (real-time output) |
| Extended thinking | Enabled |
| Max context | 200,000 tokens |
| Auto-compact | Yes — long sessions stay running automatically |

### Claude Code Plugins

| Plugin | What it gives you |
|--------|-------------------|
| **engram** | Persistent memory — project knowledge in `.canvas/memory/`, personal knowledge in `~/.canvas/memory/` |

---

## Extending This Template

### Add Amplifier behaviors

Edit `.amplifier/bundle.md` and append to the `includes:` list:

```yaml
includes:
  - bundle: git+https://github.com/your-org/your-bundle@main#subdirectory=behaviors/your-behavior.yaml
```

See the [Amplifier Foundation Bundle Guide](https://github.com/microsoft/amplifier-foundation) for how to author your own.

### Add Claude Code plugins

Edit `.claude/settings.json` and register additional plugins in `extraKnownMarketplaces` and `enabledPlugins`.

---

## License

MIT

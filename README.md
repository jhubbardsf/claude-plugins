# claude-plugins

Josh Hubbard's Claude Code plugin marketplace. One marketplace add, every plugin.

## Installation

Add the marketplace once:

```text
/plugin marketplace add jhubbardsf/claude-plugins
```

Then install any plugin:

```text
/plugin install codex-reviewer@joshd3v
/plugin install rephrasy@joshd3v
/plugin install context-budget@joshd3v
```

## Plugins

| Plugin | What it does | Docs |
|--------|--------------|------|
| `codex-reviewer` | Runs Codex GPT-5.5 as an independent code reviewer from Claude Code. Provides `/codex-reviewer:codex-reviewer`. | [Docs](https://jhubbardsf.github.io/codex-review/) · [Repo](https://github.com/jhubbardsf/codex-review) |
| `rephrasy` | Scores text for AI detectability (0 = human, 100 = AI, per-sentence breakdown) and humanizes AI-generated text via the Rephrasy API. Provides `/rephrasy:ai-detect` and `/rephrasy:humanize`. Requires `REPHRASY_API_KEY`. | [Docs](https://jhubbardsf.github.io/rephrasy-skills/) · [Repo](https://github.com/jhubbardsf/rephrasy-skills) |
| `context-budget` | Warns the model before Claude Code auto-compacts (mid-turn, at 70% and again just before the trigger), keeps a handoff that's reloaded after every compaction, and lets the model compact itself at a clean checkpoint. Hooks only, no commands. | [Repo](https://github.com/jhubbardsf/claude-context-budget) |

## How this marketplace works

The manifest lives in `.claude-plugin/marketplace.json`. Each plugin lives in its own repository and is referenced via a `git-subdir` source. The marketplace name `joshd3v` is the install namespace (`plugin@joshd3v`). Each plugin repo also ships its own standalone marketplace for direct installs.

## License

MIT

# opencli-rs command subsets

Use this file only when you need quick command examples for common targets. Keep `SKILL.md` lean.

## Safe public commands

These are the best first tests because they do not require the browser extension or login reuse.

```bash
opencli-rs hackernews top --limit 10 --format json
opencli-rs hackernews search --query "OpenClaw" --limit 10 --format json
opencli-rs bbc news --limit 10 --format json
opencli-rs arxiv search --query "large language models" --limit 10 --format json
opencli-rs stackoverflow search --query "rust async" --limit 10 --format json
opencli-rs devto top --limit 10 --format json
opencli-rs lobsters hot --limit 10 --format json
```

## Browser-backed read commands

Use these only after confirming Chrome is open, the user is logged in, and the extension/daemon are connected.

```bash
opencli-rs twitter timeline --limit 20 --format json
opencli-rs twitter search "OpenClaw" --limit 10 --format json
opencli-rs reddit frontpage --limit 15 --format json
opencli-rs reddit search --query "OpenClaw" --limit 10 --format json
opencli-rs youtube search --query "LLM tutorial" --limit 10 --format json
opencli-rs bloomberg tech --limit 10 --format json
opencli-rs yahoo-finance quote --symbol AAPL --format json
opencli-rs barchart options --symbol SPY --format json
opencli-rs substack feed --limit 10 --format json
opencli-rs medium feed --limit 10 --format json
```

## Desktop-app commands

Use these only if the desktop app is already running.

```bash
opencli-rs cursor status --format json
opencli-rs codex status --format json
opencli-rs notion search --query "meeting notes" --format json
opencli-rs discord-app status --format json
```

## Argument gotchas

Some commands take a positional argument instead of a named flag. Check `--help` for the exact form before assuming.

Examples:

```bash
opencli-rs wikipedia summary OpenAI --format json
opencli-rs google search OpenClaw --limit 3 --format json
```

Not every adapter uses `--query` or `--title`.

## Diagnostics

```bash
opencli-rs --help
opencli-rs <site> --help
opencli-rs <site> <command> --help
opencli-rs doctor
opencli-rs list
```

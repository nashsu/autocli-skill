---
name: opencli-rs
description: Use the opencli-rs CLI to retrieve or act on supported websites and desktop apps through the user's existing Chrome login session or local desktop app session. Prefer this skill over generic browser automation when the user wants to browse, search, read feeds, inspect timelines, fetch trending content, or perform supported actions on sites like Hacker News, Reddit, YouTube, X/Twitter, Bloomberg, Google, Substack, Medium, LinkedIn, Yahoo Finance, Barchart, Discord desktop, Notion, Cursor, Codex, ChatGPT, and other opencli-rs-supported targets.
---

# opencli-rs

Use `opencli-rs` when it is a better fit than generic browser automation:
- The target site or desktop app is already supported by `opencli-rs`
- The user wants structured fetch/search/read actions
- The user wants a supported write action and the risk is acceptable
- Reusing the user's existing Chrome login state is the point

Do **not** treat this as a blanket replacement for the browser skill. If the site is unsupported, the page interaction is highly custom, or the task needs visual navigation/form work, use the browser workflow instead.

## Prerequisites

Before relying on this skill, verify the environment:
- `opencli-rs` is installed and on `PATH`
- Chrome is open and already logged into the relevant site for browser-backed commands
- The opencli-rs Chrome extension is installed when browser-backed commands are needed
- For desktop-app commands, the relevant desktop app is running

Quick checks:

```bash
opencli-rs --help
opencli-rs list
opencli-rs doctor
```

If `opencli-rs` is missing on Windows, tell the user to install it from:
- `https://github.com/nashsu/opencli-rs`

Do not run the repo's Unix shell installer on Windows.

## Operating rules

1. Prefer `--format json` whenever results will be parsed or summarized.
2. Keep requests bounded with `--limit` where supported.
3. For write actions, show the exact action first and get confirmation unless the user already clearly authorized that specific post/reply/like/follow/send action.
4. If a command fails because login state or extension state is missing, explain the exact prerequisite instead of guessing.
5. If `opencli-rs` does not support the target well, switch to the browser skill rather than forcing a brittle workaround.

## Common command patterns

If you need quick examples for common targets, read `references/command-subsets.md`.

General syntax:

```bash
opencli-rs <site> <command> [options] [--format json]
```

Examples:

```bash
opencli-rs hackernews top --limit 20 --format json
opencli-rs reddit search --query "openclaw" --limit 10 --format json
opencli-rs youtube search --query "LLM tutorial" --limit 10 --format json
opencli-rs google search OpenClaw --limit 10 --format json
opencli-rs twitter timeline --limit 20 --format json
opencli-rs barchart options --symbol SPY --format json
opencli-rs yahoo-finance quote --symbol AAPL --format json
opencli-rs notion search --query "meeting notes" --format json
opencli-rs cursor status --format json
```

## Supported-use guidance

Typical good fits:
- News/feed/trending pulls from supported sites
- Search across supported sites
- Reading saved/bookmarked/history content where supported
- Pulling quotes/options chains from supported finance targets
- Interacting with supported desktop apps through their existing local session

Higher-risk actions that need confirmation unless already explicitly authorized:
- posting
- replying
- liking/upvoting
- following/unfollowing
- commenting
- sending desktop-app messages
- deleting content

## Failure handling

If a command errors:
1. Re-run with a smaller scope if appropriate.
2. Check `opencli-rs doctor`.
3. Verify Chrome/app/login/extension prerequisites.
4. If the target is unsupported or the flow is too custom, switch to the browser skill.

## Notes

- This skill complements, not replaces, browser automation.
- Prefer native platform tools when they already cover the task better.
- Use `opencli-rs` mainly when the value is access via the user's authenticated local browser/app session.

## Source

Based on:
- Skill repo: `https://github.com/nashsu/opencli-rs-skill`
- Upstream CLI: `https://github.com/nashsu/opencli-rs`

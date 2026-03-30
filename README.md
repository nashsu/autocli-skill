# opencli-rs-skill

> The perfect companion for ClaudeCode/OpenClaw/Agent. Give your AI Agent the ability to reach information across the entire web, fetching real-time data from Bilibili, Zhihu, Twitter/X, YouTube, Weibo, Reddit, Facebook, Instagram, TikTok, Notion, Cursor and 55+ platforms with natural language — reusing your Chrome login session, no API keys needed. Blazing fast Rust binary.

---

## What is this?

Have you ever wanted OpenClaw/Claude/AI to:
- Browse **Bilibili** trending, search **Zhihu**, check **Weibo** hot topics
- Search **YouTube**, get **Reddit** posts, read **HackerNews**
- Check **stock prices** on Yahoo Finance or Xueqiu
- Post a **tweet** or search your **Twitter** timeline
- Control **Cursor**, **Notion**, **ChatGPT**, **Discord** desktop apps from CLI
- Integrate **GitHub CLI**, **Docker**, **kubectl** through a unified interface

...but OpenClaw/Claude/AI has no access to these platforms?

**This skill bridges that gap.**

It wraps [opencli-rs](https://github.com/nashsu/opencli-rs) — a blazing fast Rust CLI tool that turns **55+ major platforms into command-line interfaces** by **reusing your existing Chrome login sessions**. No API keys. No re-authentication. Single 4.7MB binary with zero runtime dependencies. Just download and go.


## Prerequisites

Before installation, check that you have all of these:

- [ ] **Chrome browser** open and logged in to your target platforms
- [ ] **opencli-rs Chrome Extension** installed (for browser commands) — [Download from GitHub Releases](https://github.com/nashsu/opencli-rs/releases/latest)


## Installation

**Step 1 — Install the opencli-rs CLI tool**

See: https://github.com/nashsu/opencli-rs

**Step 2 — Install this skill**

**Method 1: Let Claude/OpenClaw/Any AI agent install for you**

```
Help me install this skill: https://github.com/ebothegreat/opencli-rs-skill
```

**Method 2: Manual Install**
```bash
npx skills add https://github.com/ebothegreat/opencli-rs-skill
```

That's it! Restart Claude Code to activate the skill.

## Supported Platforms (55+)

| Platform | Mode | Key Commands |
|----------|------|-------------|
| HackerNews | Public | `top` `new` `best` `ask` `show` `jobs` `search` `user` |
| Dev.to | Public | `top` `tag` `user` |
| Lobsters | Public | `hot` `newest` `active` `tag` |
| StackOverflow | Public | `hot` `search` `bounties` `unanswered` |
| Wikipedia | Public | `search` `summary` `random` `trending` |
| Arxiv | Public | `search` `paper` |
| BBC | Public | `news` |
| Twitter/X | Browser | `trending` `bookmarks` `profile` `search` `timeline` `post` `reply` `like` `follow` `article` ... (24 cmds) |
| Bilibili | Browser | `hot` `search` `me` `favorite` `history` `feed` `subtitle` `download` ... (12 cmds) |
| Reddit | Browser | `hot` `frontpage` `popular` `search` `subreddit` `upvote` `save` `comment` ... (15 cmds) |
| Zhihu | Browser | `hot` `search` `question` `download` |
| Xiaohongshu | Browser | `search` `feed` `user` `publish` `creator-notes` ... (11 cmds) |
| YouTube | Browser | `search` `video` `transcript` |
| Weibo | Browser | `hot` `search` |
| Douban | Browser | `search` `top250` `subject` `movie-hot` `book-hot` ... (7 cmds) |
| WeRead | Browser | `shelf` `search` `book` `highlights` `notes` `ranking` ... (7 cmds) |
| Xueqiu | Browser | `feed` `hot-stock` `hot` `search` `stock` `watchlist` ... (7 cmds) |
| BOSS Zhipin | Browser | `search` `detail` `recommend` `greet` `batchgreet` ... (14 cmds) |
| Facebook | Browser | `feed` `profile` `search` `friends` `groups` `events` ... (10 cmds) |
| Instagram | Browser | `explore` `profile` `search` `follow` `like` `comment` ... (14 cmds) |
| TikTok | Browser | `explore` `search` `profile` `follow` `like` `comment` ... (15 cmds) |
| Jike | Browser | `feed` `search` `create` `like` `comment` `repost` ... (10 cmds) |
| Google | Public/Browser | `news` `search` `suggest` `trends` |
| V2EX | Public/Browser | `hot` `latest` `topic` `node` `user` `daily` `me` ... (11 cmds) |
| Bloomberg | Public/Browser | `main` `markets` `economics` `tech` `politics` ... (10 cmds) |
| Medium | Browser | `feed` `search` `user` |
| Substack | Browser | `feed` `search` `publication` |
| LinkedIn | Browser | `search` |
| Yahoo Finance | Browser | `quote` |
| Cursor | Desktop | `status` `send` `read` `new` `dump` `composer` `model` `ask` ... (12 cmds) |
| Notion | Desktop | `status` `search` `read` `new` `write` `sidebar` `favorites` `export` |
| ChatGPT | Desktop | `status` `new` `send` `read` `ask` |
| Discord | Desktop | `status` `send` `read` `channels` `servers` `search` `members` |
| Codex | Desktop | `status` `send` `read` `new` `dump` `model` `ask` ... (11 cmds) |
| Other 20+ sites | Various | See `opencli-rs --help` |

> **Mode legend:** Public = No browser needed, calls API directly; Browser = Requires Chrome + extension; Desktop = Requires the desktop app to be running


## Usage

Make sure Chrome is open and you're logged in to the target platforms, then talk to Claude naturally:

```
"Search YouTube for LLM tutorials"
"Get the top 20 stories on HackerNews"
"What's trending on Twitter right now?"
"Search Reddit r/MachineLearning for transformer papers"
"Get BBC news headlines"
"Check AAPL stock price"
"Post a tweet: Just discovered Claude Code skills!"
"What's hot on Bilibili?"
"Search Douban for top-rated movies"
"Check my WeRead highlights"
"Ask Cursor to refactor this function"
"Search Notion for meeting notes"
```

Claude automatically picks the right opencli-rs command, runs it, and displays results in a clean table with translated titles.

## Command Reference

```bash
# Bilibili
opencli-rs bilibili hot --limit 10 --format json
opencli-rs bilibili search --keyword "AI"

# Twitter/X
opencli-rs twitter timeline --format json
opencli-rs twitter post --text "Hello from Claude!"
opencli-rs twitter search "claude AI" --limit 10

# YouTube
opencli-rs youtube search --query "LLM tutorial"

# HackerNews
opencli-rs hackernews top --limit 20 --format json

# Reddit
opencli-rs reddit hot --subreddit MachineLearning

# Yahoo Finance
opencli-rs yahoo-finance quote --symbol AAPL

# Douban
opencli-rs douban top250 --format json
```


## Troubleshooting

| Problem | Fix |
|---------|-----|
| `opencli-rs: command not found` | Re-run the install script; check your PATH |
| Chrome not being controlled | Make sure Chrome is open; verify opencli-rs Chrome extension is loaded |
| Login state not recognized | In Chrome, manually log in to the target site first |
| Browser commands timeout | Check `opencli-rs doctor` for diagnostics |

## Credits

Built on **[nashsu/opencli-rs](https://github.com/nashsu/opencli-rs)** — a complete Rust rewrite of opencli, up to 12x faster with 10x less memory.

## License

Apache 2.0

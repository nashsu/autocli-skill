# 🌐 opencli-rs-skill

> *The perfect companion for Claude, OpenClaw & AI agents. Give your AI Agent the ability to reach information across the entire web, fetching real-time data from 55+ platforms with natural language — reusing your Chrome login session, no API keys needed. Blazing fast Rust binary.*

[![License](https://img.shields.io/badge/license-Apache%202.0-blue?style=flat-square)](LICENSE)
[![GitHub](https://img.shields.io/badge/GitHub-ebothegreat%2Fopenrcli--rs--skill-black?style=flat-square&logo=github)](https://github.com/ebothegreat/opencli-rs-skill)
[![Built on](https://img.shields.io/badge/Built%20on-nashsu%2Fopenrcli--rs-orange?style=flat-square)](https://github.com/nashsu/opencli-rs)
[![Platforms](https://img.shields.io/badge/Platforms-55%2B-green?style=flat-square)](https://github.com/ebothegreat/opencli-rs-skill)

---

## Table of Contents

- [What is This?](#what-is-this)
- [Prerequisites](#prerequisites)
- [Quick Start](#quick-start)
- [Supported Platforms](#supported-platforms-55)
- [Core Features](#core-features)
- [Usage Examples](#usage-examples)
- [Command Reference](#command-reference)
- [Troubleshooting](#troubleshooting)
- [Contributing & License](#contributing--license)

---

## What is This?

Have you ever wanted Claude/OpenClaw/AI to:
- Browse **Bilibili** trending, search **Zhihu**, check **Weibo** hot topics
- Search **YouTube**, get **Reddit** posts, read **HackerNews**
- Check **stock prices** on Yahoo Finance or Xueqiu
- Post a **tweet** or search your **Twitter** timeline
- Control **Cursor**, **Notion**, **ChatGPT**, **Discord** desktop apps from CLI
- Integrate **GitHub CLI**, **Docker**, **kubectl** through a unified interface

...but Claude/AI had no access to these platforms?

**This skill bridges that gap.**

It wraps [opencli-rs](https://github.com/nashsu/opencli-rs) — a blazing fast Rust CLI tool that turns **55+ major platforms into command-line interfaces** by **reusing your existing Chrome login sessions**. No API keys. No re-authentication. Single 4.7MB binary with zero runtime dependencies. Just download and go.

---

## Prerequisites

Before installation, ensure you have:

- [ ] **Chrome browser** open and logged in to your target platforms
- [ ] **opencli-rs Chrome Extension** installed (for browser commands)
  → [Download from GitHub Releases](https://github.com/nashsu/opencli-rs/releases/latest)
- [ ] **Node.js** (for skill installation via `npx`)
- [ ] **Claude Code** or compatible AI agent

---

## Quick Start

### Step 1 - Install opencli-rs CLI tool

Visit: https://github.com/nashsu/opencli-rs

### Step 2 - Install this skill

**Option A: Let Claude install for you**
```
Help me install this skill: https://github.com/ebothegreat/opencli-rs-skill
```

**Option B: Manual install**
```bash
npx skills add https://github.com/ebothegreat/opencli-rs-skill
```

### Step 3 - Verify installation

```bash
opencli-rs --version
```

Restart Claude Code to activate the skill.

---

## Supported Platforms (55+)

### Public APIs (No browser required)
HackerNews, Dev.to, StackOverflow, Wikipedia, BBC News, Google

### Browser-based (Requires Chrome + extension)
Twitter/X, YouTube, Reddit, Bilibili, Zhihu, Weibo, Instagram, TikTok, Facebook, Douban, WeRead, Yahoo Finance, Xueqiu, BOSS Zhipin, and 20+ more

### Desktop Apps (Requires app to be running)
Cursor, Notion, ChatGPT, Discord

---

## Core Features

| Feature | Description |
|---------|-------------|
| **55+ Platform Support** | Access Twitter, YouTube, Reddit, Bilibili, Zhihu, and many more |
| **Chrome Session Reuse** | No API keys, no OAuth hassles — uses your existing Chrome login |
| **Desktop App Control** | Control Cursor, Notion, ChatGPT, Discord from CLI |
| **Natural Language** | Talk to Claude naturally; it picks the right command |
| **High Speed** | Single 4.7MB Rust binary, zero dependencies |
| **Public API Fallback** | Many platforms work without browser |

---

## Usage Examples

With Chrome open and logged in:

```
"Search YouTube for LLM tutorials"
"Get the top 20 stories on HackerNews"
"What's trending on Twitter right now?"
"Search Reddit r/MachineLearning for transformer papers"
"Check AAPL stock price"
"What's hot on Bilibili?"
"Search Douban for top-rated movies"
"Ask Cursor to refactor this function"
```

---

## Command Reference

```bash
opencli-rs hackernews top --limit 20
opencli-rs twitter timeline
opencli-rs youtube search --query "AI tutorial"
opencli-rs reddit hot --subreddit MachineLearning
opencli-rs bilibili hot
opencli-rs yahoo-finance quote --symbol AAPL
```

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Browser commands timeout | Ensure Chrome is running; check `opencli-rs doctor` |
| Login state not recognized | Manually log in to site in Chrome first |
| Command not found | Verify installation: `which opencli-rs` |
| Chrome not being controlled | Verify extension is enabled |

---

## License

Apache 2.0

---

**Questions?** Open an issue on [GitHub](https://github.com/ebothegreat/opencli-rs-skill/issues)

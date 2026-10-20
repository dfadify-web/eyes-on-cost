# Eyes on Cost

**An [Eyes on Claude](https://github.com/dfadify-web/eyes-on-claude) extension.** What your Claude Code sessions would cost on the API, live: real tokens per response, cache hit rate and savings, spend per session, model and minute.

[Español](README.es.md)

![Eyes on Cost](docs/screenshot.png)

## What it does

- API-equivalent spend from the real `usage` of every response (input, cache write, cache read, output).
- Prompt-cache hit rate and money saved by the cache.
- Burn rate ($/h over the last 10 min), cumulative and per-minute chart.
- Spend per session, per model and the most expensive requests.
- Official Anthropic prices table (Opus 5.5, Sonnet 5.5, Haiku 5.5, Fable 5.1, 4.x…).

Everything comes from the real Eyes on Claude stream (Claude Code transcripts): nothing is guessed.

## Install

Requires Eyes on Claude **v2.3+** and Node 18+.

```bash
npx -y github:dfadify-web/eyes-on-cost
```

Open Eyes on Claude → **Extensions** → **Eyes on Cost** (`http://localhost:7777/#ext/eyes-on-cost`). Uninstall with `npx -y github:dfadify-web/eyes-on-cost --uninstall`.

Standalone: `node server.js` → `http://localhost:7779` (needs Eyes on Claude running on :7777).

## How it works

A zero-dependency Node server (`server.js`) serves `public/` and proxies Eyes on Claude's live `/events` stream. It only listens on 127.0.0.1.

MIT © dfadify-web

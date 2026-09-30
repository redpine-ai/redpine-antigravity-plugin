# Redpine Connect for Antigravity and Gemini CLI

Redpine searches licensed publisher collections and open-access research, as full text rather than abstracts. Every result is cited to its source, and publishers are paid when their content is used.

Web search returns abstracts, paywalls, and citations that cannot be checked. Redpine returns the relevant chunk of the document.

Redpine licenses full-text research directly from publishers and research institutions, and serves it to your agent over MCP alongside a large open-access corpus. One query searches both.

**Provenance by default.** Every result carries its publisher, title, publication date, and a resolvable identifier such as a DOI. Licensed content and open-access content are labeled separately, so the two are never confused inside an answer.

**You see the price first.** Any search can be previewed for free. The agent sees the title, source, and a snippet of every result, plus the exact cost to unlock them, then asks before spending anything. Unlock the three results that matter instead of the 30 that came back. The same results re-fetch free for seven days. Discovery, schema inspection, previews, and balance checks are always free.

**Built for questions where being wrong is expensive.** Clinical decisions, systematic review, research engineering, and any analysis that has to survive a source check.

An account can also hold data integrations beyond literature. The agent reads what that account is entitled to at runtime rather than assuming a fixed tool list.

Compensation flows back to the rights holders. New accounts get free queries. Credits are bought on the Redpine dashboard, and the plugin never handles payment details: it shows the price and asks before anything is charged.

Requires a Redpine account. Sign-in is OAuth on first use.

## This repo

One repo, two manifests: `plugin.json` and `mcp_config.json` make it an Antigravity plugin, `gemini-extension.json` makes it a Gemini CLI extension. Both share the same skill.

## Install

Antigravity CLI:

```
agy plugin install https://github.com/redpine-ai/redpine-antigravity-plugin
```

Gemini CLI:

```
gemini extensions install https://github.com/redpine-ai/redpine-antigravity-plugin
```

then, inside Gemini CLI, `/mcp auth redpine`.

Sign-in is OAuth against the hosted Redpine Connect server; a browser window opens on first use. New accounts get free queries; see https://app.redpine.ai for usage, docs and billing.

## What you get

- The `redpine` MCP server (`https://api.redpine.ai/mcp`)
- The `redpine-search` skill (`skills/redpine-search/`): how the preview, consent, confirm loop works, how to spend well, how to search and cite.
- `GEMINI.md` (Gemini CLI only): a short always-loaded pointer that tells Gemini when to reach for Redpine and to activate the skill first

The skill is the same one shipped in the Claude Code plugin and the OpenAI (ChatGPT and Codex) listing. Its source of truth is `redpine-ai/redpine-plugin`; copy changes from there rather than editing it here.

The plugin holds no fact the server can answer. Collections, integrations, tool lists and prices come from the server at runtime, per account.

## Update

Keep `version` in `plugin.json` and `gemini-extension.json` equal.

```
gemini extensions update redpine
```

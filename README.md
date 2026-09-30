# Redpine Connect for Gemini CLI

Licensed, non-public data for AI work in medicine, science, law, and finance, served over MCP.

## Install

```
gemini extensions install https://github.com/redpine-ai/redpine-gemini-extension
```

Then inside Gemini CLI:

```
/mcp auth redpine
```

Sign-in is OAuth against the hosted Redpine Connect server. New accounts get free queries; see https://app.redpine.ai for usage, docs and billing.

## What you get

- The `redpine` MCP server (`https://api.redpine.ai/mcp`)
- The `redpine-search` skill (`skills/redpine-search/`): how the preview, consent, confirm loop works, how to spend well, how to search and cite. Gemini CLI asks before activating it.
- `GEMINI.md`: a short always-loaded pointer that tells Gemini when to reach for Redpine and to activate the skill first

The skill is the same one shipped in the Claude Code plugin and the OpenAI (ChatGPT and Codex) listing. Its source of truth is `redpine-ai/redpine-plugin`; copy changes from there rather than editing it here.

The extension holds no fact the server can answer. Collections, integrations, tool lists and prices come from the server at runtime, per account.

## Update

```
gemini extensions update redpine
```

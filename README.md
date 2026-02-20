# Flow Weaver — Claude Code Plugin

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

Claude Code plugin for [Flow Weaver](https://github.com/synergenius-fw/flow-weaver) — the TypeScript compiler for AI agent workflows.

Provides skills, commands, hooks, and an MCP server for building visual workflows directly from Claude Code.

## Installation

```bash
claude plugin add synergenius-fw/flow-weaver-claude-plugin
```

## What's Included

### Skills

- **flow-weaver-tutorial** — Step-by-step guide to building your first workflow
- **flow-weaver-concepts** — Fundamental concepts of Flow Weaver workflows
- **flow-weaver-jsdoc-grammar** — JSDoc annotation syntax reference
- **flow-weaver-debugging** — Debugging workflows and error resolution
- **flow-weaver-error-codes** — Complete validation error/warning code reference
- **flow-weaver-export-interface** — Defining workflow input/output ports
- **flow-weaver-node-conversion** — Converting TypeScript functions to node types
- **flow-weaver-iterative-development** — Test-driven workflow building
- **flow-weaver-patterns** — Create and use reusable workflow patterns
- **flow-weaver-scaffold** — Scaffold workflows and nodes from templates

### Commands

- `/fw-create` — Create a new workflow
- `/fw-build` — Build a complete workflow iteratively
- `/fw-modify` — Make targeted modifications to existing workflows
- `/fw-validate` — Validate workflow health
- `/fw-explain` — Analyze and explain how a workflow functions
- `/fw-convert` — Convert TypeScript functions to Flow Weaver node types
- `/fw-import` — Import workflows from n8n or other tools
- `/fw-export-inngest` — Export as an Inngest durable function
- `/fw-test` — Execute and test a workflow export

### MCP Server

Exposes Flow Weaver's compiler, validator, diagram generator, and more as MCP tools — enabling the visual editor integration and programmatic workflow manipulation.

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI
- Node.js >= 18
- `@synergenius/flow-weaver` installed in your project (`npm install @synergenius/flow-weaver`)

## License

MIT — see [LICENSE](./LICENSE).

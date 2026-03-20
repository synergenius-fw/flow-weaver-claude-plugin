---
description: Run a self-evolution cycle on a workflow using the Genesis protocol
argument-hint: [--init] [--project-dir <path>]
---

First, use the Skill tool to invoke:

1. flow-weaver:flow-weaver-weaver-config
2. flow-weaver:flow-weaver-concepts

Then run Genesis: $ARGUMENTS

## Prerequisites

The Weaver pack must be installed:
```bash
npm install @synergenius/flow-weaver-pack-weaver
```

## What Genesis Does

Genesis is an autonomous self-evolution protocol that:
1. **Observes** the project state (files, git, workflows)
2. **Proposes** workflow improvements using AI
3. **Validates** proposals against budget and design constraints
4. **Applies** changes with retry (up to 3 attempts with AI-driven fixes)
5. **Commits** if approved, rolls back if rejected

Safety features: snapshot-based rollback, escrow for self-modification, approval gates, stabilize mode after 3+ failures.

## Workflow

1. **Initialize** (first time only):
   ```bash
   npx flow-weaver weaver genesis --init
   ```
   Then edit `.genesis/config.json` to set `targetWorkflow`.

2. **Run a single cycle**: Use `fw_weaver_genesis` MCP tool
   - Observes project → proposes changes → applies if approved

3. **Review**: Check what changed:
   - Use `fw_describe` on the target workflow
   - Use `fw_weaver_history` to see the run outcome

## Genesis Config (.genesis/config.json)

```json
{
  "targetWorkflow": "src/my-workflow.ts",
  "intent": "What this workflow should accomplish",
  "focus": ["build", "test", "deploy"],
  "approval": { "threshold": "MINOR", "autoApprove": "COSMETIC" },
  "constraints": { "maxNodes": 12, "maxConnections": 24 }
}
```

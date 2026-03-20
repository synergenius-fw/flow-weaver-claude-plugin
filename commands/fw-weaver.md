---
description: Run the Weaver autonomous bot to create or modify workflows
argument-hint: <task-description> [--file <target>]
---

First, use the Skill tool to invoke:

1. flow-weaver:flow-weaver-weaver-config
2. flow-weaver:flow-weaver-concepts

Then execute the Weaver bot task: $ARGUMENTS

## Prerequisites

The Weaver pack must be installed:
```bash
npm install @synergenius/flow-weaver-pack-weaver
```

If no `.weaver.json` exists, initialize first:
```bash
npx flow-weaver weaver init
```

## Workflow

1. **Check setup**: Verify `.weaver.json` exists and provider is configured
   - Use `fw_weaver_providers` to list available AI providers
   - If no config exists, run `npx flow-weaver weaver init`

2. **Execute the task**: Use `fw_weaver_bot` MCP tool with:
   - `task`: The natural language task description from the user
   - `mode`: "create" for new workflows, "modify" for existing ones
   - `targets`: Array of target files (for modify mode)
   - `autoApprove`: true (Claude Code manages approval)

3. **Validate result**: After bot completes, use `fw_validate` to confirm the output

4. **Report**: Show the user:
   - What files were created/modified
   - Validation status
   - Token usage and cost (via `fw_weaver_costs`)

## Available MCP Tools

- `fw_weaver_bot` - Execute autonomous task (main tool)
- `fw_weaver_run` - Run an existing workflow with AI agent
- `fw_weaver_steer` - Control running bot (pause/resume/cancel/redirect)
- `fw_weaver_queue` - Manage task queue (add/list/clear/remove)
- `fw_weaver_status` - Get current bot session status
- `fw_weaver_history` - Query execution history
- `fw_weaver_costs` - Get AI cost summary
- `fw_weaver_providers` - List available providers
- `fw_weaver_genesis` - Run self-evolution cycle

## Modes

- **Create**: `fw_weaver_bot(task="Build a support agent workflow", mode="create")`
- **Modify**: `fw_weaver_bot(task="Add error handling", mode="modify", targets=["workflow.ts"])`
- **Read**: `fw_weaver_bot(task="Explain this workflow", mode="read", targets=["workflow.ts"])`

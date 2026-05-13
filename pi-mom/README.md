# @momhq/pi-mom

Native Pi extension for [MOM (Memory Oriented Machine)](https://github.com/momhq/mom).

Registers MOM's MCP tools directly as native Pi tools — `mom_recall`, `mom_status`, `mom_record`, and more — so the LLM can call them without going through the generic MCP gateway.

## Installation

```bash
pi install npm:@momhq/pi-mom
```

Or let `mom init` handle it automatically when it detects Pi in your project.

## Requirements

- [Pi coding agent](https://github.com/mariozechner/pi-coding-agent) installed
- [MOM](https://github.com/momhq/mom) installed and on PATH
- A `.mcp.json` with a `mom` server entry in your project (created by `mom init`)

## How it works

On Pi startup, the extension reads your `.mcp.json`, spawns `mom serve mcp` as a stdio child process, lists all tools MOM advertises, and registers each one as a native Pi tool prefixed with `mom_`. New tools added to MOM appear automatically on the next Pi session — no extension update needed.

## Related

- [MOM](https://github.com/momhq/mom) — the memory engine
- [pi-mlx-models](https://github.com/vmarinogg/pi-packages/tree/main/pi-mlx-models) — local MLX model launcher for Pi

# Starlight for Codex

The official Starlight Codex plugin installs the `$starlight` workflow and configures the hosted, OAuth-protected Starlight MCP service. It does not contain provider credentials, a local runtime, or a copy of the private Starlight platform repository.

Install from a terminal:

```bash
codex plugin marketplace add xpriment626/starlight-plugin
codex plugin add starlight@starlight
codex mcp login starlight
```

The login command opens Starlight in the browser for account authorization. Then start a new Codex task and invoke `$starlight`. A Starlight account and workspace are required to use the tools.

The signed-in setup and recovery experience lives at <https://starlight-platform.vercel.app/agent>.

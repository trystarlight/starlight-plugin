# Starlight for Codex

The official Starlight Codex plugin installs the `$starlight` workflow and configures the hosted, OAuth-protected Starlight MCP service. It does not contain provider credentials, a local runtime, or a copy of the private Starlight platform repository.

Install from a terminal:

```bash
codex plugin marketplace add xpriment626/starlight-plugin
codex plugin add starlight@starlight
codex mcp login starlight
```

The login command opens Starlight in the browser for account authorization. Then start a new Codex task and invoke `$starlight`. A Starlight account and workspace are required to use the tools.

Update an existing installation with:

```bash
codex plugin marketplace upgrade starlight
codex plugin add starlight@starlight
```

Start a new Codex task after installing, updating, or removing the plugin. Existing tasks keep the skill and tool manifest they loaded at startup.

## Public client, private platform

This repository is intentionally public because installed Codex skills and connection metadata are inspectable by the user. It contains only the public client contract: workflow instructions, plugin metadata, and the production MCP URL.

The Starlight application, database, provider routing, credentials, tenant enforcement, spend controls, audit implementation, and private prompts remain in the private hosted platform. Public installation does not grant service access; Starlight OAuth binds the client to a real account and workspace. See [`PUBLIC-BOUNDARY.md`](PUBLIC-BOUNDARY.md).

## Releases

The plugin uses strict SemVer independently from the private platform and MCP contract. `main` is release-only; immutable `vX.Y.Z` tags and GitHub Releases identify shipped bundles. Run `node scripts/validate-release.mjs` before opening a release PR. See [`RELEASING.md`](RELEASING.md) and [`CHANGELOG.md`](CHANGELOG.md).

The signed-in setup and recovery experience lives at <https://starlight-platform.vercel.app/agent>.

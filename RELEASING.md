# Releasing The Starlight Codex Plugin

The public plugin is versioned independently from the private Starlight platform and MCP contract. Releases contain no private source or credentials.

## SemVer

- **Patch** — the default for changes to the existing Starlight skill, including workflow guidance, support for backward-compatible server tools, security hardening, instructions, diagnostics, metadata, compatibility, and connection fixes.
- **Minor** — a new independently discoverable public surface such as another skill, command, app, connector, MCP server, or permission class.
- **Major** — required client migration or intentionally breaking workflow expectations.

Editing `SKILL.md`, teaching the existing skill another workflow, or releasing a compatible platform/MCP update does not by itself justify a minor plugin bump. A platform release does not imply a plugin release.

Public releases use clean strict SemVer. Do not publish `+codex.*` cachebuster versions; those suffixes are only for local development.

## Release procedure

1. Branch from current `main`.
2. Change only public client material. Re-run the public-boundary review.
3. Bump `plugins/starlight/.codex-plugin/plugin.json` and add the same version to `CHANGELOG.md`.
4. Run:

   ```bash
   node scripts/validate-release.mjs
   python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-creator/scripts/quick_validate.py" plugins/starlight/skills/starlight
   python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/plugin-creator/scripts/validate_plugin.py" plugins/starlight
   ```

5. Push, open a PR, and require green public CI.
6. Merge to `main` and tag the exact merge commit:

   ```bash
   git tag -a vX.Y.Z -m "Starlight Codex Plugin X.Y.Z"
   git push origin vX.Y.Z
   ```

7. The release workflow verifies tag/version equality and creates the GitHub Release.
8. Prove a clean install from the public repository.
9. For releases after the first, prove marketplace refresh and reinstall.
10. Start a fresh Codex task and verify the loaded skill path and MCP URL.

## Customer install and update

Install:

```bash
codex plugin marketplace add trystarlight/starlight-plugin
codex plugin add starlight@starlight
codex mcp login starlight
```

Update:

```bash
codex plugin marketplace upgrade starlight
codex plugin add starlight@starlight
```

An already-running task retains its startup manifest. Filesystem or cache state and a fresh task are the reliable update proof.

## Correction

Never move a release tag. Publish a patch release, keep the previous release visible, and mark it superseded with a link to the replacement. Re-run clean install/update proof for any correction involving marketplace metadata, OAuth resource behavior, MCP configuration, or bundled skill instructions.

# Changelog

All notable public Starlight Codex plugin releases are recorded here. The private platform and MCP contract have independent versions.

## [0.2.0] - 2026-07-16

### Added

- Workspace, scope, MCP compatibility, provider-readiness, pause, and recovery checks through the hosted `get_workspace_status` tool.
- Deliberate one-to-four identity candidate planning while retaining Starlight's two-candidate default.
- Current-plan readiness summaries and a clear handoff to the single human `Approve and start` action.
- Bounded post-start operation polling with explicit review, failure, blocker, and fixture handling.

### Changed

- Required plans to be re-read through authoritative operations before describing routes, attempt ceilings, maximum cost, or execution readiness.

## [0.1.2] - 2026-07-16

### Added

- Fail-closed handling for prompt injection in account content, ambiguous writes, workspace/ID reuse, and client/schema incompatibility.
- Public/private architecture boundary and operator release runbook.
- Strict release validator, pull-request CI, immutable tag validation, and GitHub Release automation.
- Explicit marketplace refresh, reinstall, and fresh-task update instructions.

## [0.1.1] - 2026-07-16

### Fixed

- Let Codex derive the OAuth resource so authorization requests contain one resource parameter.

## [0.1.0] - 2026-07-16

### Added

- Initial account-installed `$starlight` workflow and production hosted MCP configuration.

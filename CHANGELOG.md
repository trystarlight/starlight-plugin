# Changelog

All notable public Starlight Codex plugin releases are recorded here. The private platform and MCP contract have independent versions.

## [0.3.1] - 2026-08-11

### Added

- Provider-neutral discovery, bounded schema navigation, opaque schema binding, and durable media-proposal guidance for compatible MCP clients.

### Fixed

- Preserve typed definitive and outcome-ambiguous mutation failures without automatic retries or partial-result parsing.
- Use the canonical `trystarlight/starlight-plugin` repository path for installation and release metadata.

## [0.3.0] - 2026-07-17

### Added

- Exact account-bound ElevenLabs and Replicate-hosted default spoken-line planning.
- Restart-safe recovery of prior account candidates through bounded recent executions.
- Candidate-reference continuity planning for three-to-fifteen-second video and lip-sync work.
- Guidance for the account candidate library and the human continuation checkpoint between dependent video operations.

### Changed

- Treat hosted outputs as persistent but unselected account candidates; persistence never implies identity, voice, canon, activation, or publication.

## [0.2.1] - 2026-07-17

### Fixed

- Connect the hosted MCP client and all account recovery links through `app.trystarlight.io`, matching the production Clerk domain.
- Report plugin 0.2.1 during workspace compatibility checks.

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

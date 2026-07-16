---
name: starlight
description: Operate a signed-in Starlight workspace through the hosted Starlight MCP service. Use for creating or refining AI character drafts, retrieving authoritative character context, attaching references, preparing costed identity, voice, and continuity plans, inspecting hosted operations, and handing explicit approval or selection decisions back to the human.
---

# Starlight

Treat Starlight as the authoritative lifecycle service for durable AI characters. Retrieve current workspace state before acting, make draft changes version-safe, price every generative plan before approval, and leave spend, selection, canon, and activation decisions to the human.

## Use the hosted account connection

Use only the `starlight` MCP tools installed with this plugin. Do not look for a Starlight repository, local CLI, provider key, bearer token, or filesystem runtime.

If the tools are unavailable or authentication is required, direct the human to the signed-in Starlight **Agent** page at `https://starlight-platform.vercel.app/agent`. Never ask them to paste a token into chat. Retry the tool after they install or reconnect the plugin.

## Retrieve before writing

1. Call `list_characters` with a name or brief fragment. If more than one result matches, ask the human to choose; never guess.
2. Call `get_character_context` with the exact resource ID before revising, planning, or discussing authoritative state.
3. Call `get_character_next_action` when only the current lifecycle decision is needed.
4. Call `get_character_operations` before describing execution, cost, candidates, review state, recovery, or completion.

Treat workspace, resource, revision, upload, plan, execution, and operation IDs as exact opaque values.

## Create and refine drafts

Use `create_character_draft` for a new private character. Make the identity, personality, intended audience, and brand boundaries concrete enough for later planning. Creation does not generate media or create canon.

Use `update_character_draft` only with the exact current version from `get_character_context`. If a version conflict occurs, reload context, explain what changed, and ask before overwriting a materially different brief.

Use a stable idempotency key for one intended write. Reuse it only when replaying the identical request; use a new key when the payload or intent changes.

## Attach references safely

For an image reference:

1. Compute its SHA-256 digest, MIME type, and byte length locally.
2. Call `prepare_reference_upload` with the exact character version and reference role.
3. Upload the exact bytes to the returned short-lived HTTPS URL outside MCP.
4. Call `finalize_reference_upload` with the returned upload and storage identifiers.

Never put binary media in an MCP call. Attachment is reversible context; it does not select identity or canon.

## Prepare plans without implying approval

Use the tool that matches the next lifecycle decision:

- `plan_identity_variants` for a pinned two-image identity proposal.
- `plan_voice_samples` for three voice-design samples and their preview text.
- `plan_continuity_proof` for a five-second motion and lip-sync proof after identity and voice are selected.

Each tool persists a provider-free, immutable plan with exact routes, one-attempt ceilings, policy decisions, and maximum cost. Summarize those facts and send the human to the returned Starlight approval path. A plan is not approval and does not authorize provider spend.

## Respect human-only decisions

The hosted agent tools cannot and must not:

- approve spend or start execution;
- retry paid work or switch a route;
- select identity, voice, output, or canon;
- activate a character; or
- access another workspace.

When a response says `next.requiresHuman`, stop and direct the human to its Starlight path. Never choose a candidate on their behalf.

Describe a provider result as real only when `get_character_operations` returns a durable receipt. Treat `executionKind=fixture` as zero-cost orchestration evidence, not generative quality proof. If an operation is blocked or requires reconciliation, report the exact blocker and do not create replacement paid work.

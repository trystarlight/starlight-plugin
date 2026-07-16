# Public Plugin Boundary

The Starlight Codex plugin is public because every installed skill and connection manifest is inspectable and editable on the user's machine. Public distribution is not public platform access and does not publish the Starlight product source.

## Included here

- `$starlight` workflow instructions;
- plugin and marketplace metadata;
- the production hosted MCP URL;
- validation and release automation; and
- install, update, compatibility, and recovery documentation.

## Kept in the private platform

- application and control-plane source;
- database schema and tenant data;
- OAuth, authorization, workspace isolation, and audit implementation;
- provider credentials, private archive configuration, and billing data;
- route-selection implementation, capacity policy, and anti-abuse controls; and
- private prompts, evaluations, and operational evidence.

## Security model

The plugin is a convenience and guidance layer. A user can edit it or call the MCP protocol without it. Therefore the private server—not skill prose—must enforce every security, privacy, spend, lifecycle, and canon boundary.

The MCP endpoint is publicly discoverable but account-gated. Installation alone grants nothing. OAuth binds a client to an authenticated Starlight account, selected workspace, declared scopes, and revocable grant.

Do not commit secrets or vulnerability details to a public issue. Remove credentials from any reproduction before sharing it with this repository's maintainers.

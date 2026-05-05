# Security and privacy notes

This public repository is intentionally limited to a portfolio-safe evidence layer. It documents the system architecture without publishing source code, credentials, deployment payloads or proprietary implementation details.

## Credential handling

- API keys are not embedded in the add-in source code or installer.
- Users configure providers after installation through the service configuration dialog or optional desktop configuration tool.
- Configuration is stored per Windows user under `%LocalAppData%\PEM DocGenerator\config.dat`.
- The configuration file is DPAPI-encrypted with current-user scope.
- Saving configuration updates the in-memory `ConfigurationStore.Current`, so subsequent API calls immediately use the latest settings.

## Network and provider boundaries

- AI calls are routed only to the configured Azure OpenAI or OpenAI Direct endpoints.
- Kroki is used for chart/diagram rendering when configured.
- TLS 1.2 is enforced at startup.
- A shared HTTP client pattern is used for AI calls to avoid socket exhaustion.

## Model verification

The service configuration dialog uses a staged discovery process:

1. list provider candidates,
2. filter them by task purpose,
3. verify chat-capable candidates with bounded concurrent pings,
4. expose only successful candidates in the UI.

![API verification pipeline](assets/api-verification-pipeline.svg)

## Portfolio-safe publication boundary

The following are deliberately excluded from this repository:

- production source code,
- prompts and private generation templates,
- binary installer payloads,
- API keys and configuration files,
- endpoint names and deployment IDs,
- internal datasets or customer material.

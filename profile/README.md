# Sinetti

Sinetti is a multi-protocol identity and authentication platform that operators
run themselves. It supports OAuth 2.1, OpenID Connect, SAML, WebAuthn and
passkeys, and Biscuit tokens, with multi-tenant isolation, pluggable identity
providers, and deployment targets spanning edge platforms and standalone
servers.

The name is Finnish for "seal", an instrument of trust and verification.
Identity infrastructure should be effortless and invisible, earning trust
through cryptographic certainty rather than shared secrets.

## What Sinetti provides

- **Multi-protocol authentication**: Sinetti runs an OAuth 2.1 authorisation
  server, an OpenID Connect provider, and a SAML identity provider. It issues
  and verifies Biscuit tokens, and accepts WebAuthn and passkey credentials.
- **Multi-tenant isolation**: Each tenant holds its own configuration,
  cryptographic keys, and credential storage.
- **Pluggable identity providers**: A plugin model extends the platform with
  custom authentication factors, identity sources, and token formats.
- **Edge and standalone deployment**: Operators run Sinetti as a self-hosted
  binary, or deploy it to Fastly Compute to place authentication closer to the
  people it serves.
- **gRPC and HTTP interfaces**: A native gRPC service with Protocol Buffer
  definitions sits alongside the HTTP authentication endpoints.
- **Observability**: Sinetti emits structured logs, metrics, and OpenTelemetry
  traces.

## Repositories

These repositories mirror their canonical counterparts on
[GitLab](https://gitlab.com/sinetti).

| Repository | Purpose |
|---|---|
| [architecture](https://github.com/sinetti-dev/architecture) | Decisions and comments recording the platform's architecture |
| [oauth](https://github.com/sinetti-dev/oauth) | OAuth 2.0 and OpenID Connect consumer and provider libraries |
| [mockoidc-rs](https://github.com/sinetti-dev/mockoidc-rs) | Mock OpenID Connect issuer for integration testing |

GitLab hosts the full set, which also covers the Protocol Buffer and WebAssembly
interface specifications, the Kivi proof of concept, the generated gRPC stubs,
and the Fastly Compute deployment. Further repositories are mirrored here as the
project matures.

## Current status

Sinetti is in active development. Kivi is the proof of concept, and it exercises
the OpenID Connect provider, the plugin architecture, and the gRPC management
API together. The OAuth libraries and a mock OpenID Connect issuer for
integration testing are published alongside it. The specifications repositories
hold the interface definitions the other repositories build against.

Architectural work is public. Core design choices, among them multi-tenant
isolation, the plugin architecture, token management, and protocol conformance,
are proposed and recorded before they are built. The [architecture
repository](https://gitlab.com/sinetti/specifications/architecture) holds what
is currently under discussion.

## Contributing

Contributions are welcome, and the architecture repository is the place to
start. Review the open proposals, comment on merge requests, or submit a
decision or comment of your own. Its [contribution
guide](https://gitlab.com/sinetti/specifications/architecture/-/blob/trunk/CONTRIBUTING.md)
explains how. You do not need to be a maintainer to take part.

Raise contributions on GitLab rather than here, since the repositories in this
organisation are mirrors. Guidelines for code, testing, and documentation are
not yet published.

## Licensing

- **Platform code**: dual-licensed under LGPL 3.0 and MPL 2.0. This combination
  ensures strong copyleft protections for the core platform while allowing
  integration into a broad range of projects through MPL 2.0's file-level
  copyleft.
- **Architecture proposals**: CC BY-SA 4.0. Design documents and architectural
  decisions are shared knowledge.

## Governance

Sinetti is governed by the [Omnifi Foundation](https://omnifi.foundation), a
community-driven organisation that stewards open source projects. The
[handbook](https://handbook.omnifi.foundation/engineering/architecture/) defines
how proposals are written, reviewed, and decided, and it applies equally to all
contributors.

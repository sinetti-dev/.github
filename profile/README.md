# Sinetti

**An open source identity and authentication platform built in Rust.**

Sinetti is a multi-protocol identity platform that provides authentication and
authorisation for modern applications. It supports OAuth 2.1, OpenID Connect,
SAML, WebAuthn/passkeys, and Biscuit tokens — with multi-tenant isolation,
pluggable identity providers, and deployment targets spanning edge platforms
and standalone servers.

The name is Finnish for "seal" — an instrument of trust and verification.
Identity infrastructure should be effortless and invisible, earning trust through
cryptographic certainty rather than shared secrets.

## Why Sinetti

Existing identity solutions force operators to choose between control and
capability:

- **Managed identity services** like Auth0 and Okta provide convenience but
  lock teams into vendor-specific configurations, opaque pricing models, and
  limited extensibility for non-standard authentication flows.

- **Self-hosted platforms** like Keycloak offer flexibility but require
  significant operational overhead — JVM tuning, database management, and
  complex upgrade paths — while carrying the weight of legacy architectures.

- **Protocol-focused libraries** like Ory Hydra handle specific standards well
  but leave teams assembling multiple components to build a complete identity
  solution, with integration complexity at every seam.

Sinetti addresses these gaps. A single Rust binary provides multi-protocol
authentication with memory safety, predictable latency, and a plugin model that
lets operators extend identity flows without forking upstream code. Multi-tenant
isolation is built in from the ground up, and edge deployment via Fastly Compute
brings authentication closer to the people it serves.

## Architecture

Sinetti is in its early architecture phase. The following repositories are part
of the project:

| Repository | Purpose |
|---|---|
| [architecture](https://github.com/sinetti-dev/architecture) | Architectural proposals (ADRs and RFCs) |

Additional repositories will be mirrored from GitLab as the project matures.

## Current status

Sinetti has existing runtime, framework, and protocol repositories on GitLab.
The project is establishing its architectural foundations through architecture
decision records and requests for comments to guide the next phase of
development. This deliberate approach ensures that core design choices —
multi-tenant isolation, plugin architecture, token management, and protocol
conformance — are well-reasoned and documented.

Browse the [architecture repository](https://github.com/sinetti-dev/architecture)
to see proposals in progress and join the discussion.

## Key features

- **Multi-protocol authentication** — OAuth 2.1 authorisation server, OpenID
  Connect provider, SAML identity provider, WebAuthn/passkey support, and
  Biscuit token issuance and verification.
- **Multi-tenant isolation** — tenant-scoped configuration, cryptographic key
  separation, and isolated credential storage.
- **Pluggable identity providers** — extensible plugin model for custom
  authentication factors, identity sources, and token formats.
- **Edge deployment** — Fastly Compute support brings authentication and
  authorisation closer to the people it serves.
- **gRPC and HTTP interfaces** — native gRPC service with protocol buffer
  definitions alongside HTTP authentication endpoints.
- **Structured logging, metrics, and OpenTelemetry** — production-grade
  observability built in.

## Contributing

Sinetti is a Rust project and contributions are welcome. During the current
architecture phase, the best way to contribute is through the
[architecture repository](https://github.com/sinetti-dev/architecture) — review
open proposals, comment on pull requests, or submit your own ADR or RFC.

Once implementation begins, contribution guidelines for code, testing, and
documentation will be published in each repository.

## Licensing

- **Platform code** — dual-licensed under LGPL 3.0 and MPL 2.0. This
  combination ensures strong copyleft protections for the core platform while
  allowing integration into a broad range of projects through MPL 2.0's
  file-level copyleft.
- **Architecture proposals** — CC BY-SA 4.0. Design documents and architectural
  decisions are shared knowledge.

## Governance

Sinetti is governed by the [Omnifi Foundation](https://omnifi.foundation), a
community-driven organisation that stewards open source projects. The
architecture decision process — how proposals are written, reviewed, and
decided — is defined in the
[Omnifi Foundation handbook](https://handbook.omnifi.foundation/engineering/architecture/)
and applies equally to all contributors.

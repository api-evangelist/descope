# Descope (descope)

Descope is a customer and agentic identity access management (CIAM) platform founded in 2022 by veterans of Sentrigo and Demisto (acquired by Palo Alto Networks). Its signature is drag-and-drop Descope Flows — a visual authentication-flow builder — paired with passwordless methods (passkeys, magic link, OTP, social, biometric), risk-based MFA, SSO/SAML/SCIM, fine-grained authorization, and a growing Agentic Identity Hub that issues scoped OAuth tokens to AI agents and MCP servers. Descope ships SDKs for every mainstream language and framework, a CLI, Terraform/Pulumi providers, self-hostable hosted-auth app, and prebuilt migration tools from Auth0, Cognito, Firebase, and Keycloak. Free tier covers 7,500 MAUs forever; paid tiers start at $249/month.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/descope/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/descope/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Authentication
- Identity
- CIAM
- Passwordless
- Passkeys
- MFA
- SSO
- OAuth
- OIDC
- SAML
- SCIM
- Authorization
- FGA
- Agentic Identity
- MCP

## Timestamps

- **Created:** 2026-05-25T00:00:00.000Z
- **Modified:** 2026-05-25

## APIs

### Descope Authentication API

Public, end-user-facing authentication API covering every Descope login experience — One-Time Passwords (email/SMS/voice/IM), Magic Link, Enchanted Link, OAuth/Social, One-Tap, nOTP, TOTP authenticator apps, WebAuthn/Passkeys, password authentication, security questions, recovery codes, SSO/SAML, access keys, session refresh, tenant selection, and IdP-initiated logout. All flows expose `signup`, `signin`, `signup-in`, `verify`, and `update` endpoints where applicable so frontends and mobile SDKs can compose any journey Descope Flows can render.

- **Human URL:** [https://docs.descope.com/api](https://docs.descope.com/api)
- **Base URL:** `https://api.descope.com`

#### Tags

- Authentication
- Passwordless
- OAuth
- OIDC
- SAML
- WebAuthn
- Passkeys
- MFA

#### Properties

- [Documentation](https://docs.descope.com/api)
- [Documentation](https://docs.descope.com/auth-methods)
- [API Reference](https://docs.descope.com/api/openapi-spec)
- [OpenAPI](openapi/descope-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/descope.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/descope.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Descope Management API

Server-side administrative API for managing every resource in a Descope project — users, access keys, tenants, roles, permissions, groups, SSO/SAML/OIDC configuration, password policies, JWT customization, flows, widgets, localization, custom attributes, fine-grained authorization (FGA) schemas and relations, audit logs, analytics, third-party (inbound) applications, outbound connectors, project import/export, and impersonation. Authentication uses a Management Key (`sk_…`) and is required for any backend automation, CI/CD, migration, or admin tooling.

- **Human URL:** [https://docs.descope.com/manage](https://docs.descope.com/manage)
- **Base URL:** `https://api.descope.com`

#### Tags

- Management
- Administration
- Users
- Tenants
- Roles
- Permissions
- SSO
- SCIM
- Audit

#### Properties

- [Documentation](https://docs.descope.com/manage)
- [API Reference](https://docs.descope.com/api)
- [OpenAPI](openapi/descope-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/descope.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/descope.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Descope OAuth Applications API

Standards-compliant OAuth 2.1 / OIDC authorization server endpoints that let Descope act as an identity provider for inbound third-party applications and agentic clients. Covers the full `/oauth2/v1/...` surface — authorize, token, revoke, userinfo, device authorization, CIBA backchannel authorization, and dedicated agentic / MCP-server registration paths (`/oauth2/v1/apps/agentic/{project_id}/{mcp_server_id}/authorize|token`) for AI agents that need delegated user credentials. Supports PKCE, JAR (RFC 9101) request objects, DPoP, and dynamic client registration via SCIM v2.

- **Human URL:** [https://docs.descope.com/inbound-apps](https://docs.descope.com/inbound-apps)
- **Base URL:** `https://api.descope.com`

#### Tags

- OAuth
- OIDC
- Inbound Apps
- Third-Party
- Federation
- MCP

#### Properties

- [Documentation](https://docs.descope.com/inbound-apps)
- [OpenAPI](openapi/descope-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/descope.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/descope.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Descope SCIM 2.0 API

System for Cross-domain Identity Management (SCIM) 2.0 endpoints under `/scim/v2/` for automated user and group lifecycle provisioning from upstream IdPs (Okta, Entra ID, Google Workspace, JumpCloud, etc.) into Descope tenants. Implements the standard Users, Groups, ResourceTypes, Schemas, and ServiceProviderConfig resources required for enterprise self-service SSO.

- **Human URL:** [https://docs.descope.com/scim](https://docs.descope.com/scim)
- **Base URL:** `https://api.descope.com`

#### Tags

- SCIM
- Provisioning
- Identity
- Users
- Groups

#### Properties

- [Documentation](https://docs.descope.com/scim)
- [OpenAPI](openapi/descope-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/descope.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/descope.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Descope JWKS and Discovery API

Public key and discovery endpoints used by any RP that needs to validate Descope-issued session JWTs without calling the API. Includes the project JWKS endpoints (`/v1/keys`, `/v2/keys`), OIDC discovery (`/.well-known/oauth-authorization-server`, `/{projectId}/.well-known/...`), and project configuration metadata. These are unauthenticated and cache-friendly.

- **Human URL:** [https://docs.descope.com/jwks](https://docs.descope.com/jwks)
- **Base URL:** `https://api.descope.com`

#### Tags

- JWKS
- Discovery
- OIDC
- Keys

#### Properties

- [Documentation](https://docs.descope.com/jwks)
- [OpenAPI](openapi/descope-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/descope.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/descope.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://www.descope.com)
- [Documentation](https://docs.descope.com)
- [Getting Started](https://docs.descope.com/getting-started)
- [API Reference](https://docs.descope.com/api/openapi-spec)
- [Console](https://app.descope.com)
- [Sign Up](https://www.descope.com/sign-up)
- [Plans](https://www.descope.com/pricing)
- [Pricing](https://www.descope.com/pricing)
- [Terms of Service](https://www.descope.com/terms)
- [Privacy Policy](https://www.descope.com/privacy)
- [Status Page](https://descopestatus.com)
- [Blog](https://www.descope.com/blog)
- [Support](https://www.descope.com/contact)
- [Case Studies](https://www.descope.com/customers)
- [Training](https://www.descope.com/learn)
- [Documentation](https://www.descope.com/learn/post/agentic-identity-hub)
- [GitHub Organization](https://github.com/descope)
- [SDK](https://github.com/descope/node-sdk)
- [SDK](https://github.com/descope/python-sdk)
- [SDK](https://github.com/descope/go-sdk)
- [SDK](https://github.com/descope/descope-java)
- [SDK](https://github.com/descope/descope-dotnet)
- [SDK](https://github.com/descope/descope-php)
- [SDK](https://github.com/descope/descope-ruby-sdk)
- [SDK](https://github.com/descope/descope-swift)
- [SDK](https://github.com/descope/descope-kotlin)
- [SDK](https://github.com/descope/descope-react-native)
- [SDK](https://github.com/descope/descope-flutter)
- [SDK](https://github.com/descope/descope-js)
- [SDK](https://github.com/descope/django-descope)
- [SDK](https://github.com/descope/passport-descope)
- [Plugins](https://github.com/descope/descope-wordpress)
- [C L I](https://github.com/descope/descopecli)
- [Tools](https://github.com/descope/terraform-provider-descope)
- [Tools](https://github.com/descope/pulumi-descope)
- [Tools](https://github.com/descope/auth-hosting)
- [Tools](https://github.com/descope/virtualwebauthn)
- [Tools](https://github.com/descope/mcp-express)
- [Tools](https://github.com/descope/mcp-go)
- [Tools](https://github.com/descope/descope-mcp)
- [Tools](https://github.com/descope/skills)
- [Tools](https://github.com/descope/ai)
- [Tools](https://github.com/descope/descope-migration)
- [Tools](https://github.com/descope/descope-auth0-migration)
- [Tools](https://github.com/descope/descope-cognito-migration)
- [Tools](https://github.com/descope/descope-firebase-migration)
- [Tools](https://github.com/descope/descope-keycloak-migration)
- [Tools](https://github.com/descope/project-cicd-template)
- [Tools](https://github.com/descope/project-gitlab-cicd-pipeline)
- [Tools](https://github.com/descope/sbt-aws-descope)
- [LinkedIn](https://www.linkedin.com/company/descope)
- [Twitter](https://twitter.com/descopeinc)
- [YouTube](https://www.youtube.com/@descopeinc)
- [Forum](https://authtown.unstructured.chat)
- [Features](undefined)
- [Use Cases](undefined)
- [Integrations](undefined)
- [Solutions](undefined)
- [Portal](https://www.descope.com)
- [Documentation](https://docs.descope.com)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com

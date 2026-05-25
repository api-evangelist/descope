# Descope (descope)
Descope is a customer and agentic identity access management (CIAM) platform founded in 2022 by veterans of Sentrigo and Demisto (acquired by Palo Alto Networks). Its signature is drag-and-drop **Descope Flows** — a visual authentication-flow builder — paired with passwordless methods (passkeys, magic link, OTP, social, biometric), risk-based MFA, SSO/SAML/SCIM, fine-grained authorization, and a growing Agentic Identity Hub that issues scoped OAuth tokens to AI agents and MCP servers. Descope ships SDKs for every mainstream language and framework, a CLI, Terraform/Pulumi providers, a self-hostable hosted-auth app, and prebuilt migration tools from Auth0, Cognito, Firebase, and Keycloak. Free tier covers 7,500 MAUs forever; paid tiers start at $249/month.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/descope/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

- Authentication, Identity, CIAM, Passwordless, Passkeys, MFA, SSO, OAuth, OIDC, SAML, SCIM, Authorization, FGA, Agentic Identity, MCP

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Plans

| Plan | Starting Price | Included MAUs | Notes |
|---|---|---|---|
| Free Forever | $0 | 7,500 | All auth methods, Flows, RBAC, MFA. No overages — upgrade to exceed. |
| Pro | $249 / month (annual) | 10,000 | Custom domain, One Tap, CI/CD, Slack support. |
| Growth | $799 / month (annual) | 25,000 | Bot protection, 1M anonymous users, SCIM, FGA. |
| Enterprise | Custom | Custom | Tiered discounts, dedicated CSE, private/on-prem deployments, premium support. |

## APIs

### Descope Authentication API
Public end-user-facing authentication API covering every Descope login experience — OTP (email/SMS/voice/IM), Magic Link, Enchanted Link, OAuth/Social, One-Tap, nOTP, TOTP, WebAuthn/Passkeys, password, security questions, recovery codes, SSO/SAML, access keys, session refresh, tenant selection, and IdP-initiated logout.

**Human URL:** [https://docs.descope.com/api](https://docs.descope.com/api)

- [Documentation](https://docs.descope.com/api)
- [API Reference](https://docs.descope.com/api/openapi-spec)
- [OpenAPI](openapi/descope-openapi.yml)

### Descope Management API
Server-side administrative API for managing every resource in a Descope project — users, access keys, tenants, roles, permissions, groups, SSO, password policies, JWT settings, flows, widgets, localization, custom attributes, FGA, audit logs, analytics, inbound apps, outbound connectors, project import/export, and impersonation. Authenticated with a Management Key (`sk_…`).

**Human URL:** [https://docs.descope.com/manage](https://docs.descope.com/manage)

- [Documentation](https://docs.descope.com/manage)
- [OpenAPI](openapi/descope-openapi.yml)

### Descope OAuth Applications API
OAuth 2.1 / OIDC authorization-server endpoints (`/oauth2/v1/...`) that let Descope act as an IdP for inbound third-party apps and agentic clients. Includes authorize, token, revoke, userinfo, device authorization, CIBA backchannel, and dedicated agentic / MCP-server registration paths. Supports PKCE, JAR (RFC 9101), DPoP, and SCIM-based dynamic client registration.

**Human URL:** [https://docs.descope.com/inbound-apps](https://docs.descope.com/inbound-apps)

- [OpenAPI](openapi/descope-openapi.yml)

### Descope SCIM 2.0 API
SCIM 2.0 endpoints under `/scim/v2/` for automated user/group lifecycle provisioning from upstream IdPs (Okta, Entra ID, Google Workspace, JumpCloud) into Descope tenants.

- [OpenAPI](openapi/descope-openapi.yml)

### Descope JWKS and Discovery API
Public key and discovery endpoints used by any RP that needs to validate Descope-issued session JWTs without an API call. Includes `/v1/keys`, `/v2/keys`, OIDC discovery, and project configuration metadata.

- [OpenAPI](openapi/descope-openapi.yml)

## SDKs

**Backend:** [Node.js](https://github.com/descope/node-sdk) · [Python](https://github.com/descope/python-sdk) · [Go](https://github.com/descope/go-sdk) · [Java](https://github.com/descope/descope-java) · [.NET](https://github.com/descope/descope-dotnet) · [PHP](https://github.com/descope/descope-php) · [Ruby](https://github.com/descope/descope-ruby-sdk)

**Mobile:** [Swift (iOS)](https://github.com/descope/descope-swift) · [Kotlin (Android)](https://github.com/descope/descope-kotlin) · [React Native](https://github.com/descope/descope-react-native) · [Flutter](https://github.com/descope/descope-flutter)

**Web / Frontend:** [descope-js](https://github.com/descope/descope-js) (React, Next.js, Vue, Angular, Web Components)

**Framework plugins:** [Django](https://github.com/descope/django-descope) · [Passport.js](https://github.com/descope/passport-descope) · [WordPress](https://github.com/descope/descope-wordpress)

## Tools

- [descopecli](https://github.com/descope/descopecli) — Project snapshot / import / export / CI/CD
- [Terraform Provider](https://github.com/descope/terraform-provider-descope)
- [Pulumi Provider](https://github.com/descope/pulumi-descope)
- [Auth Hosting](https://github.com/descope/auth-hosting) — Self-hostable React app for hosted Flows
- [VirtualWebAuthn](https://github.com/descope/virtualwebauthn) — Test harness for WebAuthn flows
- [MCP Express](https://github.com/descope/mcp-express) · [MCP Go](https://github.com/descope/mcp-go) · [Descope MCP SDKs](https://github.com/descope/descope-mcp)
- [Authentication Skills for AI Agents](https://github.com/descope/skills)

## Migration Tools

- [Auth0 → Descope](https://github.com/descope/descope-auth0-migration)
- [Amazon Cognito → Descope](https://github.com/descope/descope-cognito-migration)
- [Firebase → Descope](https://github.com/descope/descope-firebase-migration)
- [Keycloak → Descope](https://github.com/descope/descope-keycloak-migration)
- [Generic migration tool](https://github.com/descope/descope-migration)

## Common Resources

- [Portal](https://www.descope.com)
- [Documentation](https://docs.descope.com)
- [Getting Started](https://docs.descope.com/getting-started)
- [API Reference](https://docs.descope.com/api/openapi-spec)
- [Console](https://app.descope.com)
- [Sign Up](https://www.descope.com/sign-up)
- [Pricing](https://www.descope.com/pricing)
- [Status Page](https://descopestatus.com)
- [Blog](https://www.descope.com/blog)
- [Customers](https://www.descope.com/customers)
- [Learning Center](https://www.descope.com/learn)
- [Terms of Service](https://www.descope.com/terms)
- [Privacy Policy](https://www.descope.com/privacy)
- [Contact / Support](https://www.descope.com/contact)
- [LinkedIn](https://www.linkedin.com/company/descope)
- [YouTube](https://www.youtube.com/@descopeinc)
- [AuthTown Community](https://authtown.unstructured.chat)
- [GitHub Organization](https://github.com/descope)

## Maintainers

- **Kin Lane** — [@apievangelist](https://twitter.com/apievangelist) — [apievangelist.com](https://apievangelist.com)

# Above Security Plugin

Connects Claude to the [Above Security](https://above.security) MCP server for insider threat
and identity investigations — surface incidents, investigate identities, and validate findings
against telemetry directly from Claude.

## Setup

The MCP server is hosted and authenticates via OAuth — no local installation required. On first
use Claude signs you in via your Above Security account (OAuth 2.1 + PKCE). Client registration is
dynamic, so there's nothing to configure.

## Connectors

Above runs a separate deployment per region. The plugin ships one connector per region;
connect **only** the one that matches the portal you sign in to.

| Connector | Use it if you sign in at | URL | Transport | Auth |
|-----------|--------------------------|-----|-----------|------|
| `above-security` | `app.abovesec.com` (US) | `https://mcp.app.abovesec.com/mcp` | HTTP | OAuth (dynamic registration) |
| `above-security-eu` | `app.eu.abovesec.com` (EU) | `https://mcp.app.eu.abovesec.com/mcp` | HTTP | OAuth (dynamic registration) |

After installing, open the plugin's **Connectors** tab and connect your region's connector.
Leave the other one disconnected. Connecting the wrong region fails at sign-in with
"User not found", because your account lives in the other region.

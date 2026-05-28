# Documentation project instructions

These instructions apply to AI coding assistants (Claude Code, Cursor, Windsurf, etc.) working in this repository.

## About this project

- This is the developer documentation site for **LoyaltyDog**, built on [Mintlify](https://mintlify.com).
- Live at [loyaltydog.mintlify.app](https://loyaltydog.mintlify.app); custom domain `docs.loyalty.dog` planned.
- Content pages are MDX files with YAML frontmatter; configuration lives in `docs.json`.
- The API reference is auto-generated from `https://api.loyalty.dog/openapi.json` — do not hand-write endpoint pages.

## MCP servers

- Edit content and settings: `https://mcp.mintlify.com`
- Query Mintlify product knowledge: `https://www.mintlify.com/docs/mcp`

## Terminology

| Use | Don't use |
| --- | --------- |
| LoyaltyDog (one word, capital L and D) | Loyalty Dog, loyalty dog, Loyaltydog |
| program | account, tenant |
| customer | member, user (in the loyalty context) |
| merchant | business, store (when referring to the LoyaltyDog account holder) |
| wallet pass | mobile pass, Apple pass, Google pass (use the generic term unless platform-specific) |
| API token / bearer token | API key (only use "app key" for the `/v2/appkeys`-issued shape) |

## Style preferences

- Active voice, second person ("you").
- One idea per sentence — favor concise over comprehensive.
- Sentence case for headings (not Title Case).
- **Bold** for UI elements: "Click **Settings**."
- `Code formatting` for endpoints, file names, environment variables, and code references.
- Endpoint references use the form `POST /v2/customers` — include the HTTP method.

## Content boundaries

- **Don't document internal admin endpoints** beyond what's needed for self-serve partner integrations.
- **Don't hand-write per-endpoint reference pages** — the API reference is generated. Add narrative guides under `guides/` instead.
- **Don't bake secrets or real customer IDs into examples.** Use clearly fake identifiers like `prog_123`, `cust_456`, `ada@example.com`.
- **Don't link to internal-only repos or dashboards** from this public site.

## When adding pages

- Add the file under the matching directory (`mcp/`, `integrations/`, `guides/`, `resources/`).
- Add the file's path (without `.mdx`) to the appropriate group in `docs.json` under `navigation.tabs[0].groups`.
- Use frontmatter with `title` and `description`.

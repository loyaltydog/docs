# Documentation project instructions

These instructions apply to AI coding assistants (Claude Code, Cursor, Windsurf, etc.) working in this repository.

## About this project

- This is the developer documentation site for **LoyaltyDog**, built on [Mintlify](https://mintlify.com).
- Live at [docs.loyalty.dog](https://docs.loyalty.dog) (Mintlify).
- Content pages are MDX files with YAML frontmatter; configuration lives in `docs.json`.
- The API reference is generated from the **public** snapshot `openapi.public.json` (SWE-1133 deny-list). Do **not** point Mintlify at `/openapi.json` (full dashboard/admin schema). Do not hand-write endpoint pages.

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
| API token / bearer token / App Key | Do not document `POST /appkeys` as a public hashed-key issuance API (SWE-1181) |

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

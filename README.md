# LoyaltyDog Developer Documentation

Source for the LoyaltyDog developer docs, published with [Mintlify](https://mintlify.com).

- **Live site:** [loyaltydog.mintlify.app](https://loyaltydog.mintlify.app) (custom domain `docs.loyalty.dog` planned)
- **API reference source:** generated live from [`https://api.loyalty.dog/openapi.json`](https://api.loyalty.dog/openapi.json) — no manual sync required when the API ships changes
- **Repo:** [`loyaltydog/docs`](https://github.com/loyaltydog/docs)

## What's documented

| Area | Lives in |
| ---- | -------- |
| Introduction, quickstart, authentication | `index.mdx`, `quickstart.mdx`, `authentication.mdx` |
| Full REST API reference (auto-generated) | `api-reference/` tab in `docs.json` |
| MCP server (Claude, Cursor, Windsurf, Claude Code) | `mcp/` |
| Platform integrations (Shopify, Square, Clover, Eposnow, Zapier) | `integrations/` |
| Webhooks, wallet passes, reporting guides | `guides/` |
| Changelog, support, status | `resources/` |

## Local development

Install the Mintlify CLI and run a local preview:

```bash
npm install -g mint
mint dev
```

The dev server runs at [http://localhost:3000](http://localhost:3000).

## Editing content

- All content pages are MDX with YAML frontmatter (`title`, `description`).
- Navigation order lives in `docs.json` under `navigation.tabs`.
- Branding (colors, logo, favicon) is in `docs.json` under `colors` and `logo`.
- The API reference is generated automatically from the live OpenAPI spec — no MDX files to maintain for individual endpoints.

## Publishing

The Mintlify GitHub App watches this repository. Any push to `main` triggers a production deploy.

## Branch protection

`main` is the only branch and is protected:

- Only members of the `loyaltydog` GitHub organization can push.
- All changes go through a pull request reviewed by an organization member.

External contributors can open issues but cannot push directly. To propose a change, open a pull request — an organization member will review and merge.

## Custom domain

The custom domain `docs.loyalty.dog` is configured in the [Mintlify dashboard](https://dashboard.mintlify.com/) under **Settings → Domain**. DNS for `docs.loyalty.dog` is managed in the LoyaltyDog DNS zone and points (`CNAME`) at the Mintlify-provided target.

## Support

For documentation issues or suggestions, open an issue on this repo. For platform support, see [support@loyalty.dog](mailto:support@loyalty.dog).

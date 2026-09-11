# LoyaltyDog Developer Documentation

Source for the LoyaltyDog developer docs, published with [Mintlify](https://mintlify.com).

- **Live site:** [docs.loyalty.dog](https://docs.loyalty.dog)
- **API reference source:** frozen public snapshot [`openapi.public.json`](./openapi.public.json) (SWE-1133). **Not** `/openapi.json` (full dashboard/admin schema).
- **Repo:** [`loyaltydog/docs`](https://github.com/loyaltydog/docs)

## What's documented

| Area | Lives in |
| ---- | -------- |
| Introduction, quickstart, authentication | `index.mdx`, `quickstart.mdx`, `authentication.mdx` |
| Public REST API reference (Mintlify playground) | `api-reference/` tab + `openapi.public.json` |
| Downloadable OpenAPI | [`/openapi.public.json`](./openapi.public.json); page menu → Download API spec |
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

- `authentication.mdx` and `guides/errors.mdx`, `guides/idempotency.mdx`, `guides/rate-limits.mdx`, `guides/test-mode.mdx` track content owned by `loyaltydog/core_api`'s `docs/public-api/` markdown (auth, errors, idempotency, rate-limits, test-mode). **There is no automatic sync between the two repos** — when that source changes, copy the update here and open a Mintlify deploy PR (SWE-1199).
- All content pages are MDX with YAML frontmatter (`title`, `description`).
- Navigation order lives in `docs.json` under `navigation.tabs`.
- Branding (colors, logo, favicon) is in `docs.json` under `colors` and `logo`.
- The API reference is generated from `openapi.public.json`. Refresh that snapshot when public routes change (see [resources/openapi.mdx](./resources/openapi.mdx)). Do not regenerate from `/openapi.json`.

## Publishing

The Mintlify GitHub App watches this repository. Any push to `main` triggers a production deploy.

## Branch protection

`main` is the only branch and is protected:

- Only members of the `loyaltydog` GitHub organization can push.
- All changes go through a pull request reviewed by an organization member.

External contributors can open issues but cannot push directly. To propose a change, open a pull request — an organization member will review and merge.

## Custom domain

The custom domain `docs.loyalty.dog` CNAME is `cname.mintlify.builders`. The Mintlify GitHub App deploys on push to `main`.

## Support

For documentation issues or suggestions, open an issue on this repo. For platform support, see [support@loyalty.dog](mailto:support@loyalty.dog).

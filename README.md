# X1VI Product Catalogue

A static, single-page product catalogue with five code-drawn pixel-art covers.

## Deploy as a Cloudflare Worker

Create a Worker in **Workers & Pages**, connect the GitHub repository `X1Vi/product-catalogue`, and use Workers Builds with these settings:

Use these settings:

| Setting | Value |
| --- | --- |
| Production branch | `main` |
| Build command | Leave blank |
| Deploy command | `npx wrangler@latest deploy` |
| Preview command | `npx wrangler@latest preview` |
| Root directory | Leave blank (repository root) |
| Build variables and secrets | None |

The Worker configuration is in `wrangler.jsonc`. Every request runs through `src/index.js` before the matching file in `dist` is returned, so request counts, successes, errors, and invocation status are recorded as Worker metrics. Workers Logs are enabled at a 100% sampling rate for this low-traffic catalogue.

Every push to `main` triggers a production deployment. Other branches can use Worker preview builds.

### View metrics

Open **Workers & Pages → x1vi-product-catalogue**. The Worker overview shows request metrics. Open **Observability** for invocation logs and Query Builder.

## Local preview

From the repository root:

```sh
npx wrangler@latest dev
```

Wrangler prints the local preview URL.

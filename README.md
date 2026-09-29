# X1VI Product Catalogue

A static, single-page product catalogue with five generated pixel-art covers.

## Deploy on Cloudflare Pages

Connect the GitHub repository `X1Vi/product-catalogue` from **Workers & Pages → Create → Pages → Import an existing Git repository**.

Use these settings:

| Setting | Value |
| --- | --- |
| Production branch | `main` |
| Framework preset | `None` |
| Build command | `exit 0` |
| Build output directory | `dist` |
| Root directory | Leave blank (repository root) |
| Environment variables | None |

Cloudflare will publish `dist/index.html` and automatically deploy every push to `main`. Pull requests and other branches can receive preview deployments.

The `dist/_headers` file adds browser security headers when the site is served by Cloudflare Pages.

## Local preview

From the repository root:

```sh
python3 -m http.server 4173 --directory dist
```

Then open `http://localhost:4173`.

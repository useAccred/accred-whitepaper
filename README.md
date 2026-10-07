# Accred Whitepaper site

The web home of the Accred whitepaper: a readable HTML version of the full document, plus the PDF for download.

| Path | What it is |
| --- | --- |
| `index.html` | The whitepaper as a web page (table of contents, tables, figures, dark mode, print styles) |
| `Accred_Whitepaper_V1.0.pdf` | The PDF |
| `whitepaper.pdf` | A copy at a stable name that does not change with the version |
| `pdf/index.html` | Redirects `/pdf` to the PDF |
| `brand/logo.png` | Logo and favicon |
| `og.png` | Social preview image |
| `render.yaml` | Render blueprint with headers and rewrites. Only used when the service is created from a Blueprint; the live service was created with the CLI, so the short links are plain files instead |

No build step. Edit `index.html`, push to `main`, and redeploy.

## Deploy

Hosted on Render as a static site. After a push, trigger a deploy from the Render dashboard or with the CLI:

```bash
render deploys create <service id> --confirm --wait -o text
```

## Custom domain

In the Render dashboard, open the service → Settings → Custom Domains → Add, enter the domain (for example `whitepaper.accred.sh`), and create the CNAME record Render shows at the DNS provider. Render issues the TLS certificate automatically once the record resolves.

## Updating the whitepaper

1. Replace the PDF (keep the file name, or add the new version and update the links in `index.html` and `render.yaml`).
2. Update the text in `index.html` and the version and date in the hero, the footer, the meta tags and `sitemap.xml`.

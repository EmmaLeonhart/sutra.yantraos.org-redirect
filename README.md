# sutra.yantraos.org redirect

Static GitHub Pages site that redirects **sutra.yantraos.org** → <https://sutra.noldor.tech/>.

Path, query string, and hash are preserved (e.g. `sutra.yantraos.org/foo?x=1` →
`https://sutra.noldor.tech/foo?x=1`). GitHub Pages issues a free Let's Encrypt
certificate for the custom domain, so `https://sutra.yantraos.org` works without a
TLS error.

## DNS setup (to do at the registrar)
`sutra.yantraos.org` is a subdomain, so point it at GitHub Pages with a single CNAME record:

- **Type:** CNAME
- **Host/Name:** `sutra` (the subdomain of `yantraos.org`)
- **Value/Target:** `emmaleonhart.github.io`

The `CNAME` file in this repo sets the Pages custom domain to `sutra.yantraos.org`.

## GitHub Pages setup
In the repo's **Settings → Pages**, set the source to deploy from the `main`
branch (root). The custom domain will populate from the `CNAME` file. Once DNS
resolves, tick **Enforce HTTPS**.

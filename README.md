# primivant.gr

The Primivant website: one static HTML page (wordmark, tagline, email), no build step, no JavaScript, no cookies.

Everything that gets published lives in `public/`. Nothing outside it is deployed.

| Path | Purpose |
| --- | --- |
| `public/index.html` | The site. CSS is inline, the logo is inline SVG. |
| `public/404.html` | Not-found page (marked `noindex`). |
| `public/og-image.png` | 1200×630 preview shown when the link is shared. |
| `public/favicon.ico`, `favicon.svg`, `apple-touch-icon.png`, `icon-192.png`, `icon-512.png`, `site.webmanifest` | Browser and home-screen icons, from the logo kit. |
| `public/robots.txt`, `public/sitemap.xml` | For search engines. Update `<lastmod>` in the sitemap when the page changes. |
| `public/_headers` | Security headers, read by Cloudflare Pages. |
| `drafts/full-site.html` | A longer version with services, process and about sections, kept for later. Not deployed. |

The Sora font loads from Bunny Fonts (EU-hosted, no tracking), so no cookie banner is needed.

## Preview locally

```
npx serve public
```

Then open http://localhost:3000.

## Deploy

Cloudflare Pages is connected to this GitHub repository. Pushing to `main` publishes the site.

Pages settings: framework preset **None**, build command **empty**, build output directory **`public`**.

Domains: `primivant.gr` is the main address. `www.primivant.gr`, `primivant.com` and `www.primivant.com` redirect to it with a 301 (Cloudflare Redirect Rules in each zone).

## Before promoting the site

- The company's legal details (registered name, address, GEMI and VAT numbers) are left off for now. EU rules (Directive 2000/31/EC, art. 5) expect them on a business website.
- Submit `https://primivant.gr/sitemap.xml` in Google Search Console and Bing Webmaster Tools.

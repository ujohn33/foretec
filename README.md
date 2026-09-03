# foretec.be

Static site. One file, no build step.

## Files
- `index.html` — the whole site (landing page + `#/mechanics` page, hash-routed)
- `og.png` — link preview card (1200x630)
- `CNAME` — tells GitHub Pages the custom domain is `foretec.be`
- `.nojekyll` — skip Jekyll processing
- `robots.txt`, `sitemap.xml`

## Deploy
1. Create a **public** repo on GitHub, e.g. `foretec-site`.
2. Upload these files to the root of the `main` branch (drag and drop on github.com works).
3. Settings -> Pages -> Source: *Deploy from a branch*, branch `main`, folder `/ (root)`.
4. Settings -> Pages -> Custom domain: `foretec.be`. Save.
5. Add the DNS records below at GoDaddy, wait for the green check, then tick **Enforce HTTPS**.

## DNS at GoDaddy (do NOT touch MX, SPF, DKIM or autodiscover)
Delete any existing A record on `@` first (GoDaddy parking page).

    Type   Name   Value
    A      @      185.199.108.153
    A      @      185.199.109.153
    A      @      185.199.110.153
    A      @      185.199.111.153
    CNAME  www    <your-github-username>.github.io

Optional IPv6, same `@` name:

    AAAA   @      2606:50c0:8000::153
    AAAA   @      2606:50c0:8001::153
    AAAA   @      2606:50c0:8002::153
    AAAA   @      2606:50c0:8003::153

`foretec.co`: use GoDaddy domain forwarding to `https://foretec.be` (301, forward with masking OFF).

## Updating
Replace `index.html` in the repo. Live within a minute or so.

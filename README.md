# meaconing.com: deploy and indexing guide

meaconing.com is a standalone site focused on meaconing, written for readers with no prior knowledge. Its sister site gnssdenial.com covers all GNSS threats with full data. The two sites link to each other and use different text, so search engines treat them as two separate, related resources rather than duplicates.

Upload every file **and folder** in this directory to the **root** of meaconing.com, keeping the folder structure. Any static host works.

## Files

| File | Purpose |
|---|---|
| `index.html` | The site, with title, description, canonical URL, Open Graph and X/Twitter tags, and JSON-LD (WebSite, TechArticle, FAQPage, DefinedTermSet glossary, Product for Navion Terra). All text is in the HTML. |
| `what-is-meaconing/`, `meaconing-vs-spoofing/`, `history-of-meaconing/`, `detect-meaconing/`, `osnma-and-meaconing/`, `meaconing-and-drones/`, `about/` | One page per question, each with its own title, canonical URL, JSON-LD (TechArticle, FAQPage, BreadcrumbList, entity links to Wikipedia and Wikidata) and a visible "last reviewed" date. `about/` carries authorship, sourcing and the Navion Terra / Ultrakinematic disclosure. |
| `privacy/` | Privacy notice: no cookies, no analytics, fonts self-hosted. Add the controller's name and postal address under "Who is responsible" in the generated page when available. |
| `fonts/` | Self-hosted Big Shoulders Display, Atkinson Hyperlegible and JetBrains Mono (SIL Open Font License, see `fonts/NOTICE.txt`). Do not switch back to Google Fonts: it sends visitors' IP addresses to Google and conflicts with the privacy notice. |
| `<slug>.md` (for example `what-is-meaconing.md`) | Markdown copy of each guide for AI assistants, linked from the page with `rel="alternate"`. |
| `0fcfd9ccd586edc4438c78cc74876257.txt` | IndexNow key file. Keep it at the root so Bing and other IndexNow engines can verify ownership. |
| `robots.txt` | Allows all search engines and explicitly allows AI crawlers. Points to the sitemap. |
| `sitemap.xml` | Page and LLM text files with dates. |
| `llms.txt`, `llms-full.txt` | Site summary and the full page as Markdown, for AI assistants. |
| `og-image.png` | 1200×630 share image. |
| icons, `site.webmanifest` | Favicon and app icons. |

## After uploading

1. Force HTTPS and redirect `www.meaconing.com` to `meaconing.com` (301).
2. **Remove any earlier redirect** from meaconing.com to gnssdenial.com, if you set one up.
3. Add meaconing.com to **Google Search Console** and **Bing Webmaster Tools** as a separate property, submit `https://meaconing.com/sitemap.xml`, and request indexing of the home page. Do **not** use Google's "Change of address" tool between the two domains.
4. If you use Cloudflare, turn off *Security → Bots → Block AI bots*, which overrides robots.txt.
5. Validate with Google's Rich Results Test and the LinkedIn Post Inspector.

## Keeping the two sites healthy

- Keep the content different. meaconing.com goes deep on one attack for beginners; gnssdenial.com is the broad, data-heavy overview. Don't copy sections between them.
- When you update figures, change the dates in `index.html` (`dateModified`, `article:modified_time`, "Page last reviewed"), `sitemap.xml` and `llms-full.txt`. The same applies to each guide page: its `dateModified`, `article:modified_time`, visible "Last reviewed" date and the matching `.md` copy. Keep the guides consistent with the home page, and keep figures that describe GNSS interference in general labelled as such.
- Links from relevant outside sites help most. Ask Ultrakinematic to link to both domains.

## Hosting on Cloudflare (Workers static assets)

This repo deploys as-is; `wrangler.jsonc` and `.assetsignore` are already set up.

1. Cloudflare dashboard → **Workers & Pages → Create → Import a repository** → pick `ayillikci/meaconing`, production branch `main`. Build command: empty. Deploy command: `npx wrangler deploy`.
2. Worker → **Settings → Domains & Routes → Add → Custom domain**: `meaconing.com` and `www.meaconing.com`. Since the domain is already on Cloudflare, DNS records and TLS certificates are created automatically.
3. Redirect `www` to the apex: **Rules → Redirect Rules** → hostname equals `www.meaconing.com` → dynamic redirect to `concat("https://meaconing.com", http.request.uri.path)`, status 301.
4. **SSL/TLS → Edge Certificates → Always Use HTTPS: on.** Then follow the "After uploading" steps above (remove any old redirect to gnssdenial.com, turn off Block AI bots, etc.).

Every push to `main` redeploys automatically.

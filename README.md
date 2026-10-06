# meaconing.com: deploy and indexing guide

meaconing.com is a standalone site focused on meaconing, written for readers with no prior knowledge. Its sister site gnssdenial.com covers all GNSS threats with full data. The two sites link to each other and use different text, so search engines treat them as two separate, related resources rather than duplicates.

Upload every file in this folder to the **root** of meaconing.com. Any static host works.

## Files

| File | Purpose |
|---|---|
| `index.html` | The site, with title, description, canonical URL, Open Graph and X/Twitter tags, and JSON-LD (WebSite, TechArticle, FAQPage, DefinedTermSet glossary, Product for Navion Terra). All text is in the HTML. |
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
- When you update figures, change the dates in `index.html` (`dateModified`, `article:modified_time`, "Page last reviewed"), `sitemap.xml` and `llms-full.txt`.
- Links from relevant outside sites help most. Ask Ultrakinematic to link to both domains.

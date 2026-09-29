# SEO Article Writer with FAQ

Write search-optimized articles with FAQ sections — and audit existing ones.

## Skills

### seo-article-writer
Give it a focus keyword (plus optional audience, length, tone, website). It will:

1. Research the live search results (top pages, People Also Ask, related searches)
2. Build an intent-matched outline that covers content gaps
3. Write a 1,500–2,000 word article (default) following an on-page SEO checklist
4. Add a 6–8 question FAQ section written for featured snippets and voice search
5. Deliver:
   - SEO summary (meta title, meta description, slug, keywords, intent, word count)
   - Article in Markdown and HTML
   - FAQPage JSON-LD schema
   - Internal and external link suggestions
   - A 20-point pre-publish SEO scorecard

Example prompts:
- "Write an SEO article for 'best budget laptops for students'"
- "Write a 2,500-word SEO blog post with FAQ on 'how to start a podcast' for my site example.com"

### seo-article-audit
Paste an article, share a file, or give a URL. It scores the article out of 20, lists the
top 5 fixes with ready-to-paste text, identifies content gaps, and writes an FAQ section
with schema if one is missing. It can then produce an optimized rewrite.

Example prompts:
- "Audit this article for the keyword 'home workout plan'"
- "Why isn't https://example.com/blog/post ranking? Check its SEO"

## Notes
- Uses web search for research; no extra connectors are required.
- Statistics are always sourced; the plugin never invents data or URLs.
- FAQ schema is valid structured data, but Google currently shows FAQ rich results mainly
  for authoritative government and health sites, so a rich result isn't guaranteed.

## Install

In Claude Code:

```
/plugin marketplace add MrTalhaMTS/seo-article-writer-faq
/plugin install seo-article-writer-faq@mrtalhamts-plugins
```

In Cowork: download this repo as a zip, rename it to `.plugin`, and open it in the Claude desktop app.

## License

MIT

---
name: seo-article-audit
description: >
  This skill should be used when the user asks to "audit my article", "check the SEO of this
  post", "score this blog post", "optimize this existing article", "why isn't my page
  ranking", "improve this content for SEO", or shares an existing article (pasted text,
  file, or URL) and wants an SEO review with fixes, including adding or improving an FAQ
  section.
metadata:
  version: "0.1.0"
---

# SEO Article Audit

Score an existing article against the on-page SEO checklist and deliver concrete, ready-to-
paste fixes. Use the rules in
`${CLAUDE_PLUGIN_ROOT}/skills/seo-article-writer/references/seo-checklist.md` and
`${CLAUDE_PLUGIN_ROOT}/skills/seo-article-writer/references/faq-guidelines.md`.

## Step 1 — Get the article and focus keyword

- Accept pasted text, an attached/connected file (.md, .html, .docx, .txt), or a URL
  (fetch it with WebFetch; if fetching fails, ask the user to paste the text).
- Identify the focus keyword. If the user didn't give one, infer it from the H1, title, and
  slug, state the inference in one line, and continue.

## Step 2 — Research the SERP

Run WebSearch for the focus keyword and skim 3–5 top results to learn search intent,
typical length, shared headings, People Also Ask questions, and semantic terms. Compare
the article against them.

## Step 3 — Measure

Compute, don't estimate, wherever possible (use a short script for counts):

- Word count, keyword count and density, keyword in first 100 words
- Meta title and description length (if present)
- Heading structure (H1 count, H2/H3 list, keyword in subheadings)
- Average sentence and paragraph length
- Number of internal/external links, images and alt text
- Presence and quality of FAQ section and FAQPage schema

## Step 4 — Report

Deliver in this order:

1. **Score** — X/20 using the scorecard in `seo-checklist.md`, with a one-line verdict.
2. **Top 5 priority fixes** — ranked by expected impact, each with the exact replacement
   text (new title, rewritten intro, new H2, etc.).
3. **Full scorecard** — all 20 items with ✅ / ⚠️ and a one-line fix.
4. **Content gaps** — sub-topics or questions top-ranking pages cover that this article
   misses.
5. **FAQ upgrade** — if missing or weak, write a complete 6–8 question FAQ section plus
   matching FAQPage JSON-LD, following `faq-guidelines.md`.
6. **New meta title and description** — with character counts.

## Step 5 — Optional rewrite

Offer, in one line, to produce a fully optimized rewrite. If the user accepts, hand off to
the seo-article-writer workflow using the audited article as source material, preserving
the author's facts, examples, and voice. When the user gave a file from a connected folder,
save the revised version as a new file beside the original (e.g. `article-optimized.md`)
rather than overwriting it.

## Rules

- Be specific: every issue gets a concrete fix, not general advice.
- Never invent statistics or sources in suggested fixes.
- Keep the author's voice and brand terminology.

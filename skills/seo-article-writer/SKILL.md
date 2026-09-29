---
name: seo-article-writer
description: >
  This skill should be used when the user asks to "write an SEO article", "write a blog post
  for the keyword", "create SEO optimized content", "write an article with FAQ", "write a
  fully SEO optimized article", "rank for [keyword]", or gives a focus keyword or topic and
  wants a search-optimized article. Researches the live SERP first, then produces a complete
  article with FAQ section, meta title and description, FAQPage JSON-LD schema, and internal
  and external link suggestions, delivered as Markdown and HTML.
metadata:
  version: "0.1.0"
---

# SEO Article Writer (with FAQ)

Produce a complete, publish-ready, search-optimized article built around one focus keyword,
always ending with an FAQ section. Follow the five steps below in order.

## Step 1 — Collect the brief

Extract from the user's message. Ask (with AskUserQuestion, one round only) only for what is
missing and cannot be reasonably defaulted:

| Input | Default if not given |
|---|---|
| Focus keyword | **Required** — ask if missing |
| Target audience | Infer from keyword intent |
| Word count | 1,500–2,000 words |
| Tone | Clear, expert, conversational |
| Country / language | English, global (use the user's spelling variant if obvious) |
| Brand / website name & URL | None — use placeholder links for internal links |
| Secondary keywords | Derive from research |
| Number of FAQs | 6–8 |

If the user says "just write it", proceed with defaults and state them in one line.

## Step 2 — Research the live SERP

Use WebSearch (and WebFetch on 3–5 top results) before writing. Capture:

1. **Search intent** — informational, commercial, transactional, or navigational. Match the
   format that ranks (guide, listicle, comparison, how-to, review).
2. **Competitor structure** — H2/H3 headings the top pages share; note gaps none cover well.
3. **Typical length** of ranking pages — aim to match or modestly exceed, never pad.
4. **People Also Ask / related searches** — primary source for FAQ questions.
5. **Semantic / LSI terms** and entities repeatedly used by top pages.
6. **Fresh facts and statistics** with their sources (for citations and external links).

If search is unavailable or returns nothing useful, say so in one line and continue from
knowledge, flagging any statistic that could not be verified.

Never copy competitor sentences. Use research to shape structure and coverage only.

## Step 3 — Build the outline

- One H1 containing the focus keyword (ideally near the start).
- 5–10 H2s covering the intent fully, including the content gap found in research.
- H3s where a section needs sub-steps or sub-points.
- Put the focus keyword or a close variant in at least 2 H2s — naturally.
- Final sections: **Conclusion** (with a clear call to action), then **Frequently Asked
  Questions**.

Do not stop to show the outline unless the user asked to review it first.

## Step 4 — Write the article

Apply every rule in `references/seo-checklist.md`. The essentials:

- **Intro (100–150 words):** focus keyword in the first 100 words; hook, the reader's
  problem, and what they'll get. Add a 40–60 word direct answer paragraph near the top when
  the query is a question (featured-snippet target).
- **Keyword use:** ~0.8–1.5% density, spread naturally; use synonyms and semantic terms.
  Never keyword-stuff.
- **Readability:** paragraphs of 2–4 sentences, sentences mostly under 20 words, active
  voice, transition words, bullet lists and at least one table where useful. Aim for
  Flesch reading ease 60+.
- **E-E-A-T:** concrete examples, specific numbers with sources, practical steps, and
  first-hand style insight. No vague filler, no fabricated statistics or quotes.
- **Images:** suggest 2–4 image placements with descriptive, keyword-aware alt text.
- **Links:** mark 3–5 internal link opportunities and 2–4 authoritative external links
  (see checklist for format).

### FAQ section

Follow `references/faq-guidelines.md`. In short: 6–8 questions drawn from People Also Ask
and real search phrasing, each as an H3 phrased exactly like a query, answered in 40–80
words that open with the direct answer. No FAQ may repeat a question already answered by an
H2 heading.

## Step 5 — Package the deliverable

Produce, in this order:

1. **SEO summary block** (see `references/output-template.md`): focus keyword, secondary
   keywords, search intent, meta title (50–60 characters), meta description (140–155
   characters, includes keyword and a call to action), URL slug, word count, estimated
   reading time.
2. **Article in Markdown.**
3. **Article in HTML** — semantic tags only (`h1`–`h3`, `p`, `ul`, `ol`, `table`,
   `strong`, `a`), no inline styles, with the FAQPage JSON-LD `<script>` at the end.
4. **Link suggestions table** — anchor text, target (internal page idea or external URL),
   and the section where it goes.
5. **Pre-publish checklist** — the scored checklist from `references/seo-checklist.md`
   with each item ticked or flagged.

Save the Markdown and HTML as files named after the URL slug (e.g. `best-running-shoes.md`
and `best-running-shoes.html`) and deliver them to the user. If a folder on the user's
computer is connected, write the files there. Keep the chat reply short: the meta title,
meta description, word count, and one line pointing to the files.

## Quality bar

Before delivering, verify:

- Character counts of meta title and description are within limits (count them, don't guess).
- Word count is within ±10% of target.
- The JSON-LD is valid JSON and the FAQ answers in the schema match the visible answers
  word for word.
- Every statistic has a source link or is clearly marked as an estimate.

## Additional resources

- `references/seo-checklist.md` — full on-page SEO rules and the pre-publish scorecard
- `references/faq-guidelines.md` — how to choose, phrase, and answer FAQs, plus schema rules
- `references/output-template.md` — exact output layout, HTML skeleton, and JSON-LD template

# Output Template

## 1. SEO summary block

```markdown
| Field | Value |
|---|---|
| Focus keyword | best running shoes for flat feet |
| Secondary keywords | stability running shoes, overpronation shoes, arch support shoes |
| Search intent | Commercial investigation |
| Meta title (55 chars) | Best Running Shoes for Flat Feet (2026): 9 Expert Picks |
| Meta description (152 chars) | Find the best running shoes for flat feet in 2026. We compare stability, cushioning and price across 9 top picks so you can run pain-free. See the list. |
| URL slug | /best-running-shoes-flat-feet |
| Word count | 1,820 |
| Reading time | 8 min |
```

Always show the real character count in brackets after "Meta title" and "Meta description".
Reading time = word count ÷ 230, rounded up.

## 2. Markdown article

```markdown
# [H1 with focus keyword]

[Intro 100–150 words, keyword in first 100 words]

[Optional 40–60 word direct-answer / snippet paragraph]

## [H2]
...

## Conclusion
[Summary + clear call to action]

## Frequently Asked Questions
### [Question?]
[Answer]
```

## 3. HTML article skeleton

```html
<article>
  <h1>[H1]</h1>
  <p>[Intro]</p>

  <h2>[H2]</h2>
  <p>...</p>

  <h2>Conclusion</h2>
  <p>...</p>

  <section class="faq">
    <h2>Frequently Asked Questions</h2>
    <h3>[Question 1?]</h3>
    <p>[Answer 1]</p>
    <h3>[Question 2?]</h3>
    <p>[Answer 2]</p>
  </section>
</article>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "[Question 1?]",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "[Answer 1 — identical to visible text]"
      }
    },
    {
      "@type": "Question",
      "name": "[Question 2?]",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "[Answer 2]"
      }
    }
  ]
}
</script>
```

Include the meta tags as a comment block above the article so the user can paste them into
their CMS:

```html
<!--
<title>[Meta title]</title>
<meta name="description" content="[Meta description]">
Slug: [url-slug]
-->
```

When writing the HTML, validate the JSON-LD by parsing it (e.g. with a short Python
`json.loads` check) before delivering.

## 4. Link suggestions table

```markdown
| # | Type | Anchor text | Target | Place in section |
|---|---|---|---|---|
| 1 | Internal | how to choose running shoes | /how-to-choose-running-shoes (page idea) | "What to look for" |
| 2 | External | American Podiatric Medical Association | https://www.apma.org/ | "Why arch support matters" |
```

## 5. Pre-publish scorecard

List the 20 items from `seo-checklist.md` with ✅ or ⚠️ and a one-line fix for each ⚠️,
followed by the total score (X/20).

# FAQ Guidelines

## Choosing questions

Pick 6–8 questions (or the number the user asked for), in this priority order:

1. **People Also Ask** questions found during SERP research.
2. **Related searches** and autocomplete-style phrasing ("is", "can", "how much", "how long",
   "what is the difference between", "best … for …").
3. **Objections and follow-ups** a buyer or learner would have after reading the article
   (cost, time, safety, alternatives, common mistakes).

Rules:

- Each question must be distinct — no two answers should overlap by more than a sentence.
- Do not repeat a question the article already answers under its own H2.
- Include the focus keyword or a variant in 2–3 of the questions, not all of them.
- Mix short-tail and long-tail / voice-search style questions.
- Order from most searched / most basic to most specific.

## Phrasing questions

- Write each as an H3, phrased exactly as a person types or speaks it, ending with "?".
- Keep questions under 12 words where possible.
- Good: "How long does it take to learn SEO?"
- Bad: "Learning Time Considerations for SEO"

## Writing answers

- 40–80 words each (2–4 sentences).
- The **first sentence is the direct answer** (yes/no, a number, a definition), so it can be
  lifted as a snippet or voice answer.
- Follow with one sentence of context or nuance, and optionally a tip.
- Plain text only inside answers that go into schema — links are allowed in the visible
  HTML, but keep the schema text identical to the visible text apart from markup.
- No sales language, no "contact us" answers, no fabricated figures.

## FAQPage schema rules

- One `FAQPage` block per page containing every visible FAQ.
- `name` = the exact question text; `acceptedAnswer.text` = the exact visible answer.
- Do not mark up questions that are not visible on the page.
- Validate that the JSON parses (no trailing commas, escaped quotes).
- Note for the user when relevant: Google currently shows FAQ rich results mainly for
  well-known authoritative sites (e.g. government and health). The schema is still valid,
  helps search and AI engines understand the page, and is used by other search engines —
  but a rich result in Google is not guaranteed.

## FAQ section template (Markdown)

```markdown
## Frequently Asked Questions

### What is [focus keyword]?
[Direct one-sentence answer.] [Context sentence.] [Optional tip.]

### How much does [focus keyword] cost?
[Direct answer with a range and source year.] [What affects the price.]
```

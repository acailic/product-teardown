# Teardown: <Business name>

- **Date analyzed:** YYYY-MM-DD
- **Category:** B2B / B2C · <SaaS · API · one-person web app · …>
- **Model:** <subscription · usage-based · ads · licensing · one-off>
- **Prices as seen (YYYY-MM-DD):** <price points snapshot, with billing basis>
- **Revenue evidence:** <verified / estimated — with links>

## 0. The essence (ELI9)

<3–6 sentences, no jargon: what it sells, who gives it money, and why they
keep doing that — as if explaining to a smart nine-year-old.>

## 1. What it is, and for whom

<One paragraph: what the product does, in its own category terms, and who
the primary user is.>

## 2. How it earns

<Model and price points from the public pricing page or founder statements.
Name the revenue units — seats, imports, impressions, licenses. Quote the
revenue evidence and label it verified or estimated.>

## 3. Who the customers are

<Concrete segments with evidence: vendor claims (marked as such), pricing
structure, review sites, forums, HN/Reddit threads.>

## 4. Why they use it

<Job-to-be-done: what the customer hires the product for. The realistic
alternatives — including "do it manually" — and what the product wins on.>

## 5. What I would build better

<1–3 concrete changes. For each: what to build, why the gap exists (point to
the evidence above), and why it is worth money — not a side feature but the
top of the offer.>

## Sources

<Optional consolidated index — one line per source: link — what it
evidences. Inline links already satisfy the evidence rule; keep this
section only when it adds a useful map of the sources.>

---

## Structure — what is fixed, what is flexible

*(Guidance for authors, not part of a teardown — delete this block after
copying the skeleton above. Full method:
[`docs/METHOD.md`](../docs/METHOD.md).)*

**Fixed** — this is what makes any two teardowns comparable question by
question:

1. **Six sections, in this order:** the essence (ELI9) first, then the five
   questions of `docs/METHOD.md` — what it is and for whom, how it earns,
   who the customers are, why they use it, what to build better.
2. **The analysis date stated up front** — in the title, a dateline, or the
   metadata block above — before the essence begins.
3. **Every non-trivial claim carries its link inline** (METHOD evidence
   rules), and prices are snapshots recorded as seen on the analysis date.

**Flexible** — presentation, not structure:

1. **H1 wording:** `# Teardown: <Name>` or `# <Name> — <descriptor>
   (2026-11-05)`. The analysis date may live in the title itself.
2. **Metadata header shape:** the bullet fields above, or a one-line
   dateline (`*Teardown date: 2026-11-05 · …*`). Extra fields — Founded,
   HQ, Ownership — are welcome when known.
3. **Section titles:** the numbered titles above, or unnumbered descriptive
   titles naming the same question (`## How it earns money (model, prices,
   revenue unit)`, `## Why they use it instead of alternatives`).
   Numbering is optional; the order is not.
4. **Sources:** links inline throughout are the norm. The trailing
   `## Sources` list is an optional index, not a requirement; a closing
   note that all sources are inline is enough.

Both the numbered form above and the unnumbered descriptive form appear in
`teardowns/` — both are this series' template in practice.

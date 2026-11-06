# Method — how each teardown dissects a small business

One small business per day, torn apart in public until we understand how it
earns, who pays, why they stay, and where a better product could take its
place. This page defines the fixed structure every analysis follows, so any
two teardowns can be compared question by question.

## The five questions

Every teardown answers, in this order:

1. **What the product is, and for whom** — one paragraph: category, form
   (SaaS, API, one-person web app, marketplace), and the primary user.
2. **How it earns** — business model (subscription, usage, ads, licensing,
   one-off sales), the actual price points from public pricing pages, the
   revenue units (imports, seats, impressions, licenses), and any visible
   revenue evidence (founder statements, filings, marketplace listings).
   Label clearly what is *verified* versus *estimated*.
3. **Who the customers are** — concrete segments with evidence from public
   sources: the vendor's own positioning and claims (marked as vendor
   claims), pricing-page structure, review sites, forums, HN/Reddit threads,
   integration directories. Segments are hypotheses anchored in evidence,
   not demographics invented for the exercise.
4. **Why they use it** — the job-to-be-done: what the customer is trying to
   accomplish when they hire this product, and what the realistic
   alternatives are (doing nothing, doing it manually, a different tool).
   The alternatives define the real competition.
5. **What I would build better** — 1–3 concrete changes to the offer, each
   with an argument grounded in the evidence above: why the gap exists, why
   filling it is worth money, and why it would be the top of the offer
   rather than a side feature.

## The essence, explained like you're nine

Every teardown opens with **The essence (ELI9)**: the whole business
explained in plain, jargon-free language a smart nine-year-old would
understand. Three to six sentences answering, in kid terms: what does it
sell, who gives it money, and why do they keep doing that? One analogy is
allowed; buzzwords are not. If the ELI9 paragraph cannot be written, the
analysis does not yet understand the business — go back to the sources.
The rest of the teardown is the proof behind the paragraph.

## Evidence rules

- **Public sources only.** No scraping behind login walls, no private data,
  no accounts. If a claim cannot be sourced publicly, it is either dropped
  or explicitly marked as an estimate.
- **Every non-trivial claim carries a link** — pricing pages, docs, founder
  statements, press, review threads, GitHub repos.
- **Separate vendor claims from third-party evidence.** A homepage saying
  "trusted by 1,500+ devs" is a vendor claim; a founder's HN comment with a
  revenue figure is a primary source; a reviewer's complaint is a pain
  signal.
- **Prices are snapshots.** Pricing pages change; each teardown records the
  prices as seen on its analysis date, stated in the header or next to the
  quoted price.
- **Respect licensing.** Teardown content is CC-BY-4.0; quotes stay short
  and attributed.

## Choosing subjects

- Small enough that one person can plausibly understand the whole business:
  indie projects, bootstrapped SaaS, micro-products, one-person companies —
  occasionally larger ones that started small, when the early story is the
  lesson.
- Prefer businesses with verifiable public evidence: published pricing,
  active docs/changelogs, founder interviews, review presence.
- Mix B2B and B2C, and mix revenue models (subscriptions, usage-based, ads,
  licensing) so the comparison set teaches something new each day.

## Format

- Each teardown lives at `teardowns/YYYY-MM-DD-<slug>.md`, where the date is
  the analysis date. One business per file.
- 400–1000 words, English (the repo is public and the audience is global). Essence-depth analyses may use the full band; future teardowns target ≤1000.
- Opens with **The essence (ELI9)** — required, placed immediately after the
  metadata header defined in `teardowns/template.md`.
- Starts from `teardowns/template.md`.
- `teardowns/examples/` holds sample teardowns written to validate the
  method itself; they follow every rule on this page.
- The README index lists every teardown with a one-line takeaway.

## License

Content in this repository is licensed [CC-BY-4.0](../LICENSE) — reuse with
attribution. All cited sources remain the property of their owners.

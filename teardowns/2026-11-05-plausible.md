# Plausible Analytics — product teardown

*Analyzed 2026-11-05. All facts from public sources, linked inline. License of this document: CC-BY-4.0.*

## The essence (for a 9-year-old)

Plausible is a counting machine for websites. When people visit your site, it counts how many came and which pages they saw — but it does not try to find out who they are or follow them around the internet, the way Google's free tool does. Because it behaves this way, website owners don't need to show the annoying "accept cookies?" pop-up. Owners pay a small monthly fee for this honest counting, and today about 22,000 of them do — enough money to support a team of just 11 people who built the whole thing themselves without rich investors. ([plausible.io](https://plausible.io/))

## What the product is and who it's for

Plausible is simple, privacy-first web analytics: a one-page dashboard (visitors, sources, pages, goals) fed by a script 54× smaller than Google Analytics' (~135 KB less JavaScript per pageview). It is open source (AGPLv3) — the [GitHub repo](https://github.com/plausible/analytics) has ~29,800 stars and is written in Elixir. The company pitches itself at seven segments: ecommerce, SaaS, agencies, creators & publishers, public sector, white-label analytics, and enterprise ([homepage nav](https://plausible.io/)). Everything is hosted in the EU on European-owned infrastructure ([plausible.io](https://plausible.io/)).

## How it earns

**Model:** subscription SaaS. The managed, EU-hosted cloud is the *only* revenue source; the free, self-hosted "Community Edition" (CE) is a distribution and trust engine, not a product line ("Our only source of funding is the managed cloud service" — [self-hosting page](https://plausible.io/self-hosted-web-analytics)). The company is bootstrapped, profitable, 11 people, running since 2018, no outside investors ([homepage](https://plausible.io/)).

**Revenue unit:** monthly pageviews, bundled with site count and team seats. Three self-serve tiers scale with traffic ([pricing section](https://plausible.io/#pricing)): Starter $9/mo (10k pageviews, 1 site), Growth $14/mo (3 sites, 3 members), Business $19/mo (10 sites, 10 members) — rising with traffic to $169/$254/$339 per month at the 10M+ pageview tier. Enterprise is custom-priced. Yearly billing gives two months free; 30-day trial, no credit card.

**Feature gating as an upsell:** CE is free but funnels, user journeys, ecommerce revenue goals, SSO and the Sites API are cloud-only — "to help support the project's long-term sustainability" ([CE vs cloud comparison](https://plausible.io/self-hosted-web-analytics)).

**Revenue:** unknown (private company). Best public signals: 22,000 paying subscribers and 332B events stored ([homepage](https://plausible.io/), accessed 2026-11-05), plus the founder-reported **$1.2M ARR in early 2023** ([public writeup, 210 points on Hacker News](https://news.ycombinator.com/item?id=35121435)). At current tier prices that subscriber count implies a rough order of magnitude of single-digit millions ARR today — an estimate, not a disclosed figure.

## Who the customers are

- **Recognizable brands:** Stripe, Mozilla, MongoDB, Harvard University and Sentry are named as customers ([homepage](https://plausible.io/)).
- **Developer/indie founders:** Hugging Face's CEO calls them "massive users"; 37signals' DHH is "a very happy customer… at Basecamp" ([testimonials](https://plausible.io/)).
- **Publishers/creators:** Ghost's CEO "switched over everything from GA"; SEO consultant Cyrus Shepard recommends it for client work ([homepage](https://plausible.io/)).
- **Self-hosters:** a long-running HN thread on the product is full of self-hosted users ("I'm a very happy self-hosted Plausible user for years") ([HN discussion](https://news.ycombinator.com/item?id=40909006)).
- **Agencies** get a dedicated white-label offering ([homepage](https://plausible.io/)).

## Why they use it instead of alternatives

The job-to-be-done: "know my traffic and conversions without a cookie banner, GDPR risk, or a GA4 training course." Shepard's quote captures it: "SOOO easy to use (for clients too)… a good solution for ~70% of websites struggling with GA4" ([homepage](https://plausible.io/)). Concrete alternatives and why customers pass on them:

- **Google Analytics** — free but, in Plausible's framing, "frustrating to use… and privacy-invasive"; the site dedicates whole comparison pages to "vs Google Analytics" and "Migrate from GA4" because that migration is the core growth motion ([homepage](https://plausible.io/)).
- **Matomo, Fathom, Simple Analytics, Umami, GoatCounter** — the direct privacy-focused rivals, all named organically by commenters in [this HN thread](https://news.ycombinator.com/item?id=40909006). Customers choose Plausible over them for the combination of polish, open source, EU hosting and scale.

## What I'd build better

1. **Lighter self-hosting.** CE requires running PostgreSQL *and* ClickHouse; an HN user calls it "extremely heavy for a simple analytics solution" ([HN](https://news.ycombinator.com/item?id=40909006)). A single-binary or one-click VPS image would widen the free funnel that feeds cloud conversions — self-hosters are the credibility engine of an open-source analytics business.
2. **Journey/funnel depth at lower tiers.** The same thread notes Plausible "lacks much of the information from Matomo" (path analysis), and funnels/journeys are cloud-only. GA4 refugees — the core growth segment — are migrating precisely for simpler behavioral insight; shipping a lightweight journeys view in Starter would defend that wedge.
3. **Close the session-hash transparency gap.** Critics document that Plausible stores `hash(siteID + IP + User-Agent)` for sessions while marketing "no personal data" ([review thread](https://news.ycombinator.com/item?id=24868012)). For a company whose moat *is* trust, either engineer session tracking away or make the trade-off explicit on the pricing page itself.

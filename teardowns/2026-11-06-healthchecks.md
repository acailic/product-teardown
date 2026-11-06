# Teardown: Healthchecks.io — a one-person watchdog for cron jobs

- **Date analyzed:** 2026-11-06
- **Category:** B2B · SaaS (developer infrastructure, open source)
- **Model:** freemium subscription (per-account tiers)
- **Prices as seen (2026-11-06):** $0 Hobbyist (20 jobs) · $5/mo Supporter (patronage) · $20/mo Business (100 jobs, SMS/phone credits) · $80/mo Business Plus (1,000 jobs) · annual −20% ([pricing](https://healthchecks.io/pricing/))
- **Revenue evidence:** verified — vendor-published live stats: 1,420 paying accounts, $29,300 MRR ([About](https://healthchecks.io/about/), 2026-11-01)

## 0. The essence (ELI9)

Computers have chores: every night they back things up and send emails. Sometimes a chore quietly doesn't happen — and nobody notices for weeks. Healthchecks.io is a roll-call teacher: after each chore, the computer must phone her and say "done!" If the call doesn't come, she immediately emails, texts or calls you. About 200,000 people use it free and roughly 1,400 pay — mostly $20 a month — $29,300 monthly for exactly one man in Latvia who wrote the program himself and gives the code away for free.

## 1. What it is, and for whom

Healthchecks.io is a dead man's switch for scheduled work: each cron job, backup script or daemon pings a URL after finishing; a missed ping trips alerts via email, SMS, phone, chat, webhooks and on-call integrations ([homepage](https://healthchecks.io/)). The primary user: the developer or sysadmin who owns scheduled tasks and needs to hear about *silence*, not just errors. The code is open source (BSD, ~10.5k stars — [GitHub](https://github.com/healthchecks/healthchecks)); self-hosting is free, the managed service is the paid product — a one-person company, SIA Monkey See Monkey Do, run by Pēteris Caune since July 2015 ([About](https://healthchecks.io/about/)).

## 2. How it earns

**Freemium subscription. Revenue unit: monitored jobs ("checks"), plus log retention and SMS/phone credits** ([pricing](https://healthchecks.io/pricing/)): Hobbyist $0 (20 jobs, 100 log entries/job); Supporter $5/mo — identical limits, patronage ("But what's the point?"); Business $20/mo (100 jobs, 1,000 entries, SMS + call credits); Business Plus $80/mo (1,000 jobs, more credits); annual −20%. Above 1,000 jobs, custom plans ("2000 checks for $160/mo" — [founder on HN](https://news.ycombinator.com/item?id=41104293)); open-source and nonprofits get Business free.

**Revenue is verified, not estimated** — rare at this size. The About page (2026-11-01) publishes 1,420 paying accounts, $29,300 MRR and 134M pings/day, and calls the business "profitable and sustainable" (vendor claim — [About](https://healthchecks.io/about/)). July 2024: 652 customers, $14,043 MRR ([9-years post](https://blog.healthchecks.io/2024/07/running-one-man-saas-9-years-in/)) — MRR doubled in 27 months. Costs stay tiny: nine Hetzner servers, €484/month in 2022 ([2022 post](https://blog.healthchecks.io/2022/02/healthchecks-io-hosting-setup-2022-edition/)).

## 3. Who the customers are

- **Solo developers and homelabbers** dominate: 199,000 free accounts vs 1,420 paying ([About](https://healthchecks.io/about/)). Third-party: "saved me on more occasions than I care to remember" ([HN](https://news.ycombinator.com/item?id=41104563)); Capterra shows **5.0 from 106 reviews** ([Aug 2026 snapshot](http://web.archive.org/web/20260824110108/https://www.capterra.com/p/249957/Healthchecksio/reviews/)).
- **Small businesses with scheduled jobs** — the 100–1,000-check tiers (vendor testimonials, [pricing](https://healthchecks.io/pricing/)); average paying account ≈ $20.6/mo (derived from stats).
- **Open-source projects and nonprofits** on free Business plans ([About](https://healthchecks.io/about/)).
- Growth per the founder (vendor claim): search traffic, word of mouth, "regular mentions in Reddit /r/selfhosted" ([HN](https://news.ycombinator.com/item?id=41104293)).

## 4. Why they use it

The job-to-be-done: **sleep through the night knowing a silent failure will still be heard** — cron's failure mode is an unread email or nothing at all ([homepage](https://healthchecks.io/)). Alternatives as seen 2026-11-06:

- **Doing nothing** — free, until backups turn out dead for a month.
- **Cronitor** — $2/mo per monitor + $5/mo per user (20 monitors ≈ $55/mo) ([pricing](https://cronitor.io/pricing)) vs 100 jobs for $20; the founder built this because incumbents were "overpriced" ([blog](https://blog.healthchecks.io/2024/07/running-one-man-saas-9-years-in/)).
- **Dead Man's Snitch** — $19/mo for 100 snitches, one free ([plans](https://www.deadmanssnitch.com/plans)); Healthchecks gives 20 checks free.
- **Self-hosting the same code** — free, but your watchdog lives on the dog it watches; serious users pay to escape that loop.

## 5. What I would build better

1. **Team workspaces as a real tier.** Accounts are single-owner while Business buyers are teams (custom-plan demand proves it — [HN](https://news.ycombinator.com/item?id=41104293)). Seats, roles and audit logs monetize what Cronitor charges $5/user/mo for — the next rung up, without enterprise procurement.
2. **Failure signatures — alert on *why*, not just *that*.** The service already stores the first 100 KB of every ping body — 14M objects, ~30 uploads/sec ([blog](https://blog.healthchecks.io/2026/04/healthchecks-io-now-uses-self-hosted-object-storage/)). Clustering recurring error signatures turns stored bytes into diagnosis — top of the offer for anyone paged at 3 AM.
3. **A continuity guarantee.** One operator, manual failover, "multi-hour or even multi-day outages are possible" ([About](https://healthchecks.io/about/)); HN's standing critique: "bus factor is 1" ([HN](https://news.ycombinator.com/item?id=31490068)). A published succession/escrow plan and automated failover convert earned trust into larger accounts.

## Sources

- [Pricing](https://healthchecks.io/pricing/) · [About](https://healthchecks.io/about/) · [homepage](https://healthchecks.io/) · [GitHub](https://github.com/healthchecks/healthchecks) — vendor; prices 2026-11-06, stats 2026-11-01
- [9-years post](https://blog.healthchecks.io/2024/07/running-one-man-saas-9-years-in/) · [2022 hosting](https://blog.healthchecks.io/2022/02/healthchecks-io-hosting-setup-2022-edition/) · [2026 storage](https://blog.healthchecks.io/2026/04/healthchecks-io-now-uses-self-hosted-object-storage/) — revenue history, costs, scale
- [HN: 9 Years In](https://news.ycombinator.com/item?id=41104293) · [user praise](https://news.ycombinator.com/item?id=41104563) · [bus-factor critique](https://news.ycombinator.com/item?id=31490068) — HN evidence
- [Capterra via Wayback](http://web.archive.org/web/20260824110108/https://www.capterra.com/p/249957/Healthchecksio/reviews/) — reviews; [Dead Man's Snitch](https://www.deadmanssnitch.com/plans) · [Cronitor](https://cronitor.io/pricing) — competitor prices

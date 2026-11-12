# Nomad List (now Nomads.com) — Product Teardown

*Date: 2026-11-05 · All sources are free and public; accessed 2026-11-05.*

**Prices as seen (2026-11-05):** Lifetime Membership $19.99 one-time (a $1 price-test variant also visible) · free tier with limited access · paid API/data plans and sponsorships exist, prices not published ([join page](https://nomads.com/?join=nomads))

## The essence (for a 9-year-old)

Some people can work from their laptop in any city in the world. Nomad List is a website that gives every city a score for how good it is for them — how much it costs, how fast the internet is, how warm and safe it is. It is also a big club of about 49,000 remote workers who find friends, meetups and even girlfriends or boyfriends in whatever city they land in. Joining the club is free, but the full pass costs $19.99 once, and the site also sells its city data to programmers and shows ads. One man, Pieter Levels, built it by himself and it made money from its very first day.

## What the product is, and for whom

Launched in 2014 as a public Google Spreadsheet, Nomad List grew into a ranking engine covering 1,377 cities scored on cost of living, internet speed, weather, safety and visas, plus a community layer: members' trips and locations, meetups, a friend finder, a dating app, and chat on Telegram ([FAQ](https://nomads.com/faq), [API docs](https://nomads.com/api/v3), [Indie Hackers interview](https://www.indiehackers.com/post/growing-a-community-for-digital-nomads-to-33-000-mo-7LcQB09oK9RHH3zvQb1L)). The audience started as "digital nomads" and has widened to remote workers generally, per the [FAQ](https://nomads.com/faq). Levels still runs it solo as a vanilla PHP app on a single Linux server ([HN](https://news.ycombinator.com/item?id=48540883)).

## How it earns

- **One-time memberships.** A free tier gives limited access; the join modal sells a "Lifetime Membership" at **$19.99 one-time** ("Billed once. Then never again"), with a $1 variant also visible — classic founder price-testing ([join page](https://nomads.com/?join=nomads)). The FAQ states the paid membership "offers a way to fund the main site's development" ([FAQ](https://nomads.com/faq)). Revenue unit: one membership payment.
- **API / data licensing.** The public API is free but limited — 60 requests/hour and 200/day per IP, curated fields only, no bulk export ([API](https://nomads.com/api/v3)) — and paid plans with all cities and a commercial license exist for apps and AI agents.
- **Ads and sponsorships.** The site runs a SafetyWing insurance affiliate ad ("from $2/day") and sells sponsorship: "Get your product in front of 8.4 million digital nomads a year" (self-reported reach) ([example page](https://nomads.com/search)).
- **Revenue: honestly, unknown.** No public books exist. Best public signals: the founder reported **$33,000/mo in July 2016** ([Indie Hackers interview title](https://www.indiehackers.com/post/growing-a-community-for-digital-nomads-to-33-000-mo-7LcQB09oK9RHH3zvQb1L)); a 2022 HN commenter estimated "~$2.7M a year, largely from running Nomad List" across his businesses — a third-party guess ([HN](https://news.ycombinator.com/item?id=32266695)); the live counter shows 49,252 members ([join page](https://nomads.com/?join=nomads)). Wired, quoted on the site's press section, called it "profitable on the first day" ([press quotes](https://nomads.com/faq)).

## Who the customers are

- **Destination deciders:** remote workers picking their next base. A paying HN user: "I look around for this all the time trying to decide what the next best place to live is… I have the paid version" ([HN](https://news.ycombinator.com/item?id=30883456)).
- **Loneliness solvers:** testimonials on the join page — "You're going to be lonely sometimes… One way I combat this is by being a part of Nomads.com"; one member met her boyfriend through a site meetup ([join page](https://nomads.com/?join=nomads)).
- **Developers and AI builders** licensing the data via API/MCP ([API](https://nomads.com/api/v3)).
- **B2B advertisers** (e.g. SafetyWing) buying reach into this niche; media and even the EU's Draghi report cited its data ([HN](https://news.ycombinator.com/item?id=41774712), [press quotes](https://nomads.com/faq)).

## Why they use it instead of alternatives

The job-to-be-done: *"When I pick my next base, I want to weigh cost, internet, weather and safety at once — and have people waiting when I land."* Numbeo/Expatistan offer raw cost tables with no nomad scoring and no people; Facebook groups and Reddit offer people but fragmented, stale info. Nomad List merges normalized public datasets (UN, WHO, IMF, World Bank) plus live measurements, re-scored every 10 minutes ([FAQ](https://nomads.com/faq)) with the social layer — who's there now, reviews, meetups — in one place; users recommend it exactly for that combined use ([HN](https://news.ycombinator.com/item?id=31770138)).

## What I would build better

1. **Provable data quality.** The site itself admits inaccuracies ([FAQ](https://nomads.com/faq)), and users have found costs off by 2-3x ([HN](https://news.ycombinator.com/item?id=8107490)). I'd show sources, sample sizes, last-updated dates and confidence per figure, plus personal cost profiles. Why first: the ranking IS the product — distrust poisons everything downstream, including API sales.
2. **Community health as a feature.** A member publicly turned on the product after finding chat mods were rampant anti-vaxxers with the founder doing nothing about it ([HN](https://news.ycombinator.com/item?id=33641157)), and chat has since fled to Telegram, fragmenting the loop ([HN](https://news.ycombinator.com/item?id=38987978)). I'd rebuild moderation and in-house chat, because the testimonials show community — not data — is what converts members.
3. **Personalized "your score" ranking.** Today's Nomad Score is one-size-fits-most; with the API already exposing the site's underlying city data, a ranking weighted by your budget, passport, climate taste and friends' locations turns commodity data into a personal moat ([API docs](https://nomads.com/api/v3)).

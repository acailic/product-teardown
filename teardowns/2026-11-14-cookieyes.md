# Teardown: CookieYes — a million-site cookie banner, metered by pageviews

- **Date analyzed:** 2026-11-14
- **Category:** B2B/B2C · compliance SaaS (consent management) + free WordPress plugin
- **Model:** per-domain subscription (free → Basic → Pro → Ultimate), metered by pageviews and scan limits; agency reseller discounts; owned by Mozilor alongside WebToffee and WebYes
- **Prices as seen (2026-11-14):** Free $0 (5,000 pageviews/mo, 100 pages/scan, 5 scans/mo) · Basic $10/mo/domain or $100/yr (100,000 pageviews/mo, + $0.30 per 1,000 extra, 600 pages/scan) · Pro $25/mo or $250/yr (300,000 pageviews + same overage, 4,000 pages/scan, geo-targeting, IAB TCF v2.4) · Ultimate $55/mo or $550/yr (unlimited pageviews, 8,000 pages/scan, branding removal) — annual billing is "2 months free" ([pricing](https://cookieyes.com/pricing/)); Black Friday 2026 promo "up to 50% off" running ([BF page](https://www.cookieyes.com/black-friday/))
- **Revenue evidence:** **estimated** — no public revenue figures; verified anchors: 1+ million active WordPress installs ([plugin](https://wordpress.org/plugins/cookie-law-info/)), 3,238 ratings at 4.8/5 ([wp.org API](https://api.wordpress.org/plugins/info/1.0/cookie-law-info.json)); "1.5M+ businesses" and "100+ employees" are vendor claims ([Mozilor](https://www.mozilor.com/about/))

## 0. The essence (ELI9)

CookieYes makes the "accept cookies?" box you see on nearly every website — and it gives that box away free, especially to WordPress sites, which is why over a million of them carry it. The box is free while your site is small; when it grows, or needs different boxes for different countries, you pay $10–55 a month per website — a bill that grows with traffic. The money keeps coming because laws (GDPR in Europe, cousins elsewhere) say websites must ask before tracking, and Google increasingly refuses to count your ads unless the box works properly. The company behind it, Mozilor, was one student in an Indian college incubator in 2017 and now has 100+ people — and it owns a WordPress-plugin shop, so the free plugin doubles as its shop window.

## 1. What it is, and for whom

CookieYes is a consent management platform (CMP): a cookie banner that blocks tracking scripts until visitors consent, a site scanner that inventories cookies, a consent log, and free privacy/cookie-policy generators ([product](https://www.cookieyes.com/product/cookie-consent/)). It ships two ways: a WordPress plugin that "works without an account" and a cloud app connected by a one-line script for any CMS ([plugin page](https://wordpress.org/plugins/cookie-law-info/)). It markets itself as a Google-certified CMP supporting Consent Mode v2 on all plans and IAB TCF v2.4 from Pro up ([pricing](https://cookieyes.com/pricing/)). The primary user is the small website owner with no legal team; agencies sit above. It is owned by Mozilor (founded 2017 by Anvar TK at NIT Calicut; London/Cochin/Calicut offices), alongside WebToffee and WebYes ([Mozilor](https://www.mozilor.com/about/)). The WordPress plugin itself dates to 2012 and was WebToffee's "GDPR Cookie Consent" by 2020 ([wp.org API](https://api.wordpress.org/plugins/info/1.0/cookie-law-info.json), [2020 archive](http://web.archive.org/web/20200617015743/https://wordpress.org/plugins/cookie-law-info/)) — the rebrand welded a million-install funnel onto the new SaaS.

## 2. How it earns

**Per-domain subscription metered by pageviews** ([pricing, seen 2026-11-14](https://cookieyes.com/pricing/)):

- **The meter:** free up to 5,000 pageviews/month (a pageview is every load of a page carrying the banner code); Basic buys 100K, Pro 300K, then **+$0.30 per 1,000 overage** — traffic growth converts directly into revenue, and scan limits climb with the plan (100 → 600 → 4,000 → 8,000 pages).
- **Upgrades are feature-laddered:** geo-targeting, scheduled scanning, TCF v2.4 and GPC land at Pro ($25/mo, "most popular"); branding removal, login-behind scanning and static-IP scanning at Ultimate ($55/mo). Advertiser table stakes — Consent Mode v2, GTM, Microsoft UET — are free in every tier, a deliberate funnel floor.
- **Volume motion:** multi-domain accounts with one free domain, an agency program advertising "up to 50% partner discounts" and "recurring revenue" for resellers ([agency](https://www.cookieyes.com/partners/agency/)), custom Enterprise plans, plus a seasonal discount cadence (Black Friday, "up to 50% off").
- 14-day trials on paid plans; annual billing sold as "2 months free."

**Revenue: estimated.** No figures are published; the private Mozilor discloses only user counts. Third-party review platforms corroborate scale, not money: Capterra 4.7/5 and G2 4.8/5 badges on the homepage (vendor-displayed), WordPress 4.8/5 from 3,238 ratings (verified).

## 3. Who the customers are

- **WordPress site owners** — the plugin's 1+ million active installs ([wp.org](https://wordpress.org/plugins/cookie-law-info/)) are dominated by blogs and small sites; the free tier's limits (5K pageviews, 100 pages/scan) are sized exactly for them.
- **SMBs and e-commerce with growing traffic** — the pricing page names them directly: "for small business and startups," "for medium business with growing traffic" ([pricing](https://cookieyes.com/pricing/)).
- **Ad-running sites with EU visitors** — Consent Mode v2 everywhere plus TCF 2.4 at Pro targets keeping Google Ads and EEA programmatic inventory alive.
- **Agencies managing client sites** — a dedicated reseller track with partner discounts and a client-management dashboard ([agency](https://www.cookieyes.com/partners/agency/)).
- A quieter channel: HN commenters repeatedly cite CookieYes's blog as the reference on consent law ([example](https://news.ycombinator.com/item?id=41108152)) — content SEO feeds all segments.

## 4. Why they use it

The job: **put a legally credible consent banner live today, without a developer or lawyer.** The plugin installs in minutes, scans the site, generates the policies, and blocks scripts until consent. The realistic alternatives — hand-rolling a banner and hoping it complies, a lawyer, or rival CMPs (Cookiebot, Complianz, Termly at $10–20/site, iubenda at €5–80/site ([sibling teardown](2026-11-09-iubenda.md))) — all start paid or DIY, where CookieYes starts free with advertiser integrations included. The WordPress plugin is the moat: a site owner picks the 4.8-star million-install default rather than evaluating CMPs. They stay because the banner is embedded, the consent log accumulates, and $10–25/month is cheaper than reconsidering. CookieYes itself concedes the limit of the promise: "installing CookieYes does not on its own make your site compliant" ([plugin page](https://wordpress.org/plugins/cookie-law-info/)).

## 5. What I would build better

1. **Sell consent performance, not just consent plumbing.** The pricing page's headline is cost ("Get cookie compliant without the high costs"), yet the buyer with budget is the marketer whose real fear is conversions collapsing when consent rates drop. "Consent trends & pageviews" reporting already exists in every tier but is buried as a checkbox ([pricing](https://cookieyes.com/pricing/)). Making it the product — consent rate by region/language, banner A/B tests, modeled-conversion recovery under Consent Mode — moves CookieYes from a compliance utility into the ad-performance stack, where $25/month looks cheap.
2. **Package proof of compliance as the upsell.** CookieYes's own disclaimer — installing it "does not on its own make your site compliant" — names the gap: customers get paperwork, not evidence. The consent log and scan history already exist; exporting them as a dated, continuously refreshed compliance attestation (for clients, insurers, platforms) is the SKU Vanta proved sells at enterprise scale ([sibling teardown](2026-11-12-vanta.md)) and that a CMP is uniquely positioned to own.
3. **Turn the agency discount into an agency product.** The agency page sells discounts ("up to 50% partner discounts"); Termly sells a workflow ("manage hundreds of clients from one dashboard" ([teardown](2026-11-13-termly.md))). A fleet console — cross-client consent analytics, white-label client reports, consolidated billing — converts resellers from discount-seekers into platform subscribers, and the 2021 XSS episode in the million-install plugin ([archived report](http://web.archive.org/web/20250809154623/https://portswigger.net/daily-swig/wordpress-security-cookieyes-gdpr-plugin-patches-xss-bug-following-large-scale-php-audit)) suggests agencies would also pay for a published security posture on the script that gates every client's site.

---

*All sources inline; prices are snapshots from 2026-11-14.*

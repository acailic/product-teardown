# Teardown: EvidentTrail — continuous audit evidence as a thin layer on GitHub

- **Date analyzed:** 2026-11-10
- **Category:** B2B · early-stage compliance SaaS (audit evidence)
- **Model:** freemium subscription metered in evidence packs/month (planned); currently Early Access, no public prices
- **Prices as seen (2026-11-10):** guest mode free (24h, one report per repo, no account); plans in the public JS bundle: Free 0 packs/mo (no long-term retention) · Starter 5 (7-day retention) · Growth 25 (30-day) · Enterprise unlimited (90-day) ([bundle, seen 2026-11-10](https://evidenttrail.com/assets/index-FEU-2aSA.js)); no dollar prices published — "Contact us for current plan details" ([FAQ](https://evidenttrail.com/faq)); Stripe billing wired ([Terms](https://evidenttrail.com/terms))
- **Revenue evidence:** **estimated ≈ €0 — effectively pre-revenue.** Founder at launch: "First launch, no users yet" ([Show HN, 2026-02-25](https://news.ycombinator.com/item?id=47151920)); no public customers or revenue claims found

## 0. The essence (ELI9)

Companies that build software must periodically prove to a safety inspector — an auditor — that "someone always double-checked the work before it shipped." The proof already exists inside GitHub: who approved each change, which tests ran, who was allowed to merge. Collecting it into inspector-shaped folders means weeks of screenshots and spreadsheets. EvidentTrail, a tiny Dutch operation, plugs into GitHub read-only and keeps a sealed, day-by-day diary of all that checking — so when the inspector knocks, the folder assembles itself. It is "Early Access" today, free while hunting for its first real teams, and plans to charge monthly rent priced by how many sealed folders you keep.

## 1. What it is, and for whom

EvidentTrail is a web app plus a read-only GitHub App that captures PR approvals, required CI checks, branch-protection snapshots and drift, exceptions, and AI-assisted-commit oversight signals, maps them to specific controls — SOC 2 CC8.1/CC6.1/CC7.4, ISO 27001 A.8.32/A.8.9, EU AI Act Art. 14 — and exports them as tamper-evident "evidence packs" (PDF/CSV/JSON + SHA-256 manifest) ([homepage](https://evidenttrail.com/)); auditors can open packs in guest mode without an account ([SOC 2 page](https://evidenttrail.com/soc2-change-management-evidence)). The primary user: the engineer or security lead at a small software company heading into its first SOC 2 or ISO 27001 audit. The GitHub App was created 2026-01-01, read-only ([GitHub API](https://api.github.com/apps/evidenttrail), [listing](https://github.com/apps/evidenttrail)); the site first hit the Internet Archive on 2026-02-25 — launch day ([Wayback](http://web.archive.org/web/20260225143004/https://evidenttrail.com/)); Terms date from January 2026 ([Terms](https://evidenttrail.com/terms)). Closed-source, no team page, "Operated by EvidentTrail (Early Access), Netherlands" ([footer](https://evidenttrail.com/)); the founder is publicly visible only as HN user `elviro`.

## 2. How it earns

Today it earns essentially nothing publicly — the honest snapshot records that. The Terms say "Paid plans **may be** offered. If you purchase a subscription, billing is handled by Stripe and subject to plan limits, including repository limits and retention periods" ([Terms](https://evidenttrail.com/terms)) — billing wired, sales not visible. The intended revenue unit is the **evidence pack per month**, retention as the upgrade lever (public bundle, [seen 2026-11-10](https://evidenttrail.com/assets/index-FEU-2aSA.js)). Pricing itself is gated: "Pricing is plan-based... Contact us for current plan details" ([FAQ](https://evidenttrail.com/faq)). The launch thread drew 2 points, zero comments; no third-party mentions exist — a verified absence of revenue evidence.

## 3. Who the customers are

Segments are vendor positioning — marked as vendor claims — because third-party corroboration is near zero:

- **Engineering-led startups before their first SOC 2 Type II** — the core pitch: "Stop manually screenshotting pull requests" ([vendor claim, SOC 2 page](https://evidenttrail.com/soc2-change-management-evidence)).
- **Teams using GitHub Copilot facing EU AI Act human-oversight duties** — the homepage leads with an "EU AI Act enforcement: August 2, 2026" countdown and sells AI-oversight evidence linking Copilot co-author signals to human reviewer approvals ([vendor claim, homepage](https://evidenttrail.com/)).
- **Outsourced-development shops** proving change control to client auditors — a dedicated landing page ([vendor claim](https://evidenttrail.com/outsourced-software-change-control)).
- **Internal audit teams** — FAQ: "Yes... sample changes for testing" ([vendor claim](https://evidenttrail.com/faq)).

Missing: any review, forum thread, or named customer — these segments are hypotheses anchored in vendor positioning alone.

## 4. Why they use it

**Pass the audit without two weeks of spreadsheet archaeology — and survive SOC 2 Type II**, which samples controls across a 6–12 month window: "screenshots taken retrospectively cannot prove that controls were operating six months ago" ([vendor copy](https://evidenttrail.com/soc2-change-management-evidence), accurate to the standard). Alternatives: manual export (free, point-in-time, labor-heavy); homegrown scripts (a maintenance tax); GitHub itself (no auditor-ready export); or a GRC platform like Vanta, Drata, or Secureframe — broad suites whose entry is a sales conversation: as seen on 2026-11-10, Vanta's pricing page publishes no prices, only "Request a free demo... to get personalized pricing" ([vanta.com/pricing](https://vanta.com/pricing)). EvidentTrail's bet is complement-not-replace: packs export in "JSON format compatible with GRC platform ingestion... imported into Vanta, Drata, Secureframe" ([vendor claim](https://evidenttrail.com/soc2-change-management-evidence)) — cheap continuous evidence beneath an expensive platform.

## 5. What I would build better

1. **Publish prices and sell self-serve.** A thin evidence layer can only live next to Vanta by being cheap and instant; yet the FAQ gates pricing behind "contact us" ([FAQ](https://evidenttrail.com/faq)) — copying the demo-gated motion of the incumbent it undercuts ([Vanta pricing, seen 2026-11-10](https://vanta.com/pricing)). A 10–50 person company will not book an enterprise demo for audit prep; a published monthly price is the top of this offer, not a detail.
2. **Make auditors the distribution channel.** Guest mode already lets an auditor open packs account-free; extend it into sampling-native "sample packs" answering a CPA firm's actual request — "show me N sampled changes across the period" ([the vendor's own copy describes this sampling](https://evidenttrail.com/soc2-change-management-evidence)). An auditor who asks every client for EvidentTrail packs turns each engagement into distribution; today the tool treats auditors as readers, not the wedge.
3. **Lead with the EU AI Act Art. 14 SKU.** SOC 2 has no deadline; the AI Act does — the vendor counts down to August 2, 2026 enforcement on its homepage ([homepage](https://evidenttrail.com/)). "Who reviewed AI-assisted code" is a fresh, deadline-driven buying event with no packaged incumbent answer, yet it sits as a sub-feature. Packaging Copilot-oversight packs as the flagship would give a nine-month-old product its own market instead of Vanta's crumbs.

---

*All sources inline; prices are snapshots from 2026-11-10.*

# Teardown: Promptfoo — the open-source AI tester that OpenAI is buying

- **Date analyzed:** 2026-11-07
- **Category:** B2B · open-source developer tool → enterprise AI-security SaaS
- **Model:** open-core (free MIT framework + custom-priced Enterprise / On-Premise), agreed to be acquired by OpenAI 2026-03-09
- **Prices as seen (2026-11-07):** Community $0 "free forever" (red teaming capped at 10k probes/month) · Enterprise Custom · On-Premise Custom ([pricing](https://www.promptfoo.dev/pricing/))
- **Revenue evidence:** funding and exit agreement **verified** ([Series A](https://www.promptfoo.dev/blog/series-a-announcement/), [OpenAI acquisition](https://openai.com/index/openai-to-acquire-promptfoo/)); revenue itself **estimated** — no public figures, but "10 or 12 paying customers… the ones we do have are massive" ([Promptfoo engineer, FusionAuth case study](https://fusionauth.io/blog/promptfoo-case-study))

## 0. The essence (ELI9)

When a company builds a robot helper that talks to people, someone mean has to try to trick it — whisper secrets out of it, make it do naughty things — *before* real bad guys do. Promptfoo is that mean tester, but it's a computer program anyone can use for free. About 350,000 programmers have used it ([vendor claim](https://www.promptfoo.dev/blog/promptfoo-joining-openai/)), and big companies pay lots of money for the extra-strong version that comes with dashboards, support and permission to run inside their own locked buildings. The tool became so important that OpenAI — one of the world's biggest AI companies — agreed to buy the whole company in March 2026 so every AI helper could get tested that way.

## 1. What it is, and for whom

Promptfoo is an open-source CLI and library for evaluating, comparing and **red-teaming** LLM applications — prompts, RAG pipelines and agents — with CI/CD integration ([GitHub, 26,925 stars, MIT](https://github.com/promptfoo/promptfoo)). It began in May 2023 as a one-author CLI for picking the best prompt/model combination ("I built this because I'm tuning a bunch of prompts and don't have a great way to do this systematically" — [Ian Webster, Show HN](https://news.ycombinator.com/item?id=35807020)). The company was founded in 2024 by Webster (ex-Discord LLM engineering) and Michael D'Angelo (ex-Head of AI, Smile Identity), pivoting from eval tooling to **AI security**: automated red teaming, guardrails, model-security scanning and MCP-proxy tooling ([about](https://www.promptfoo.dev/about/)). The primary user is the AI platform/AppSec engineer at an enterprise shipping LLM features to production.

## 2. How it earns

**Open-core with enterprise contracts.** The framework is free and MIT-licensed; the paid product is an Enterprise platform — central dashboards, SSO, continuous monitoring, compliance reports — and an On-Premise edition; both are "Custom — contact us" ([pricing, seen 2026-11-07](https://www.promptfoo.dev/pricing/)). **Revenue units: red-team "probes" (a single request attacking the target), seats and deployment model** — the free tier meters red teaming at 10k probes/month, and enterprises buy custom limits plus air-gapped installs (80–90% of enterprise customers require on-premise, per the [FusionAuth case study](https://fusionauth.io/blog/promptfoo-case-study)).

**Evidence:** $18.4M Series A led by Insight Partners with a16z participating, July 2025 ([announcement](https://www.promptfoo.dev/blog/series-a-announcement/)); agreed to be acquired by OpenAI, announced 2026-03-09, terms undisclosed, tech to be folded into OpenAI Frontier ([OpenAI](https://openai.com/index/openai-to-acquire-promptfoo/), [promptfoo blog](https://www.promptfoo.dev/blog/promptfoo-joining-openai/)). Actual revenue was never disclosed (**estimated**); the closest primary figure is a principal engineer, Dec 2025: "up to 10 or 12 paying customers… massive" Fortune 1000/500 accounts with 5,000+ users each ([case study](https://fusionauth.io/blog/promptfoo-case-study)) — contrast with the vendor claim that "40+ Fortune 500 companies run Promptfoo" ([Series A post](https://www.promptfoo.dev/blog/series-a-announcement/)): running ≠ paying.

## 3. Who the customers are

- **Regulated, conservative enterprises** — the paying base. Promptfoo sells by *industry*: financial services ("FINRA-aligned security testing") ([finance](https://www.promptfoo.dev/solutions/finance/)), insurance, telecom, real estate ("fair housing compliance testing") ([real estate](https://www.promptfoo.dev/solutions/real-estate/)); vendor claims "25% of the Fortune 500 rely on it" ([joining-OpenAI post](https://www.promptfoo.dev/blog/promptfoo-joining-openai/)); the case study names signed Fortune 500 contracts and three-week deployment deadlines.
- **AI labs** — "Foundation model labs test their models with Promptfoo before release"; the repo is billed "Used by OpenAI and Anthropic" (both [vendor claims](https://github.com/promptfoo/promptfoo)).
- **Individual developers** — 350k used / 130k monthly active, 381+ OSS contributors (all [vendor claims](https://www.promptfoo.dev/about/)); third-party practitioners adopt it for serious evals, e.g. Simon Willison exploring SNAP benefits-eligibility evals ([blog](https://simonwillison.net/2025/Apr/24/exploring-promptfoo/)).

## 4. Why they use it

The job-to-be-done: **get AI features past security review and into production without becoming the next breach headline.** "AI security has become the largest blocker to enterprises shipping generative AI applications to end users" (vendor framing, [Series A](https://www.promptfoo.dev/blog/series-a-announcement/)), sharpened by regulation the vendor cites: EU AI Act fines, OWASP LLM Top 10, NIST AI RMF. Alternatives: manual pentest consultants (slow, expensive); homegrown eval scripts (what the founder himself lacked); eval platforms like LangSmith/Langfuse (observability, not adversarial security); or shipping on vibes. Promptfoo won on zero-cost local start, CI/CD fit, and red-teaming breadth — moving teams from "vibes-based" testing to rigorous quality evaluations to comprehensive red teaming ([Series A](https://www.promptfoo.dev/blog/series-a-announcement/)).

## 5. What I would build better

1. **The neutral trust anchor.** A testing company owned by a model vendor is a referee employed by one team; within a week of the deal announcement developers were already asking what to use instead ([Ask HN, 2026-03-17](https://news.ycombinator.com/item?id=47412524)). An independent, vendor-neutral eval/red-team harness — the SSL-Labs-of-agents, with published methodology — is the gap the acquisition itself opened, and compliance buyers pay for independence.
2. **A self-serve middle tier.** 130k monthly-active developers sit on a free CLI with no priced rung between $0 and "Custom": the paid offer serves ~10–12 whales ([case study](https://fusionauth.io/blog/promptfoo-case-study)). A hosted $50–100/seat/month regression-CI for small agent teams — alerts on every prompt or model change — monetizes the long tail promptfoo never touched.
3. **Deterministic workflow testing for n8n/Make/Zapier automations.** Promptfoo tests LLM behavior, not the non-LLM workflow platforms where small-business automations silently break; that territory (cf. [Healthchecks teardown](2026-11-06-healthchecks.md)) is still served only by cron watchdogs, not regression suites.

## Sources

- [Pricing](https://www.promptfoo.dev/pricing/) (snapshot 2026-11-07) · [About](https://www.promptfoo.dev/about/) · [GitHub](https://github.com/promptfoo/promptfoo) — vendor, product and license
- [Finance solutions](https://www.promptfoo.dev/solutions/finance/) · [Real estate solutions](https://www.promptfoo.dev/solutions/real-estate/) — industry-specific compliance testing claims
- [Series A $18.4M](https://www.promptfoo.dev/blog/series-a-announcement/) (2025-07-29) · [Joining OpenAI](https://www.promptfoo.dev/blog/promptfoo-joining-openai/) (2026-03-09) · [OpenAI announcement](https://openai.com/index/openai-to-acquire-promptfoo/) — funding, exit, vendor traction claims
- [Show HN 2023](https://news.ycombinator.com/item?id=35807020) — founder origin quote · [Ask HN 2026](https://news.ycombinator.com/item?id=47412524) — post-acquisition neutrality gap
- [FusionAuth case study](https://fusionauth.io/blog/promptfoo-case-study) (2025-12-08) — primary engineer quotes: paying-customer count, on-prem share, team size
- [Simon Willison](https://simonwillison.net/2025/Apr/24/exploring-promptfoo/) (2025-04-24) — third-party practitioner adoption

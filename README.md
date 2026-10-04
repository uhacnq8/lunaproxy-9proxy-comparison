# lunaproxy review: Real Prices, IP Quality and Refund Complaints, and a Per-IP Alternative With Unlimited Bandwidth

LunaProxy turns up on almost every "cheapest residential proxies" list, usually attached to a headline rate between $0.65 and $0.77 per GB. That number is real, but it isn't the number most people end up paying, and it isn't the thing that generates the complaints you'll find once you dig past the sponsored roundups.

If you're searching for a lunaproxy review right now, you're probably trying to answer one of three questions: what does it actually cost, do the IPs hold up under real blocking, and what happens if it doesn't work. This covers all three, plus the billing-model question most reviews skip entirely.

> **Short version:** LunaProxy is a genuine budget residential network with real strengths on price and coverage breadth, and real weaknesses on IP quality verification, refund handling, and support responsiveness. It's a reasonable first or second provider if you test small. If your work needs unlimited transfer on a fixed number of IPs — or you're scraping anything in finance — 9Proxy's per-IP model sidesteps a lot of LunaProxy's problems.

## What LunaProxy actually sells

It's easy to assume LunaProxy is just rotating residential GB. It isn't. The catalog has five product lines:

- **Rotating residential** — the flagship. Metered GB, no per-IP charge, no request or concurrency caps, country and city-level targeting.
- **Static ISP proxies** — billed per IP with unlimited bandwidth, positioned at roughly $3 per IP per week.
- **Dedicated datacenter proxies** — sold per IP, or as traffic plans that start near $3.30 per GB and fall toward $0.77 per GB at multi-terabyte volumes.
- **Unlimited residential** — bandwidth-unlimited access sold in daily increments.
- **Rotating ISP and a Universal Scraping API** — the API is a separate line item, not bundled into the proxy plans.

Protocols are HTTP(S) and SOCKS5 across the board, and the proxy manager is included rather than gated behind a paid tier — one of the few places LunaProxy clearly beats pricier competitors on packaging.

## LunaProxy pricing: what the tiers actually cost

Here's the part where the marketing and the self-serve page disagree, and it's worth understanding why.

The site banner advertises "from $0.65/GB." A separate FAQ page says plans start at $0.77/GB with 200 GB added at no cost. Meanwhile LunaProxy's own help center lists these tiers:

| Plan | Rate | Notes |
| --- | --- | --- |
| 5 GB | $3.00/GB | Entry, metered |
| 40 GB | $2.10/GB | Metered |
| 150 GB | $1.80/GB | Metered |
| 280 GB | $1.50/GB | Metered |
| 1,000 GB | $0.80/GB | Metered |
| 5,000 GB | $0.70/GB | Metered |

The headline $0.65–$0.77 rates reflect the largest commitment tiers plus whatever promotion is running that week. If you're buying 5 or 40 GB — which is where most people start — you're paying $2–3 per GB, not 65 cents. There's nothing dishonest about volume pricing, but the gap between the banner and the 5 GB tier is large enough that people notice after they've paid.

Two genuinely useful details: rotating-pool plans carry no per-IP charge and no concurrency or request limits, and metered plans can be extended to 60 or 90 days with traffic rollover if you renew before expiry. That rollover matters — plenty of budget providers expire your unused balance at 30 days.

## Where the performance numbers diverge

LunaProxy advertises a 99.99% success rate and roughly 0.6-second average response times. Independent benchmark aggregation lands lower: around 98% success and a P95 latency near 1.2 seconds on rotating residential. Sub-100% success on a budget pool is normal and not a dealbreaker. But a P95 double the advertised average is the difference between "this works fine" and "my pipeline stalls at scale," depending entirely on your concurrency.

The bigger structural issue is pool composition. The network legitimately holds a very large number of IPs, but the distribution skews toward Tier 2 and Tier 3 geographies — Brazil and India are heavily represented, while US and European depth is thinner than the headline count suggests. If your targets are US retail sites or EU financial data, this is the spec to test first, not the total IP count.

LunaProxy also publishes almost nothing about how those IPs are sourced, how the infrastructure is operated, or what KYC applies to users. Independent reviewers have described it as a reseller of a larger upstream network rather than an operator of its own. For scraping a public product catalog that's tolerable. For a compliance-driven engagement where you need to document provenance, it's a hard stop.

## Is LunaProxy legit? What the Trustpilot record shows

LunaProxy sits at roughly **3.6 out of 5 across about 105 reviews on Trustpilot** — a middling score that hides a genuinely bimodal distribution. The top reviews read like product marketing. The bottom reviews are specific, dated, and repetitive.

Four complaint patterns show up over and over:

1. **IPs get flagged by third-party checkers.** Reviewers describe static ISP proxies scoring as medium risk on Scamalytics and being identified as hosting-provider ranges on Ping0, which defeats the point of buying residential.
2. **A single detection standard is the arbiter.** Multiple reviews say support would only accept IPinfo results as proof of a bad IP — a complaint the company's own public replies confirm, with support explaining that IPinfo is their standard and offering to expand supported platforms in future. Users whose checkers disagree with IPinfo effectively have no remedy.
3. **Refunds are hard.** Several reviewers report buying traffic, finding the IPs useless, and being refused a refund even after sending screenshots. Company replies point to a refund policy with conditions, which is common practice — but the volume of people surprised by it suggests the conditions aren't prominent at checkout.
4. **Support isn't always immediate.** One long-standing review describes waiting 12 hours for a reply on Telegram. LunaProxy's own response acknowledges they don't run 24/7 coverage.

There's also a smaller set of reviews about geotargeting mismatches — a Turkish IP resolving as Singapore, for instance. And on the other side, plenty of reviewers praise support for actually resolving problems, sometimes going as far as manually crediting traffic to a new account after a wrong-username payment. Both things appear to be true: support can be helpful, and it isn't reliably fast.

One practical warning that has nothing to do with the company's service: lookalike domains using the LunaProxy name exist, including ones registered within the last year and flagged as suspicious by reputation scanners. If you land somewhere that isn't the domain you set out to visit, verify before entering payment details.

## Who LunaProxy is right for

- **Cost-first scraping of Tier 1/Tier 2 public sites**, where you can tolerate a percent or two of failures.
- **Broad geographic coverage needs** — 195 locations including city-level targeting is genuinely wide at this price point.
- **Mixed workloads.** Rotating residential, static ISP, datacenter, and an API under one account saves you from juggling vendors.
- **Teams that like traffic rollover**, because unused GB surviving 60–90 days is unusual in the budget tier.

And who should look elsewhere:

- Anyone scraping **financial or banking sites** — see the restriction section below, which applies to the alternative discussed here too.
- Workloads where **bandwidth is the unpredictable variable**. Metered GB punishes video, large file transfers, or anything where a runaway script can burn hundreds of dollars before you notice.
- Anyone needing **24/7 guaranteed support or documented IP provenance**.
- Anyone who wants a **free trial before paying**. Trial availability for individual users is inconsistently documented across sources, and the company's own materials lean toward no free trial for individuals.

## The alternative worth pricing: pay per IP, not per gigabyte

Here's the structural argument. LunaProxy's rotating pool bills by traffic consumed. If your workload is thousands of small requests spread across thousands of rotating IPs, metered GB is exactly right — each request costs almost nothing.

But if you're running hundreds of long-lived sessions — logged-in accounts, persistent carts, multi-step workflows — you're paying per gigabyte for bandwidth you could have bought once. That's the gap **9Proxy** fills, and it's a different billing philosophy rather than a slightly cheaper version of the same thing.

9Proxy runs a residential network advertised at 20M+ IPs across 90+ countries and offers two separate models:

- **Residential by IPs** — fixed price per IP, unlimited bandwidth while the IP is active, and unused IPs that never expire. IPs stay live anywhere from a few hours up to roughly 24 hours. Setup runs through the 9Proxy desktop app via local port forwarding, with optional auto-rotation at intervals you set on selected ports.
- **Residential by GB** — metered traffic with 180-day validity, unlimited endpoint generation, and both rotating and sticky modes. This one works straight from the dashboard with username/password or IP whitelist authentication, no app required.

Protocols cover HTTP(S) and SOCKS5, and city/state-level targeting is available. The per-IP model is the one to think about carefully: if your transfer volume is high and your IP count is modest, unlimited bandwidth per IP is a fundamentally cheaper shape than paying per gigabyte forever.

## 9Proxy plan pricing

IP-based plans, unlimited bandwidth per IP:

| Plan | Price | Per-IP rate | Get it |
| --- | --- | --- | --- |
| 100 IPs | $24 | $0.24/IP | Check live pricing |
| 500 IPs | $72 | $0.144/IP | Check live pricing |
| 1,000 IPs + 500 bonus | $126 | 500 bonus IPs included | Check live pricing |
| 100,000 IPs | $2,300 | $0.023/IP | See current plan price |
| 500,000 IPs | $8,625 | $0.017/IP | See current plan price |

These rates reflect a price adjustment — earlier third-party listings showed 100 IPs at $20. Verify before you commit, since the effective per-IP cost falls steeply with volume and the entry tier is the worst value in the table.

GB-based plans, 180-day validity:

| Plan | Total | Effective rate | Get it |
| --- | --- | --- | --- |
| 5 GB | $15 | $3.00/GB | Check live pricing |
| 50 GB (+5 GB bonus) | $105 | $2.10/GB on paid volume | Check live pricing |
| 100 GB | $150 | $1.50/GB | Check live pricing |
| 200 GB | $200 | $1.00/GB | See current plan price |
| 1,000 GB | $800 | $0.80/GB | See current plan price |
| 2,000 GB | $1,500 | $0.75/GB | See current plan price |
| 10,000 GB | — | ~$0.68/GB | See current plan price |

Bundle plans, combining IPs and traffic:

| Plan | Includes | Price | Get it |
| --- | --- | --- | --- |
| Starter | 100 IPs + 5 GB | $30 | Check live pricing |
| Popular | 1,500 IPs + 50 GB | $180 | Check live pricing |
| Pro | 5,000 IPs + 500 GB | $720 | See current plan price |

Trial access at 9Proxy is promotion-based rather than a standing free tier, so ask support before assuming you can test for nothing. There's also a "Today List" feature that lets you reuse any proxy from the previous 24 hours at no extra charge, which the company estimates cuts costs around 30% for recurring session work.

## LunaProxy vs 9Proxy: the differences that actually change your bill

|  | LunaProxy | 9Proxy |
| --- | --- | --- |
| Primary billing | Per GB consumed | Per IP (unlimited bandwidth) or per GB |
| Entry rate | $3.00/GB at 5 GB | $24 for 100 IPs, or $3.00/GB at 5 GB |
| Unused balance | 60–90 day extension with rollover on renewal | IPs don't expire; GB valid 180 days |
| Setup | Dashboard and API, no app required | Dashboard for GB plans; desktop app for IP-based plans |
| Advertised pool | 200M+ IPs, 195 locations | 20M+ IPs, 90+ countries |
| Concurrency limits | None on rotating pool | Endpoint generation unlimited on GB plans |
| Protocols | HTTP(S), SOCKS5 | HTTP(S), SOCKS5 |

The pool-size gap is real and worth weighing: LunaProxy advertises more than ten times the IP count and considerably wider location coverage. If your task needs a specific small city in a country that 9Proxy doesn't carry, LunaProxy wins on availability regardless of price. If your task needs a lot of bandwidth through a moderate number of IPs, the per-IP model wins on arithmetic.

## What 9Proxy restricts — read this before you buy

9Proxy's acceptable use policy is unusually explicit, and two changes affect real workflows:

- **Effective March 15, 2026:** access restrictions on all banking and financial institution websites.
- **Effective April 1, 2026:** heavy media streaming platforms, including Netflix, YouTube, and Spotify, are restricted on IP-based plans. They remain supported on GB-based plans.

The network also proactively blocks adult content, .gov domains, and known malicious domains, and forbids ad and click fraud, fake engagement, bulk automated account creation, SEO manipulation, survey fraud, and scraping data behind logins or paywalls. If any of those are on your roadmap, this isn't the provider for you — and given how much affiliate marketing surrounds this category, it's better to know that before you top up rather than after.

One more honest note that applies to both providers: third-party catalogs have reported at least one extended service interruption at 9Proxy during 2026, and LunaProxy's own complaint history includes periods of slow support. Treat any proxy vendor as infrastructure you should be able to swap. Test small, keep a second route, and don't prepay a year to chase a discount.

## How to test either provider without wasting money

1. **Buy the smallest tier that covers a real task**, not a synthetic speed test. 5 GB or 100 IPs is enough to learn whether your target site tolerates the pool.
2. **Log success rates yourself for 48 hours.** Vendor dashboards and third-party checkers disagree constantly — measure what your actual targets do.
3. **Check the geotargeting you paid for.** Verify via multiple IP intelligence tools, and if you're on LunaProxy, know in advance that IPinfo is the reference their support uses.
4. **Confirm the restrictions before topping up.** Streaming, finance, and .gov categories are where most surprise refund requests originate.
5. **Scale in steps.** Both providers drop rates sharply at volume. Get to 200 GB or 1,000 IPs on the cheapest tier first.

## FAQ

**Is LunaProxy a scam?**
No. It's a real provider that delivers working proxies, with roughly 3.6/5 across about 105 Trustpilot reviews. The recurring problems are IP quality on the static ISP line, refund refusals, and non-24/7 support — service issues, not fraud.

**Why do LunaProxy reviews contradict each other so sharply?**
Because the provider's quality varies by product line and geography. Someone using rotating residential for Tier 2 scraping and someone using static ISP proxies in the US are reviewing two different experiences under one brand name. Check which product the reviewer used before trusting the verdict.

**Is 9Proxy cheaper than LunaProxy?**
It depends entirely on your traffic-to-IP ratio. At 5 GB both land near $3.00/GB. Above that they diverge: LunaProxy keeps dropping per-GB while 9Proxy charges a flat rate per IP with unlimited bandwidth. Low transfer plus many IPs favors 9Proxy's IP model; high transfer through few IPs is where the per-IP model saves the most.

**Can I use LunaProxy if I'm already on 9Proxy, or the reverse?**
Yes, and for anything production-critical you probably should. Neither provider guarantees access to a specific third-party site, and both have had reliability wobbles. Running one as primary and one as failover is cheaper than a single outage.

**Which should I pick first?**
Start with the model that matches your workload shape, not the brand. Metered GB for high-rotation, low-transfer tasks. Per-IP with unlimited bandwidth for long sessions or predictable heavy transfer. Get that decision right and the rest is a rounding error on your invoice.

<｜｜tool▁calls▁begin｜｜>

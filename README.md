# WordPress VPS: Is It Worth Leaving Shared Hosting, How Much RAM Do You Need, and Which Plan Actually Fits? (Every Plan Compared, With Real Prices and Hidden Costs)

A WordPress VPS gives your site dedicated CPU, RAM and NVMe storage plus root access, so a traffic spike stops competing with everyone else's cron jobs for processor time. That argument for leaving shared hosting holds up. What doesn't hold up is treating "VPS" as one product category — a managed WordPress VPS and a bare KVM box with a root password in your inbox are further apart than shared hosting and either of them.

Here is the part most plan-comparison posts skip: the number that decides whether your site survives a spike isn't the traffic allowance, it's whether your cart and checkout pages can be cached. They can't. Every order hits PHP and MySQL directly, which is why a 1 GB RAM box that benchmarks fine on a static page falls over on the third simultaneous checkout. Keep that in mind as we go through the plans.

> **Short on time?**

>

> - **You want someone else to own updates, caching and backups** → buy managed WordPress hosting. Nothing below applies to you, and a VPS will cost you more in hours than in dollars.

> - **You want root, your own caching stack and no plugin blocklist** → a self-managed WordPress VPS. On LisaHost, the realistic starting point is the **进阶版 at ¥158/month** (2 vCPU, 2 GB RAM, 40 GB NVMe). The 1 GB plans are test boxes, not production blogs.

> - **You're running WooCommerce, a membership site or several client sites** → **豪华版 at ¥388/month** (4 vCPU, 4 GB RAM, 80 GB NVMe, 100 Mbps), and budget an evening for tuning.

>

> 👉 [See current LisaHost plans and live pricing](https://lisahost.com/aff.php?aff=1587)

---

## What a WordPress VPS actually is

A VPS runs WordPress on a virtual server instead of a shared account. You get allocated CPU cores and RAM that other customers can't touch, root or SSH access, and the freedom to pick your web server, PHP version, cache layer, firewall and backup method. On a shared account, none of those are yours to choose.

The distinction that matters more is **who operates it**:

|  | Shared hosting | Managed WordPress | Self-managed WordPress VPS |
| --- | --- | --- | --- |
| **Resources** | Pooled across every account on the machine | Dedicated, but often capped or throttled | Allocated to your instance |
| **Access** | No root, usually no SSH | No root, dashboard only | Full root and SSH |
| **Plugins and themes** | Sometimes restricted | Frequently blocklisted when they overlap with the host's own tooling | Anything you want |
| **Caching and PHP version** | Fixed by the host | Fixed by the host | Your choice, your responsibility |
| **Security, firewall, DDoS** | Provider | Provider | You |
| **Backups** | Provider | Provider | You, or a paid add-on |
| **Scaling** | Change plan, hope | Change plan, hope | Resize, add capacity, or migrate up a tier |
| **Typical buyer** | First site | Hands-off site owner | Developers, agencies, high-traffic publishers |

The right-hand column is the honest trade. You are not buying convenience — you are buying control and paying for it in labour. A VPS that nobody administers is a slower, more expensive shared host with a worse security posture.

### The one thing a VPS genuinely fixes

When a traffic spike turns your site into a timeout page, the real explanation is usually queueing, not a bad plugin. On a shared machine your account waits behind every other account for processor time. On a VPS, the CPU you paid for is yours around the clock, and unused capacity on the host can often be borrowed during a burst.

That is a real, structural fix. It is also the only one a VPS gives you for free.

---

## How much RAM does WordPress actually need?

Vendors love selling 1 GB plans to people who have never watched `htop` during a crawl. Rough working numbers, assuming a stock LEMP stack with a page cache in front:

- **1 GB RAM** — PHP-FPM, MariaDB and WordPress with a cache plugin. Fine for a brochure site with steady low traffic. One uncached WooCommerce checkout under concurrency and you'll see 502s. Treat this as a staging or test box.
- **2 GB RAM** — the practical floor for a real content site with a page cache, a handful of plugins and a search console crawl running alongside normal visitors.
- **4 GB RAM** — WooCommerce, membership sites, LMS plugins like LearnDash or LifterLMS, WordPress Multisite, or two to four small sites on one server.
- **8 GB and up** — large product catalogues, heavy background processing, or genuine concurrency during a sale.

Storage matters just as much and gets discussed less. A fresh Linux install plus WordPress plus a database takes roughly 4–6 GB before you upload a single image. A 10 GB NVMe disk leaves you around 5 GB for media, plugins, and every backup you forget to move off-server. For a media-heavy site, 40 GB is the floor and 80 GB is comfortable.

Bandwidth is the third number people misread. A **20 Mbps port** moves about 2.5 MB per second. An optimised WordPress page with images is commonly 1–2 MB. That's roughly one to two complete page loads per second at full saturation — fine for a low-traffic site, ugly during a social media spike. **"Unmetered traffic" is a statement about volume, not speed.**

---

## Every LisaHost plan, compared

LisaHost's headline feature is dual-ISP residential IP addresses — IPs registered to consumer broadband rather than data centres. That matters enormously for TikTok accounts, marketplace seller profiles and streaming unlocks. **It does nothing whatsoever for a WordPress site.** A residential IP does not make WordPress faster, rank better, or more secure.

So judge these plans on the hardware, not the IP label. All prices below are in Chinese yuan (CNY), billed monthly unless stated, and all plans are KVM with NVMe storage and a dedicated IPv4.

### US Los Angeles — AS9929, dual-ISP residential IP

| Plan | vCPU | RAM | NVMe | Port | Monthly traffic | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 精简版 | 1 | 1 GB | 10 GB | 50 Mbps | 1,000 GB | ¥68/mo | [Start with the entry plan](https://lisahost.com/aff.php?aff=1587) |
| 基础版 | 1 | 1 GB | 20 GB | 60 Mbps | 2,000 GB | ¥88/mo | [Get the 20 GB budget plan](https://lisahost.com/aff.php?aff=1587) |
| 进阶版 | 2 | 2 GB | 40 GB | 80 Mbps | 4,000 GB | ¥158/mo | [Pick the 2-core plan that can host a real site](https://lisahost.com/aff.php?aff=1587) |
| 豪华版 | 4 | 4 GB | 80 GB | 100 Mbps | 8,000 GB | ¥388/mo | [Choose the 4-core WooCommerce-capable plan](https://lisahost.com/aff.php?aff=1587) |
| 不限流量 Lite | 2 | 2 GB | 40 GB | 20 Mbps | Unmetered | ¥498/mo | [See the unmetered 20 Mbps plan](https://lisahost.com/aff.php?aff=1587) |
| 不限流量 Pro | 4 | 4 GB | 80 GB | 50 Mbps | Unmetered | ¥1,288/mo | [View the high-volume unmetered plan](https://lisahost.com/aff.php?aff=1587) |
| 特价年付版 | 1 | 1 GB | 10 GB | 50 Mbps | 600 GB | ¥499/yr (~¥41/mo) | [Check the annual budget deal](https://lisahost.com/aff.php?aff=1587) |

### Hong Kong — CMI / CU2 / CN2, three-network direct routing

| Plan | vCPU | RAM | NVMe | Port | Monthly traffic | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 基础版 | 1 | 1 GB | 20 GB | 30 Mbps | 1,000 GB | ¥88/mo | [Get the Hong Kong entry plan](https://lisahost.com/aff.php?aff=1587) |
| 进阶版 | 2 | 2 GB | 40 GB | 50 Mbps | 2,000 GB | ¥188/mo | [Compare the Hong Kong 2-core plan](https://lisahost.com/aff.php?aff=1587) |
| 不限流量 Lite | 2 | 2 GB | 40 GB | 30 Mbps | Unmetered | ¥998/mo | [Look at Hong Kong unmetered Lite](https://lisahost.com/aff.php?aff=1587) |
| 不限流量 Pro | 4 | 4 GB | 80 GB | 50 Mbps | Unmetered | ¥1,988/mo | [See Hong Kong unmetered Pro](https://lisahost.com/aff.php?aff=1587) |

LisaHost also sells native-IP ranges in Singapore, Taiwan, Japan, Korea, the UK, Germany and Vietnam. The Singapore line starts around **¥68/month** for a 1-core, 1 GB box with a 300 Mbps port; configurations and traffic allowances vary by region and change more often than the US and Hong Kong line-ups. Check the cart page for the current spec sheet before you commit to a region.

### What the price steps actually buy you

The US ladder is worth reading closely, because two of the jumps are good and one is a trap.

**¥68 → ¥88 (+¥20):** double the disk, +10 Mbps of port speed, double the traffic. CPU and RAM unchanged. This is the cheapest meaningful upgrade on the page — if you're staying on 1 GB of RAM, the 20 GB disk is worth the ¥20 on its own.

**¥88 → ¥158 (+¥70):** the CPU doubles to 2 cores, RAM to 2 GB, disk to 40 GB, port to 80 Mbps, traffic to 4 TB. This is the jump from "toy" to "server". If your site is anything more than a static brochure, this is where the real money starts.

**¥158 → ¥388 (+¥230):** 4 cores, 4 GB, 80 GB, 100 Mbps, 8 TB. Roughly 2.5× the price for 2× the CPU and RAM. Per unit of resource it's worse value than the step below it — but 4 GB is the threshold where WooCommerce stops being frightening, so for a store it's the correct buy.

**¥388 → ¥498 (+¥110, 不限流量 Lite):** and here's the trap. For **more** money you get **fewer** cores (2 instead of 4), **less** RAM (2 GB instead of 4 GB), and a port cut from 100 Mbps to 20 Mbps. The only thing you gain is unmetered traffic. Unless your site genuinely pushes past 8 TB a month — which at 20 Mbps you physically cannot do quickly — the 豪华版 is the better server and the cheaper one. Paying a premium to downgrade your hardware is a bad trade.

**¥498 → ¥1,288 (不限流量 Pro):** 4 cores, 4 GB, 80 GB, 50 Mbps, still unmetered. ¥790/month for the privilege of removing a traffic cap you were probably never going to hit.

One more piece of arithmetic on the annual plan: ¥499/year works out to about ¥41/month, roughly 39% cheaper than the ¥68 monthly 精简版. But the annual box ships with **600 GB of traffic instead of 1,000 GB** and the same 1 core / 1 GB / 10 GB hardware. It's a good deal for a low-traffic site or a staging server. It is not the same product at a discount.

---

## Which plan fits your situation

**A personal blog or content site, under a few thousand visits a month**
→ 基础版, ¥88/month. You get 20 GB of disk, which is the real constraint at this tier. The 10 GB 精简版 will fill up with images faster than you expect.
👉 [Grab the 20 GB starter plan](https://lisahost.com/aff.php?aff=1587)

**A content site with real traffic, ad revenue, or a newsletter list**
→ 进阶版, ¥158/month. Two cores and 2 GB of RAM is where a page cache, a search plugin, an analytics script and an actual visitor load stop fighting each other. This is the cheapest plan I'd put a business on.
👉 [Move up to the 2-core plan](https://lisahost.com/aff.php?aff=1587)

**WooCommerce, a membership site, or an LMS**
→ 豪华版, ¥388/month. The reason is specific: cart, checkout and account pages bypass your page cache, so every order consumes real CPU and a database write. 4 GB of RAM gives MariaDB room to breathe during a sale instead of swapping. 2 GB will work until it doesn't, and it will fail at the worst possible moment.
👉 [Get the 4-core plan built for checkouts](https://lisahost.com/aff.php?aff=1587)

**Several small client sites or a staging copy of a live site**
→ 豪华版, and keep the total count low. How many WordPress installs fit on one VPS has nothing to do with a site counter and everything to do with combined traffic, plugin weight and database load. Four brochure sites on 4 GB is comfortable. Four WooCommerce stores on 4 GB is not.
👉 [Check the multi-site-capable tier](https://lisahost.com/aff.php?aff=1587)

**A test environment, a demo, or a site you're learning on**
→ 特价年付版, ¥499/year. About ¥41/month for a box you can break and rebuild without thinking about it. The 600 GB traffic cap is irrelevant at this scale.
👉 [Start cheap with the annual plan](https://lisahost.com/aff.php?aff=1587)

**You don't want to touch a terminal**
→ Don't buy any of these. LisaHost sells self-managed infrastructure: the server platform is theirs, the WordPress installation, updates, caching, hardening, plugin choices and application-level troubleshooting are yours. If that sentence made you tired, a managed WordPress host is cheaper than the hours you'd spend learning.
👉 [Still want to look at the plans?](https://lisahost.com/aff.php?aff=1587)

---

## The costs that aren't on the plan card

Every self-managed VPS has a second invoice, and it isn't always denominated in money. Before you pay anyone, get written answers to these six questions.

**Backups.** LisaHost's plan pages don't spell out an automatic backup allowance, so confirm it before you migrate anything. Across the VPS market the arrangements vary wildly: one common model bills daily backups at 20% of the server price with a $1 monthly minimum; another bundles a snapshot quota into each tier and still recommends you keep a separate WordPress-level backup with off-server storage and a tested restore. Neither is unreasonable. Assuming backups exist when they don't is how people lose three years of posts.

**Control panel licensing.** Bare KVM plans usually ship without one — you get SSH and that's it. If you want a panel, budget for the licence separately; a cPanel licence alone can run around $23/month, which on the ¥68 plan would more than double your bill. Free alternatives exist and work fine for a single WordPress site.

**Additional IPv4 addresses.** Each LisaHost plan includes one dedicated IPv4, which is all a single WordPress site needs. Extra public IPv4 addresses are a paid add-on almost everywhere — one provider lists them at $3.65/month each, with IPv6 free. Only relevant if you're terminating mail or running multiple SSL endpoints.

**Migration.** On self-managed plans, moving your existing site is normally your job. Some hosts offer it as paid hourly work — one quotes from $8 per 15 minutes, or $28/hour, billed by time used. If you have a large WooCommerce database and no appetite for a manual move, price this in before you compare plan costs.

**Refund windows.** They are not standardised and they are not generous. LisaHost advertises a **48-hour no-questions refund**, which is enough to verify that the network and the IP behave as described, and not much more. Some competitors offer 7 or 30 days; almost all of them exclude domain fees and third-party licence charges from any refund. Read the terms before you click pay, not after.

**Provisioning delays.** Most orders deploy automatically once payment clears. Orders flagged for fraud or security review can sit for days waiting on verification — one host quotes 4–6 business days when that happens. If you're migrating on a deadline, order early enough to absorb a delay.

Payment on LisaHost is straightforward for Chinese buyers: Alipay is accepted and the interface is in Chinese. That's a genuine convenience if your team is in mainland China, and irrelevant if it isn't.

---

## Where LisaHost is the wrong answer

Three honest disqualifications, in order of how often they apply.

**You're buying it for the residential IP.** If your WordPress site is a blog or a store, the dual-ISP residential IP is dead weight. You are paying a premium for an asset that only pays off on TikTok, marketplace accounts and streaming. If you don't need IP reputation, buy a plain VPS and put the difference into RAM.

**Your visitors are mostly outside mainland China.** AS9929 and the Hong Kong CMI/CU2/CN2 routing are engineered for latency from mainland China to the server — useful when your editors log into wp-admin from Shanghai, or when your audience is there. For an audience in Europe or North America, the China-optimised route is a cost with no matching benefit, and a Frankfurt or Ashburn box would serve them better.

**You need serious concurrency.** The top of the standard line-up is 4 cores and 4 GB. That comfortably handles a normal WooCommerce store. It does not handle a flash sale, a viral post with 20,000 simultaneous readers, or a Multisite network with dozens of active sites. If that's your trajectory, plan on horizontal scaling with a load balancer or a CDN doing the heavy lifting — not on buying a bigger box here.

---

## FAQ

**Managed or unmanaged — which is LisaHost?**
Self-managed. LisaHost provides the server platform; you handle WordPress installation, updates, caching, security hardening, plugin selection and application-level troubleshooting.

**How many WordPress sites can I host on one plan?**
As many as the CPU, RAM and storage can cover once you add up their traffic, plugins and database load. There's no site-count limit, which is exactly why it's a bad metric. Two heavy stores will saturate 4 GB before ten brochure sites do.

**Can I run WooCommerce?**
Yes, on 4 cores and 4 GB or more. Size for product count, checkout traffic and background jobs, not for the number of products. A 200-product store with steady orders is harder on the database than a 5,000-product catalogue nobody visits.

**Can I run WordPress Multisite?**
Technically yes on the larger plans. Practically, Multisite multiplies database and PHP worker demand with every subsite, and 4 GB is a low ceiling. If the network is the business, buy more headroom elsewhere.

**Do I need to know Linux?**
Effectively, yes. You can install WordPress from the command line in about ten minutes if you're comfortable with SSH, or use a free control panel if you'd rather click. Either way you own the patching.

**Which control panel should I use?**
For a single WordPress site, a free lightweight panel is plenty. cPanel makes sense if you're hosting multiple sites and want mail, DNS and databases in one interface — but check the licence cost against your plan price first, because on the entry tiers it can exceed the server itself.

**What happens after the 48-hour refund window?**
You're committed. Use the first two days to test what actually matters: install your real plugin set, run a load test on a checkout page if you have one, verify the IP behaves the way the sales page claims, and confirm whether backups are included. Then decide.

---

## The decision

If you came here from a shared host that keeps telling you a plugin is the problem, the fix is real: dedicated CPU, dedicated RAM, and root access to configure caching the way your site actually needs it. LisaHost's US line-up prices that starting at ¥158/month for a configuration that can carry a real site, and ¥388/month for one that can carry a store.

If you came here for the residential IP, buy on that basis and treat the WordPress specs as a bonus. If you came here because you want someone else to handle the server, close this tab and go buy managed hosting — it will cost less than the mistake.

Everything else is arithmetic you can do on the table above.

👉 [Compare LisaHost's current plans and order the one that fits](https://lisahost.com/aff.php?aff=1587)

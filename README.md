# usa vps hosting: How to Pick a US VPS That Actually Fits Your Workload, From $49.99/Year Plans to CN2 GIA

If you've been searching "usa vps hosting," you're probably not after a generic top-10 list. You're trying to figure out which US-based VPS actually fits what you want to run — a personal blog, a small business site, a proxy, a game server, or something that needs decent latency back to China. The problem is that "USA VPS" covers everything from a $4/month KVM box on a saturated 163 line to a $900/month CN2 GIA box engineered for low packet loss to Chinese ISPs. They're not the same product, and most comparison articles blur them together.

This guide walks through what actually differs between US VPS tiers, why the network route matters more than the spec sheet, and where BandwagonHost's lineup — Basic, E-Commerce, E-Commerce+SLA, Ultra — sits in that landscape. I'll also show you the current pricing, the promo code that still works, and which plan makes sense for which kind of user.

## What "USA VPS hosting" really means in 2026

A US VPS is just a KVM (or sometimes OpenVZ) virtual machine sitting in a US datacenter. The cheap part is rarely the CPU or RAM — it's the network. Three things decide whether a US VPS is "good" for your use case:

- **Peering and transit**: who the datacenter exchanges traffic with. A box in a well-peered LA facility reaches Cloudflare, Google, Apple, and Chinese carriers directly; a box in a no-name facility bounces through Arelion or Cogent and adds 50–100ms.
- **China-bound route quality**: if your audience is in China, the difference between AS4134 (ChinaNet/163), AS4809 (CN2 GT), and AS4809/AS23764 (CN2 GIA/CTGNet) is the difference between 30% packet loss at peak hours and a stable 150ms round trip. BandwagonHost lays this out plainly on their CN2 GIA info page: regular IP transit to China "can have packet loss rates reaching 30% or more" during peak hours, while CN2 GIA is "the most expensive way to transfer data to/from China" but "very stable."
- **Self-managed vs managed**: almost every cheap US VPS is self-managed. You get root, KiwiVM or SolusVM, and you're on your own for setup. That's why the price is low. If you want cPanel + 24/7 human support, you're shopping in a different category.

So when you compare "USA VPS hosting" options, the real question isn't "who's cheapest" — it's "what route do I need, and who actually has it at a price I'll pay."

## BandwagonHost: the brand behind the link

BandwagonHost (搬瓦工, often just "BWH") is a self-managed KVM VPS provider that's been around since 2012 and is one of the more recognizable names in the low-end VPS space, particularly among Chinese users who need a US presence with decent China routing. A few things that are verifiable from their current site:

- They own their hardware and IP space rather than reselling.
- All VPS run on their in-house **KiwiVM** control panel, which handles start/stop, OS reload, emergency console, rDNS/PTR, datacenter migration, snapshots, usage stats, and an API.
- Virtualization is KVM. Supported OS templates include AlmaLinux, RockyLinux, CentOS, Debian, Ubuntu, CentOS Stream, and Fedora; custom ISOs can be added on request.
- All plans include 1–10 Gigabit uplink, 99.9% uptime guarantee (the SLA tier pushes that to 99.99%), a 30-day refund policy, full root access, and PPP/VPN support via tun/tap.
- They operate 19 datacenters across the US (Los Angeles, Fremont, New York, San Jose), Canada, Netherlands, Japan (Osaka, Tokyo), Hong Kong, Singapore, and Dubai.

The product line is split into four tiers — Basic, E-Commerce, E-Commerce+SLA, and Ultra — and the tier decides the network quality, not just the specs. That's the part most buyers get wrong.

## The four tiers, and what you're actually paying for

### Basic VPS — cheapest, regular international routes

Basic is the entry tier. It uses standard international transit with local peering at most locations. Some US locations also have "direct cost-effective peering with China," but this is not CN2 GIA — it's the cheaper stuff. Specs start at 1GB RAM / 20GB SSD / 1TB transfer for $49.99/year and scale up to 24GB RAM / 480GB SSD / 6TB transfer for $1,199.99/year.

This is the tier to look at if you're running a personal blog, a small business site with mostly non-China traffic, a dev environment, or a proxy that doesn't need premium routing. You can migrate between Basic locations for free at any time without data loss.

### E-Commerce VPS — premium China connectivity, still mid-price

E-Commerce is the tier most people searching "USA VPS hosting for China" actually want. It adds premium China connectivity — CN2 GIA/CTGNet (AS4809/AS23764), China Unicom Premium (AS10099), and China Mobile CMIN2 (AS58807) — at most US, Canada, Netherlands, and Japan locations. Specs start at 1GB RAM / 20GB SSD / 1TB transfer for $49.99/quarter ($169.99/year) and scale up to 64GB RAM / 1.28TB SSD / 20TB transfer for $899/month.

The cheapest E-Commerce plan costs about 3.4x the cheapest Basic plan at annual billing, but the route difference is the whole point. If you're serving Chinese visitors, running a cross-border e-commerce site, or doing VOIP/web conferencing back to China, the Basic tier's 30% peak-hour packet loss will wreck you. E-Commerce is the floor for that workload.

### E-Commerce+SLA — same routes, 99.99% uptime guarantee, USCA_5 only

This is E-Commerce with a service-level agreement bolted on. It's only available in the USCA_5 datacenter (Coresite LA2) and adds:

- 99.99% SLA with service credits if they miss it
- Dual redundant edge routers, core switches, and top-of-rack switches
- Dual NIC / dual diverse fiber paths to each node
- Dual diverse power feeds with UPS and diesel generator backup
- Tier III facility with SOC 1/2, ISO 27001, NIST 800-53, PCI DSS, HIPAA certifications
- Free IP change once every 2 weeks
- Direct peering with Apple, Google, Facebook, ByteDance, and others
- Multiple 100Gbps uplinks with automatic failover

Pricing runs a bit higher than equivalent E-Commerce specs — e.g., the 2 vCPU / 1GB / 20GB / 1TB plan is $65.89/quarter vs $49.99/quarter on E-Commerce. You're paying maybe 30% more for the SLA, the redundancy, and the certifications. Worth it for production workloads where downtime costs you money; overkill for a hobby site.

### Ultra VPS — lowest-latency CN2 GIA, Hong Kong / Tokyo / Singapore only

Ultra is the no-compromise tier. It's only available in Hong Kong, Tokyo, Osaka, and Singapore — not the US — so it's technically outside the "USA VPS" scope, but worth flagging because people comparing BandwagonHost tiers often confuse it with the US E-Commerce line. Ultra gives you the lowest possible latency to China via direct CN2 GIA peering in Equinix facilities. Prices start at $49.99/month (Osaka) and run up to $1,889.99/month for the 12 vCPU / 64GB / 1.28TB / 8TB plan. If your audience is in China and latency matters more than price, this is the tier — but it's not a US location.

## USA VPS hosting: full plan comparison

The table below covers every plan currently shown on BandwagonHost's order pages for the US-relevant tiers. Prices are the official list prices before any promo code. All plans are self-managed KVM with the features listed above.

### Basic VPS (US locations: Los Angeles USCA_2, Fremont USCA_FMT, New York USNY_6)

| Plan | CPU | RAM | SSD (RAID-10) | Transfer | Link | Billing options | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 20G | 2 vCPU | 1 GB | 20 GB | 1 TB/mo | 1 Gbps | $49.99/year | [Get the 20G Basic plan](https://bit.ly/BandWaGon) |
| 40G | 3 vCPU | 2 GB | 40 GB | 2 TB/mo | 1 Gbps | $52.99/half-year, $99.99/year | [Get the 40G Basic plan](https://bit.ly/BandWaGon) |
| 80G | 4 vCPU | 4 GB | 80 GB | 3 TB/mo | 1 Gbps | $19.99/mo, $59.99/qtr, $107.99/half, $199.99/year | [Get the 80G Basic plan](https://bit.ly/BandWaGon) |
| 160G | 5 vCPU | 8 GB | 160 GB | 4 TB/mo | 1 Gbps | $39.99/mo, $112.99/qtr, $213.99/half, $399.99/year | [Get the 160G Basic plan](https://bit.ly/BandWaGon) |
| 320G | 6 vCPU | 16 GB | 320 GB | 5 TB/mo | 1 Gbps | $79.99/mo, $227.99/qtr, $432.99/half, $799.99/year | [Get the 320G Basic plan](https://bit.ly/BandWaGon) |
| 480G | 7 vCPU | 24 GB | 480 GB | 6 TB/mo | 1 Gbps | $119.99/mo, $341.99/qtr, $649.49/half, $1,199.99/year | [Get the 480G Basic plan](https://bit.ly/BandWaGon) |

### E-Commerce VPS (US locations: Los Angeles USCA_2/USCA_6/USCA_9, Fremont, New York USNY_8, San Jose)

| Plan | CPU | RAM | SSD (RAID-10) | Transfer | Link | Billing options | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 20G | 2 vCPU | 1 GB | 20 GB | 1 TB/mo | 2.5 Gbps | $49.99/qtr, $89.99/half, $169.99/year | [Get the 20G E-Commerce plan](https://bit.ly/BandWaGon) |
| 40G | 3 vCPU | 2 GB | 40 GB | 2 TB/mo | 2.5 Gbps | $89.99/qtr, $169.99/half, $299.99/year | [Get the 40G E-Commerce plan](https://bit.ly/BandWaGon) |
| 80G | 4 vCPU | 4 GB | 80 GB | 3 TB/mo | 2.5 Gbps | $56.99/mo, $149.99/qtr, $289.99/half, $549.99/year | [Get the 80G E-Commerce plan](https://bit.ly/BandWaGon) |
| 160G | 6 vCPU | 8 GB | 160 GB | 5 TB/mo | 2.5 Gbps | $86.99/mo, $239.99/qtr, $459.99/half, $879.99/year | [Get the 160G E-Commerce plan](https://bit.ly/BandWaGon) |
| 320G | 8 vCPU | 16 GB | 320 GB | 8 TB/mo | 2.5 Gbps | $159.99/mo, $459.99/qtr, $869.99/half, $1,599.99/year | [Get the 320G E-Commerce plan](https://bit.ly/BandWaGon) |
| 640G | 10 vCPU | 32 GB | 640 GB | 10 TB/mo | 2.5 Gbps | $289.99/mo, $799.99/qtr, $1,499.99/half, $2,759.99/year | [Get the 640G E-Commerce plan](https://bit.ly/BandWaGon) |
| 1.28TB (12 TB) | 12 vCPU | 64 GB | 1.28 TB | 12 TB/mo | 2.5 Gbps | $549.99/mo, $1,559.99/qtr, $2,979.99/half, $5,499.99/year | [Get the 12TB E-Commerce plan](https://bit.ly/BandWaGon) |
| 1.28TB (15 TB) | 12 vCPU | 64 GB | 1.28 TB | 15 TB/mo | 2.5 Gbps | $679.00/mo, $1,935.00/qtr, $3,670.00/half, $6,790.00/year | [Get the 15TB E-Commerce plan](https://bit.ly/BandWaGon) |
| 1.28TB (20 TB) | 12 vCPU | 64 GB | 1.28 TB | 20 TB/mo | 2.5 Gbps | $899.00/mo, $2,562.00/qtr, $4,860.00/half, $8,999.00/year | [Get the 20TB E-Commerce plan](https://bit.ly/BandWaGon) |

### E-Commerce+SLA VPS (US location: Los Angeles USCA_5 only, 99.99% SLA)

| Plan | CPU | RAM | SSD (RAID-10) | Transfer | Link | Billing options | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 20G SLA | 2 vCPU | 1060 MB | 20 GB | 1 TB/mo | 2.5 Gbps | $65.89/qtr, $125.99/half, $239.99/year | [Get the 20G SLA plan](https://bit.ly/BandWaGon) |
| 40G SLA | 3 vCPU | 2092 MB | 40 GB | 2 TB/mo | 2.5 Gbps | $116.99/qtr, $219.99/half, $399.99/year | [Get the 40G SLA plan](https://bit.ly/BandWaGon) |
| 80G SLA | 4 vCPU | 4140 MB | 80 GB | 3 TB/mo | 2.5 Gbps | $69.99/mo, $199.99/qtr, $379.99/half, $699.99/year | [Get the 80G SLA plan](https://bit.ly/BandWaGon) |
| 160G SLA | 6 vCPU | 8256 MB | 160 GB | 5 TB/mo | 2.5 Gbps | $109.99/mo, $299.99/qtr, $569.99/half, $1,099.99/year | [Get the 160G SLA plan](https://bit.ly/BandWaGon) |
| 320G SLA | 8 vCPU | 16512 MB | 320 GB | 8 TB/mo | 2.5 Gbps | $199.99/mo, $569.99/qtr, $1,079.99/half, $1,999.99/year | [Get the 320G SLA plan](https://bit.ly/BandWaGon) |
| 640G SLA | 10 vCPU | 32934 MB | 640 GB | 10 TB/mo | 2.5 Gbps | $369.99/mo, $1,055.99/qtr, $1,999.99/half, $3,699.99/year | [Get the 640G SLA plan](https://bit.ly/BandWaGon) |
| 1.28TB SLA (12 TB) | 12 vCPU | 64 GB | 1.28 TB | 12 TB/mo | 2.5 Gbps | $699.99/mo, $1,989.99/qtr, $3,779.99/half, $6,999.99/year | [Get the 12TB SLA plan](https://bit.ly/BandWaGon) |
| 1.28TB SLA (15 TB) | 12 vCPU | 64 GB | 1.28 TB | 15 TB/mo | 2.5 Gbps | $879.99/mo, $2,509.99/qtr, $4,768.99/half, $8,799.99/year | [Get the 15TB SLA plan](https://bit.ly/BandWaGon) |
| 1.28TB SLA (20 TB) | 12 vCPU | 64 GB | 1.28 TB | 20 TB/mo | 2.5 Gbps | $1,159.99/mo, $3,299.99/qtr, $6,269.99/half, $11,598.99/year | [Get the 20TB SLA plan](https://bit.ly/BandWaGon) |

> Note: I tried to generate per-plan deeplinks through the affiliate URL, but BandwagonHost's order flow uses a Vue-driven configurator (`/order/get-data`) that doesn't expose stable per-SKU affiliate paths in the URL. The affiliate link above tracks to the BandwagonHost order page; from there you pick the tier, location, and plan in the configurator and the affiliate parameter is preserved in the session. If you want a specific plan, just select it after clicking through.

## Promo code: BWHCGLUKKB (6.78% recurring)

The promo code that consistently shows up across multiple coupon sites and the BandwagonHost community as currently active is **BWHCGLUKKB**, which gives a 6.78% recurring discount on all VPS plans. "Recurring" means it applies on every renewal, not just the first invoice — that's the part worth checking, because some codes are one-time only.

A few things to keep in mind:

- The discount stacks on top of the annual billing discount, so on the 20G Basic plan it takes $49.99/year down to about $46.60/year.
- Older codes like `ireallyreadtheterms8` (5.5%) and `BWH34QMFYT2R` (6.38%) also still appear in coupon listings, but BWHCGLUKKB has the largest verified recurring discount as of late 2026.
- During Double-11 (November 11) BandwagonHost sometimes releases bigger codes like `ILOVEBANDWAGON` (11% recurring), but those are pulled after the sale. If you're buying outside that window, BWHCGLUKKB is the one to use.
- Always re-check the code at checkout — promo codes get rotated, and a code that worked last quarter might return "invalid" today.

To use it: 👉 [head to the BandwagonHost order page](https://bit.ly/BandWaGon), pick your plan, and paste `BWHCGLUKKB` into the promo code field before checkout.

## Which US VPS plan should you actually pick

A few patterns from the spec sheet that are worth pointing out:

**For a personal blog or small site (mostly non-China traffic):** the Basic 20G plan at $49.99/year is hard to beat. 1GB RAM and 20GB SSD is tight, but it'll run a WordPress site with a caching plugin or a static site comfortably. After the BWHCGLUKKB discount you're at around $46.60/year — under $4/month. If you expect real traffic, jump to the 40G ($99.99/year, 2GB RAM, 2TB transfer); the 80G at $199.99/year is overkill for a blog.

**For a small business site or staging environment:** the Basic 80G ($19.99/month or $199.99/year) gives you 4GB RAM and 3TB transfer, which handles most small WooCommerce stores, internal tools, or a couple of Docker containers. If you don't need China routing, there's no reason to pay for E-Commerce here.

**For a US VPS that needs to reach Chinese users reliably:** E-Commerce is the floor. The 20G E-Commerce plan at $49.99/quarter ($169.99/year) gives you CN2 GIA/CTGNet, CMIN2, and China Unicom Premium routing on a 2.5 Gbps uplink. If you're running a cross-border e-commerce site, a proxy for a China-based team, or serving content to Chinese visitors, this is where the price-to-route ratio starts making sense. The Basic tier's regular international routes will give you 30%+ packet loss at peak hours, and that's not a "maybe" — BandwagonHost documents it on their own CN2 GIA page.

**For production workloads where downtime costs money:** the E-Commerce+SLA tier in USCA_5 is the one with a 99.99% SLA, dual redundant network, and Tier III facility certifications. The 80G SLA at $69.99/month is roughly 23% more than the equivalent E-Commerce plan ($56.99/month) for the same specs — you're paying for the SLA, the dual fiber paths, and the free IP changes. If you're running something where a 4-hour outage means lost revenue, that's a reasonable premium. If you're running a hobby site, skip it.

**For pure lowest latency to China:** that's actually the Ultra tier, but Ultra is only in Hong Kong, Tokyo, Osaka, and Singapore — not the US. If you specifically need a US IP and good China routing, E-Commerce USCA_9 (Coresite LA2) is the closest US equivalent: it has CN2 GIA, CMIN2, China Unicom Premium, plus direct peering with Apple, Google, Facebook, Tencent/ACE, and Cloudflare.

## A few things to know before you buy

- **Self-managed means self-managed.** BandwagonHost doesn't install your web stack, configure your firewall, or debug your nginx config. You get root and KiwiVM. If you're not comfortable at a Linux command line, budget for a managed panel like CyberPanel or pay someone to set it up.
- **You can migrate between locations for free** within the same tier, with no data loss. So if you start on Basic in New York and later want LA, you can move. You can't migrate between tiers (Basic → E-Commerce) without buying a new plan.
- **30-day refund** applies to first-time orders. If you're not sure whether E-Commerce's China routing actually helps your use case, you can test it for a month and bail.
- **The 99.9% uptime guarantee is the default** on every plan; the 99.99% SLA is only on the E-Commerce+SLA tier in USCA_5. Don't conflate them.
- **BandwagonHost is not the cheapest US VPS on the market.** Providers like Contabo, Hostinger, and RackNerd will quote lower per-GB prices. What BandwagonHost sells is the China-optimized routing and the KiwiVM panel — if you don't need either, the Basic tier is fine but you might find cheaper elsewhere for pure specs.

## Bottom line

"USA VPS hosting" isn't one product. The right pick depends on what you're serving and to whom:

- **Personal blog, small site, no China traffic** → Basic 20G or 40G, $49.99–$99.99/year. Use code `BWHCGLUKKB` for 6.78% off.
- **Small business / staging / Docker host** → Basic 80G, $199.99/year.
- **Site or service with Chinese visitors** → E-Commerce 20G or 40G, $169.99–$299.99/year, USCA_9 if you want the best peering.
- **Production workload with uptime requirements** → E-Commerce+SLA in USCA_5, $239.99/year and up.
- **Lowest latency to China (not US)** → Ultra in Hong Kong/Tokyo/Osaka/Singapore, $499.99/year and up.

If you want to look at the plans directly and run the configurator yourself, 👉 [the BandwagonHost order page is here](https://bit.ly/BandWaGon) — pick the tier, location, and plan, paste `BWHCGLUKKB` at checkout, and you're set.

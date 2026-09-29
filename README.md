# dmit review: What the Current VPS Pricing, Routing and Real-World Feedback Actually Say

Searching for **dmit review** usually means one thing: you want to know whether DMIT is actually worth paying for, not another page that repeats “premium VPS” without showing the numbers.

As of September 26, 2026, DMIT’s current catalog is centered on cloud VPS instances in **Los Angeles, Hong Kong, and Tokyo**, with Premium, Eyeball, and Tier 1 network profiles depending on location. The company also offers Bare Metal, IP Transit, and Colocation, but the cloud-instance lineup is where most of the public pricing and third-party discussion is concentrated.

The short version of this review is fairly straightforward: **DMIT’s main differentiator is its network design and the amount of choice it gives you over routing, not bargain-basement pricing**. Premium routes are aimed at China/APAC-sensitive workloads; Eyeball is positioned between Premium and ordinary Tier 1 connectivity; Tier 1 is the cost-oriented option for global traffic that does not require China-specific routing.

The interesting part is that the trade-offs are now much easier to see in the live catalog.

## What DMIT is actually selling

DMIT describes its cloud instances as KVM virtual machines with AMD EPYC processors, SSD storage, full root access, and free instant setup. Its cloud page also advertises snapshots, automated backups, and SSH-key authentication.

The hardware is split into several generations:

* **AN5** uses AMD EPYC 9005-series processors, Zen 5 architecture, DDR5 memory, and NVMe Gen5 storage.
* **AN4** uses AMD EPYC 9004-series processors, Zen 4 architecture.
* **AS3** uses AMD EPYC 7003-series processors, Zen 3 architecture.

DMIT positions AN5 as its performance-oriented platform, AN4 as the balanced option, and AS3 as the lower-cost generation.

That distinction matters because two plans with the same number of vCores and RAM can have noticeably different prices depending on the hardware generation and network profile.

So a DMIT comparison should not stop at “4 vCPU / 4 GB RAM.” You need to look at **location + network + hardware + traffic allowance + port speed**.

## Premium vs Eyeball vs Tier 1: this is the real DMIT decision

DMIT's own descriptions make the three network profiles fairly clear.

### Premium Network

Premium combines Tier 1 transit with premium transit partners and China Telecom CN2 GIA. DMIT describes it as the network profile intended for China Mainland and wider APAC workloads where route quality and packet loss matter more than minimizing the monthly bill.

Typical use cases include cross-border applications, e-commerce, streaming, interactive services, and game workloads where latency is important.

DMIT currently quotes roughly **15 ms reference latency from Hong Kong to China Mainland** and under **0.1% reference packet loss**, although the company explicitly notes that real results vary by route, access network, and time of day. Tokyo's corresponding published reference is around 28–30 ms. These are reference measurements, not guarantees for every user.

### Eyeball Network

Eyeball uses Tier 1 transit plus “reasonable-effort” China routing through Chinese eyeball networks such as CMI/CMIN2, depending on the location.

The practical positioning is simple: you get more China-aware routing than a plain Tier 1 profile, but without the same Premium routing design. DMIT explicitly describes it as a cost-and-reach compromise for mixed China/global websites, APIs, SaaS backends, development servers, and moderate China traffic.

There is one particularly important caveat in Hong Kong: **DMIT currently labels HKG Eyeball as Beta** and says the routing is still being tuned. It also says the profile is not recommended for production workloads that require high stability. That is a meaningful limitation, not marketing fine print you can safely ignore.

### Tier 1 Network

Tier 1 removes the China-specific routing emphasis and concentrates on general global connectivity, APAC, North America, and high bandwidth.

That makes the cheapest Tier 1 plans considerably easier to understand. You are primarily paying for compute, transfer, and general network connectivity rather than specialized China routing. DMIT specifically lists backups, archives, monitoring, CI/CD, DevOps, VPN/relay nodes, and cost-sensitive compute among the intended workloads.

This is also where some of DMIT's price points become much easier to justify: a low-cost Tier 1 VPS can carry a lot of traffic without paying Premium-network pricing.

## Current DMIT pricing: the full public catalog is much bigger than the usual review tables

One reason many DMIT reviews feel incomplete is that the official pricing page exposes a large matrix rather than a simple “Basic / Pro / Business” structure.

The table below consolidates the **currently surfaced public configurations on DMIT's pricing pages**, including stock status where the page explicitly shows it. DMIT itself warns that displayed prices may lag behind adjustments, so the checkout price should still be treated as the final authority.

All prices below are in **USD**. Unless explicitly marked annual, the billing period is monthly.

### Los Angeles

| Family | Current public configurations | Purchase |
| --- | --- | --- |
| **LAX Premium · AS3** | TINY — 1 vCore / 2 GB / 20 GB / 1,000 GB / 1 Gbps — **$10.90**; Pocket — 2 / 2 GB / 40 GB / 1,500 GB / 4 Gbps — **$16.90**; STARTER — 2 / 2 GB / 80 GB / 3,000 GB / 10 Gbps — **$34.90**; MINI — 4 / 4 GB / 80 GB / 5,000 GB / 10 Gbps — **$62.90**; MICRO — 4 / 4 GB / 160 GB / 7,000 GB / 10 Gbps — **$87.90**; MEDIUM — 6 / 8 GB / 160 GB / 15,000 GB / 10 Gbps — **$199.90**. | [ View LAX Premium plans](https://bit.ly/DmiT) |
| **LAX Premium · AN4** | MINI — 4 / 4 GB / 80 GB / 5,000 GB / 10 Gbps — **$72.90**, out of stock; MICRO — 4 / 4 GB / 160 GB / 7,000 GB — **$102.90**, out of stock; MEDIUM — 6 / 8 GB / 160 GB / 15,000 GB — **$239.90**, out of stock; LARGE — 8 / 16 GB / 320 GB / 25,000 GB — **$459.90**, out of stock; GIANT — 12 / 24 GB / 640 GB / 50,000 GB — **$929.90**, out of stock. | [ Check availability](https://bit.ly/DmiT) |
| **LAX Premium · AN5** | MINI — 4 / 4 GB / 80 GB / 10,000 GB / 10 Gbps — **$79.90**; MICRO — 4 / 4 GB / 160 GB / 14,000 GB — **$110.90**; MEDIUM — 6 / 8 GB / 160 GB / 30,000 GB — **$289.90**; LARGE — 8 / 16 GB / 320 GB / 50,000 GB — **$499.90**; GIANT — 12 / 24 GB / 640 GB / 100,000 GB — **$1,009.90**. | [ Check AN5 Premium](https://bit.ly/DmiT) |
| **LAX Eyeball · AS3** | TINY — 1 / 2 GB / 20 GB / 1,500 GB / 2 Gbps — **$10.90**; Pocket — 2 / 2 GB / 40 GB / 3,000 GB / 4 Gbps — **$16.90**; STARTER — 2 / 2 GB / 80 GB / 5,000 GB / 10 Gbps — **$34.90**; MINI — 4 / 4 GB / 80 GB / 10,000 GB / 10 Gbps — **$62.90**; MICRO — 4 / 4 GB / 160 GB / 14,000 GB / 10 Gbps — **$87.90**; MEDIUM — 6 / 8 GB / 160 GB / 30,000 GB / 10 Gbps — **$199.90**. | [ View LAX Eyeball](https://bit.ly/DmiT) |
| **LAX Eyeball · AN4** | MINI — 4 / 4 GB / 80 GB / 10,000 GB / 10 Gbps — **$72.90**, out of stock; MICRO — 4 / 4 GB / 160 GB / 14,000 GB — **$102.90**, out of stock; MEDIUM — 6 / 8 GB / 160 GB / 30,000 GB — **$239.90**, out of stock; LARGE — 8 / 16 GB / 320 GB / 50,000 GB — **$459.90**, out of stock; GIANT — 12 / 24 GB / 640 GB / 100,000 GB — **$929.90**, out of stock. | [ Check stock](https://bit.ly/DmiT) |
| **LAX Eyeball · AN5** | MINI — 4 / 4 GB / 80 GB / 10,000 GB / 10 Gbps — **$79.90**; MICRO — 4 / 4 GB / 160 GB / 14,000 GB — **$110.90**; MEDIUM — 6 / 8 GB / 160 GB / 30,000 GB — **$289.90**; LARGE — 8 / 16 GB / 320 GB / 50,000 GB — **$499.90**; GIANT — 12 / 24 GB / 640 GB / 100,000 GB — **$1,009.90**. | [ View AN5 Eyeball](https://bit.ly/DmiT) |
| **LAX Tier 1 · AN5 Volume** | V2C2G — 2 / 2 GB / 40 GB / 5,000 GB max IN/OUT / 10 Gbps — **$14.90**; V2C4G — 2 / 4 GB / 80 GB / 10,000 GB — **$23.90**; V4C4G — 4 / 4 GB / 120 GB / 20,000 GB — **$36.90**; V4C8G — 4 / 8 GB / 160 GB / 40,000 GB — **$52.90**; V8C16G — 8 / 16 GB / 240 GB / 80,000 GB — **$119.90**; V12C24G — 12 / 24 GB / 320 GB / 160,000 GB — **$199.90**. | [ View volume plans](https://bit.ly/DmiT) |
| **LAX Tier 1 · AN5 General** | G2C4G — 2 / 4 GB / 80 GB / 4,000 GB max IN/OUT / 10 Gbps — **$16.90**; G4C8G — 4 / 8 GB / 160 GB / 8,000 GB — **$36.90**; G8C16G — 8 / 16 GB / 320 GB / 12,000 GB — **$79.90**; G12C24G — 12 / 24 GB / 480 GB / **240,000 GB as displayed** — **$119.90**; G16C32G — 16 / 32 GB / 640 GB / **320,000 GB as displayed** — **$199.90**. The last two transfer figures are reproduced as currently displayed rather than recalculated or corrected. | [ View general plans](https://bit.ly/DmiT) |
| **LAX Tier 1 · AS3** | WEE — 1 / 1 GB / 20 GB / 1,000 GB max IN/OUT — **$36.90 annually**; TINY — 1 / 1 GB / 20 GB / 2,000 GB — **$6.90/month**; STARTER — 2 / 2 GB / 40 GB / 4,000 GB — **$12.90**; MINI — 2 / 4 GB / 80 GB / 8,000 GB — **$21.90**; MICRO — 4 / 4 GB / 120 GB / 16,000 GB — **$32.90**. | [ View LAX Tier 1](https://bit.ly/DmiT) |

For the LAX catalog, there is one additional operational warning worth keeping visible: **DMIT currently says the LAX AS3 series is still being built out and optimized, with potentially reduced disk performance and a lower SLA than its mature platforms**.

### Hong Kong

| Family | Current public configurations | Purchase |
| --- | --- | --- |
| **HKG Premium · AN5** | MINI — 4 / 4 GB / 80 GB / 1,500 GB / 1 Gbps — **$149.90**; MICRO — 4 / 4 GB / 160 GB / 2,000 GB — **$199.90**; MEDIUM — 6 / 8 GB / 160 GB / 2,500 GB — **$279.90**; LARGE — 8 / 16 GB / 320 GB / 3,000 GB — **$359.90**; GIANT — 12 / 24 GB / 640 GB / 6,000 GB — **$759.90**. | [ View HKG Premium](https://bit.ly/DmiT) |
| **HKG Eyeball · AN5** | TINY — 1 / 1 GB / 20 GB / 500 GB / 1 Gbps — **$39.90**; STARTER — 1 / 2 GB / 40 GB / 1,000 GB — **$79.90**; MINI — 2 / 4 GB / 60 GB / 1,500 GB — **$126.90**; MICRO — 4 / 4 GB / 80 GB / 2,000 GB — **$179.90**; MEDIUM — 4 / 8 GB / 160 GB / 2,500 GB — **$239.90**. | [ View HKG Eyeball](https://bit.ly/DmiT) |
| **HKG Premium · AS3** | MINI — 4 / 4 GB / 80 GB / 2,200 GB / 1 Gbps — **$149.90**; MICRO — 4 / 4 GB / 160 GB / 3,000 GB — **$199.90**; MEDIUM — 6 / 8 GB / 160 GB / 4,000 GB — **$279.90**; LARGE — 8 / 16 GB / 320 GB / 4,500 GB — **$359.90**; GIANT — 12 / 24 GB / 640 GB / 9,000 GB — **$759.90**. | [ View AS3 Premium](https://bit.ly/DmiT) |
| **HKG Eyeball · AS3** | TINY — 1 / 1 GB / 20 GB / 800 GB / 1 Gbps — **$39.90**; STARTER — 1 / 2 GB / 40 GB / 1,500 GB — **$79.90**; MINI — 2 / 4 GB / 60 GB / 2,200 GB — **$126.90**; MICRO — 4 / 4 GB / 80 GB / 3,000 GB — **$179.90**; MEDIUM — 4 / 8 GB / 160 GB / 4,000 GB — **$239.90**. | [ View AS3 Eyeball](https://bit.ly/DmiT) |
| **HKG Tier 1 · AS3** | WEE — 1 / 1 GB / 20 GB / 1,000 GB max IN/OUT — **$36.90 annually**; TINY — 1 / 1 GB / 20 GB / 2,000 GB — **$6.90/month**; STARTER — 1 / 2 GB / 40 GB / 4,000 GB — **$12.90**; MINI — 2 / 2 GB / 60 GB / 8,000 GB — **$21.90**; MICRO — 4 / 4 GB / 80 GB / 16,000 GB — **$32.90**; MEDIUM — 4 / 8 GB / 160 GB / 32,000 GB — **$49.90**; LARGE — 8 / 16 GB / 320 GB / 64,000 GB — **$99.90**; GIANT — 8 / 24 GB / 640 GB / 128,000 GB — **$199.90**. | [ View HKG Tier 1](https://bit.ly/DmiT) |

The Hong Kong catalog is particularly important to read carefully because DMIT currently offers **both AN5 and AS3 hardware**, while the **Eyeball profile is explicitly in Beta**. The company says the HKG node uses Equinix HK2 and quotes roughly 15 ms reference latency to China Mainland from Hong Kong, but also warns that actual performance varies by access network and route.

For some representative products, a current third-party catalog has documented product IDs such as HKG AS3 Tier 1 TINY **PID 198**, HKG AS3 Tier 1 STARTER **PID 199**, HKG AS3 Eyeball TINYv2 **PID 210**, HKG AS3 Eyeball STARTERv2 **PID 211**, and HKG AS3 Premium STARTER **PID 266**.

That lets you use a more specific AFF link for those products:

[👉 HKG Tier 1 TINY](https://www.dmit.io/aff.php?aff=18446&pid=198) · [👉 HKG Tier 1 STARTER](https://www.dmit.io/aff.php?aff=18446&pid=199) · [👉 HKG Eyeball TINY](https://www.dmit.io/aff.php?aff=18446&pid=210) · [👉 HKG Eyeball STARTER](https://www.dmit.io/aff.php?aff=18446&pid=211) · [👉 HKG Premium STARTER](https://www.dmit.io/aff.php?aff=18446&pid=266)

### Tokyo

| Family | Current public configurations | Purchase |
| --- | --- | --- |
| **TYO Premium · AS3** | TINY — 1 / 1 GB / 20 GB / 500 GB / 1 Gbps — **$21.90**; STARTER — 1 / 2 GB / 40 GB / 1,000 GB — **$45.90**; MINI — 2 / 4 GB / 60 GB / 2,000 GB — **$89.90**; MICRO — 4 / 4 GB / 80 GB / 4,000 GB — **$189.90**; MEDIUM — 4 / 8 GB / 160 GB / 6,000 GB — **$320.90**; LARGE — 8 / 16 GB / 320 GB / 8,000 GB — **$429.90**; GIANT — 8 / 24 GB / 640 GB / 15,000 GB — **$829.90**. | [ View Tokyo Premium](https://bit.ly/DmiT) |
| **TYO Tier 1 · AS3** | WEE — 1 / 1 GB / 20 GB / 1,000 GB max IN/OUT — **$36.90 annually**; TINY — 1 / 1 GB / 20 GB / 2,000 GB — **$6.90/month**; STARTER — 1 / 2 GB / 40 GB / 4,000 GB — **$12.90**; MINI — 2 / 2 GB / 60 GB / 8,000 GB — **$21.90**; MICRO — 4 / 4 GB / 80 GB / 16,000 GB — **$32.90**; MEDIUM — 4 / 8 GB / 160 GB / 32,000 GB — **$49.90**; LARGE — 8 / 16 GB / 320 GB / 64,000 GB — **$99.90**; GIANT — 8 / 24 GB / 640 GB / 128,000 GB — **$199.90**. | [ View Tokyo Tier 1](https://bit.ly/DmiT) |

Representative current product IDs are also available for several Tokyo products: TYO Tier 1 TINY **PID 131**, TYO Tier 1 STARTER **PID 132**, TYO Premium TINY **PID 138**, and TYO Premium STARTER **PID 139**.

[👉 Tokyo Tier 1 TINY](https://www.dmit.io/aff.php?aff=18446&pid=131) · [👉 Tokyo Tier 1 STARTER](https://www.dmit.io/aff.php?aff=18446&pid=132) · [👉 Tokyo Premium TINY](https://www.dmit.io/aff.php?aff=18446&pid=138) · [👉 Tokyo Premium STARTER](https://www.dmit.io/aff.php?aff=18446&pid=139)

The complete public catalog is therefore less like a traditional hosting-provider price sheet and more like a matrix. That is useful once you understand it, but it also means that choosing a plan solely because the headline price looks low can lead you into the wrong network profile.

## What stands out in the numbers

The cheapest headline price I found is **$6.90/month**, appearing on the AS3 Tier 1 TINY configurations in Hong Kong and Tokyo. There is also a **$6.90/month LAX AS3 Tier 1 TINY**, but the exact LAX catalog context and traffic rules need to be checked at checkout because the pricing page has several LAX Tier 1 generations and configurations.

At the other end, the LAX AN5 Premium GIANT currently displays at **$1,009.90/month**, with 12 vCores, 24 GB RAM, 640 GB SSD, 100,000 GB transfer, and a 10 Gbps port.

That tells you something important about DMIT's positioning: there is no single “DMIT price level.” The cheapest products and the high-end Premium products are solving very different networking problems.

Another noticeable detail is that **AS3 can be dramatically cheaper than AN5 at the same location/network family**, while providing different transfer levels and a different CPU generation. Whether that price gap matters depends much more on the workload than on the product-generation label itself.

## What current reviews and user feedback say

This is where the picture becomes more mixed.

The positive feedback tends to concentrate on routing. A Reddit discussion from October 2025 includes a user reporting good experiences with DMIT and another provider from China, specifically calling out DMIT's performance from China Mobile connections and the availability of looking-glass tools for checking latency and routes before deployment. That is useful anecdotal evidence, but it is still one discussion rather than a statistically meaningful customer survey.

Recent third-party review pages also tend to focus on DMIT's China/APAC routing as the main reason to pay its prices. That matches DMIT's own product positioning, although many of these reviews are affiliate-oriented and should be read as product summaries rather than independent benchmark reports.

The negative side is harder to ignore, but it is also smaller in sample size.

Trustpilot currently shows **only four reviews** for DMIT and a **2.6/5 TrustScore**. Three reviews were posted in the previous 12 months on the page's current crawl. Complaints include refund disputes, outages, and support-response issues. Because the total sample is so small, I would treat the rating as a signal to investigate rather than as a reliable measurement of the entire customer base. Trustpilot itself warns that the reviews may not be representative.

There is also a recent LowEndTalk thread concerning a DMIT abuse/security warning involving a user's publicly exposed services. The thread itself does not establish that DMIT has a systemic security problem; the original poster explicitly said they had no evidence their VPS had been compromised and was asking whether the event was isolated or widespread. That makes it a useful example of a support/security interaction to be aware of, not proof of a general failure.

So the external review picture is better described as **positive network-specific anecdotes plus some serious support/refund complaints, with too little high-quality data to claim a universal customer consensus**.

## Refund policy: one of the details worth reading before paying

DMIT's current refund documentation is unusually specific.

For a new service, the company says a **full refund is available within 3 days provided VM transfer usage does not exceed 30 GB** and other refund conditions are satisfied. It also provides a **partial refund within 30 days**, calculated against the remaining value. Payment-gateway transaction fees are deducted.

The refund policy also lists situations where a payment-gateway refund is not available, including some DDoS-related cases, IP-geolocation situations, abuse-related losses, and successful renewal invoices.

That makes the first few days more important than they might be with a consumer SaaS subscription. A sensible evaluation window is not just “does SSH work?” but:

1. Check latency and packet loss from the actual networks you care about.
2. Check routing at different times of day.
3. Test the storage workload you intend to run.
4. Verify IPv4 reachability from the places that matter.
5. Watch transfer consumption carefully during the refund window.

DMIT's own beginner guidance similarly recommends testing routes from your real carrier rather than assuming that a published reference latency is your final result.

## There are also resource-use restrictions

DMIT's current Acceptable Use Policy gives the provider the ability to limit CPU performance when abnormal or excessive CPU consumption affects node stability. It also reserves the right to restrict VM internet ports under certain circumstances and can suspend or terminate service for AUP violations.

That is not unusual for a managed infrastructure provider, but it matters if your project involves unusual traffic patterns, large public proxy deployments, automated scraping, mail delivery, or software that might generate abuse complaints.

A cheap VPS is only cheap if the intended workload actually fits the provider's operating rules.

## What about current discount codes?

This is one area where I would be careful.

I found several third-party coupon sites claiming active 2026 DMIT discounts, including recurring discounts for certain LAX, HKG, and Tokyo products. However, I did **not** find a current 2026 promotion code published and independently verifiable on DMIT's own current pricing material during this review. The official promotional page that surfaced prominently was the **2025 Christmas campaign**, which is clearly not a current September 2026 promotion.

That means I would not treat a coupon listed on a generic coupon site as confirmed simply because the page says “verified.”

For an actual purchase, the safer approach is to check the checkout page and compare the resulting recurring price against the public catalog.

[👉 Check the current DMIT catalog](https://bit.ly/DmiT)

## Which DMIT configuration makes sense for which workload?

The answer becomes easier once the network profile is treated as a first-class choice.

For a website, API, SaaS service, or cross-border application where China Mainland performance is a core requirement, **Premium is the most directly aligned network profile according to DMIT's own documentation**. That does not mean every Premium VM will produce identical results from every ISP; route quality is still location- and path-dependent.

For mixed China/global traffic where some optimization is useful but Premium pricing is harder to justify, **Eyeball is the middle ground**. In Hong Kong, however, its current Beta status makes the caveat more important for production workloads.

For backups, CI/CD, monitoring, internal tools, large transfer jobs, and ordinary global connectivity, **Tier 1 is the cleaner fit on paper** because DMIT explicitly positions it for these workloads and the entry-level prices are much lower.

Hardware choice is a separate question. AN5 gives you the newest published platform, while AS3 is materially cheaper in many configurations. For a small website or light Docker stack, spending substantially more purely for a newer CPU generation may not change the user-visible result nearly as much as choosing the appropriate network profile.

## A practical buying strategy

The easiest way to avoid paying for a feature you do not need is to decide these four things before opening the order page:

**Where are your users?**
Los Angeles, Hong Kong, and Tokyo are not interchangeable. Geography affects latency before you even look at CPU.

**Does China-specific routing matter?**
If it does, start with Premium and compare Eyeball only when the workload can tolerate best-effort routing. If it does not, Tier 1 deserves serious consideration.

**How much transfer do you really need?**
DMIT's Tier 1 catalog can provide dramatically more transfer per dollar than its Premium products.

**Do you need the newest hardware?**
AN5 is the flagship platform, but AS3 prices can be considerably lower. The right choice depends on CPU sensitivity, not on the generation number alone.

The official cloud page also says every plan includes free instant setup and full root access, while snapshots and automated backups are available as part of the cloud tooling.

## Is DMIT worth considering?

Based on the current information, the most defensible conclusion is not “DMIT is cheap” or “DMIT is expensive.”

It is **specialized**.

If you need ordinary US or international VPS hosting and have no reason to care about China/APAC routing, many of the features that distinguish DMIT's Premium network are simply not central to your use case. Tier 1 plans make more sense in that situation, but DMIT is still competing on infrastructure rather than being the cheapest possible VPS seller.

If your workload crosses the Pacific, especially toward China Mainland and APAC, DMIT becomes much more interesting because the company lets you choose a routing strategy rather than forcing every workload onto the same generic network. That design is supported by its Los Angeles, Hong Kong, and Tokyo infrastructure descriptions and by the current plan matrix.

The main caution is support and operational risk. The current public review sample is sparse and mixed, and the Trustpilot complaints about refunds and support are specific enough that they should not simply be brushed aside.

In other words, the strongest reason to consider DMIT is **network fit**. The strongest reason to slow down before purchasing is **price plus the need to validate the exact route, stock, and support expectations for your particular workload**.

For a first purchase, using the refund window as an actual test period is more useful than trusting any generic “DMIT review” score.

[👉 Check current DMIT plans and availability](https://bit.ly/DmiT)

## FAQ

### Is DMIT a VPS provider?

Yes. DMIT offers KVM cloud instances alongside Bare Metal, IP Transit, and Colocation services. Its current cloud infrastructure is deployed in Los Angeles, Hong Kong, and Tokyo.

### Does DMIT use AMD EPYC processors?

Yes. The current product documentation lists AMD EPYC 9005-series processors for AN5, AMD EPYC 9004-series processors for AN4, and AMD EPYC 7003-series processors for AS3.

### Does DMIT offer CN2 GIA?

DMIT says its Premium Network uses China Telecom CN2 GIA and positions that profile for China Mainland and APAC-sensitive workloads.

### Is DMIT good for China access?

That depends on the location, carrier, network profile, and time of day. DMIT specifically designs Premium and Eyeball profiles around China-aware routing, while Tier 1 does not include China-specific routing enhancements. The company also recommends testing actual routes because reference figures are not guarantees of every user's final connection.

### Does DMIT have a refund policy?

Yes. DMIT currently states that qualifying new services can receive a full refund within 3 days when usage stays within 30 GB, with partial refunds available within 30 days under its rules. Transaction fees may be deducted.

### Which DMIT plan is cheapest?

The current public pricing includes **$6.90/month** entry-level Tier 1 configurations in several locations, plus a $36.90 annual WEE option in some catalogs. Exact availability can change, so the checkout page matters.

### Are DMIT reviews reliable?

Individual reviews can be useful for identifying specific issues such as routing quality, outages, or support interactions, but the total volume of independent review data is limited. Trustpilot currently shows only four reviews, so its 2.6/5 score should not be treated as a statistically representative customer rating.

### Does DMIT offer a 2026 coupon?

Third-party coupon pages currently claim various discounts, but I did not find a current September 2026 code on DMIT's own site that I could independently verify. Treat third-party codes as unconfirmed until the checkout page actually applies them.

# NorthPeak Electronics: The Hidden Revenue Leaks
### Strategic Sales Funnel & Traffic Analysis (Jan 2024 to Dec 2025)

---

## Client Background

Over the past two years, **NorthPeak Electronics** has established a formidable presence as a premier D2C retailer in consumer audio, wearables, and computing. We have seen incredible momentum. But as our traffic scales, top-line growth is beginning to mask critical friction points in our customer journey.

Between **Jan 2024 and Dec 2025**, we successfully served **59K users** and processed **84.41K purchases**, driving **$22.73M** in gross revenue. However, the C-Suite asked a critical question: *Where are we leaving money on the table?*

Reporting directly to the **Chief Commercial Officer**, I initiated this deep-dive analysis (which also doubles as a comprehensive **portfolio case study** of our internal analytics capabilities) to empower our **VP Product** and **Head of Growth**. The goal? Move beyond vanity metrics, diagnose our exact funnel leaks, and identify the highest-impact levers we can pull today.

### Our Northstar Diagnostic Pillars

- **Funnel Health** - Tracking the exact moments our customers abandon us across browse, cart, checkout, payment, and purchase.
- **Channel Performance** - Cutting through attribution noise to see which acquisition sources actually pay the bills.
- **Geographic Concentration** - Mapping our global revenue dependence to prioritize targeted localization.
- **Product Mix** - Flagging the concentration risks in our catalog and spotlighting our true anchor products.
- **Retention Signals** - Sizing up the lifetime value gap between first-time buyers and our loyal repeat customers.

---

## Executive Summary
### E-commerce Performance (Jan 2024 to Dec 2025)

1. **Healthy Top Funnel, High Intent Volume:**
   - Our marketing is working. Users generated **515K page views** and **187.6K add to carts**, yielding a highly competitive **36.4%** view-to-cart rate.
   - Our overall view-to-purchase conversion sits at a sturdy **16.4%**, bolstered by a very committed mid-funnel audience.

2. **The Bleeding Edge: Late Checkout Leaks:**
   - Here is the critical flaw: after users take the time to add their payment info, conversion to purchase is only **70.2%**. We are losing about **30%** of our highest-intent sessions at the finish line.
   - The financial impact is massive. Improving this payment-to-purchase step by just **5 points** (70% to 75%) translates to roughly **+6K incremental purchases** at our current traffic volume.

3. **Our Growth Engine: Organic and Email Lead the Charge:**
   - **Google organic** is our absolute powerhouse, driving roughly **36%** of all purchases. It is followed closely by **Bing organic**, **Direct**, and **Email**.
   - This mix proves we have a resilient brand. The playbook is clear: build a moat around our SEO, and deploy aggressive lifecycle email campaigns to drive repeat buying.

4. **The Concentration Risk: UK and Top Products Dominate:**
   - We are heavily reliant on the **United Kingdom**, which generates about **$10.21M** in revenue. Roughly **45%** of our global total.
   - Our flagship items, the **TitanDesktop** and **QuantumCore X**, carry the lion's share of our revenue. Any stockouts, pricing errors, or fulfillment delays on these specific SKUs pose a severe threat to our quarterly targets.

---

## Dataset Structure & ERD

Our analysis is based on a structured dataset that captures the full e-commerce journey through one central event log, supported by four core dimension tables:

- **Events:** This is the primary fact table containing granular user actions across the funnel, such as page views, add to carts, checkout steps, payment activity, and completed purchases. It enables stage-by-stage funnel measurement, drop-off diagnostics, and conversion analysis at the event level.

- **Users:** This table provides user identifiers and related attributes needed to analyze behavior across customer types, such as first-time vs returning patterns. It supports user-level funnel views and retention style cuts when paired with the Events table.

- **Product:** This table contains product identifiers and descriptive fields that allow us to group and compare performance by item and category. It supports product mix analysis, top SKU contribution, and conversion performance by product.

- **Traffic:** This table captures acquisition and session attribution fields, such as channel or source classification. It enables performance comparisons across traffic sources and helps identify which channels drive the most intent and purchases.

- **Date:** This is the time dimension used to standardize reporting periods. It supports consistent filtering and aggregation by day, week, month, quarter, and year across the entire model.

Together, these datasets form a single, consistent view of how users arrive, what they interact with, and where they convert or drop off. This foundation allows us to diagnose funnel friction, evaluate channel quality, and quantify which levers can drive the highest impact on purchases and revenue.

To ensure a single source of truth for the leadership team, the data model is structured as a highly optimized star schema. It features one central event fact table and four core dimensions: `Events`, `Date`, `Users`, `Product`, and `Traffic`.

<div align="center">
  <img width="964" height="617" alt="image" src="https://github.com/user-attachments/assets/0f4e0008-8d6c-4c4a-9386-43b4041750ce" />
</div>

---

# The Deep-Dive: Diagnostics & Evidence

## Sales Funnel Health

<div align="center">
  <img width="1057" height="191" alt="image" src="https://github.com/user-attachments/assets/aa88afb8-1470-4512-8e5c-c13e278b9f51" />
</div>

- **A Rock-Solid Mid Funnel:** Once a product is in the cart, our customers are committed. Cart-to-checkout sits at **75.4%**, and checkout-to-payment is an impressive **84.9%**.
- **The High-Intent Drop-Off:** Payment-to-purchase drops to **70.2%**. This is our most urgent battleground. These users have their wallets out; every percentage point we recover here is pure, immediate revenue.
- **Strategic Recommendation:** We need to split this metric immediately. We must isolate *payment gateway failures* from *user abandonment*. Product and Payments Ops need to co-own this fix starting tomorrow.

---

## Channel Performance

<div align="center">
  <img width="1272" height="771" alt="image" src="https://github.com/user-attachments/assets/8ae855df-cd8c-4cf7-84da-00d7e5e5498d" />
</div>

### Where We Are Winning

- **Organic Search is the Backbone:** Google organic isn't just a supporting player; it is our primary growth engine, driving the highest purchase volume across all channels.
- **Email Delivers:** The newsletter is a top-tier conversion channel. It represents our most cost-effective lever for orchestrating win-backs and repeat purchases.
- **Brand Gravity (Direct Traffic):** Direct traffic goes toe-to-toe with Email and Bing. This means either our brand word-of-mouth is incredibly strong, or our attribution model is defaulting to Direct when it shouldn't.

### The Hidden Risk

- **Attribution Blind Spots:** We urgently need to confirm if our session source logic is last-touch or first-touch. If we misattribute this, we risk overstating Direct traffic while starving our assist channels of the credit (and budget) they deserve.

---

## Geographic Performance

<div align="center">
  <img width="1275" height="774" alt="image" src="https://github.com/user-attachments/assets/a7c54903-3c6e-4f06-a03b-c6ebad7d0e17" />
</div>

- **The UK Profit Engine:** At roughly **45%** of our revenue (**$10.21M**), the United Kingdom is our lifeblood. Any UI/UX changes must ensure the UK experience remains flawless.
- **The Sleeping Giants:** Canada, the United States, Australia, and Singapore are all sitting at healthy, similar sizes (**$2.2M to $4.6M** each). These are our prime targets for aggressive localization.
- **Localization as a Lever:** Aligning our payment methods, shipping promises, and return policies to feel native to these specific countries is our fastest route to lifting late-funnel conversion globally.

---

## Product Mix & Concentration Risk

<div align="center">
  <img width="1256" height="529" alt="image" src="https://github.com/user-attachments/assets/a2c02934-ae83-4bef-93d8-a98098334a3a" />
</div>

- **Heavy is the Crown:** TitanDesktop and QuantumCore X dictate our financial success. Merchandising, discounting, or pricing tests on these specific SKUs will have outsized, company-wide impacts.
- **The Bundle Opportunity:** Because these items drive such high volume, they are the perfect Trojan horses. We should be anchoring them with high-margin accessory bundles and warranty attachments.
- **Portfolio Hygiene:** We have dead weight in the catalog. We need leadership to enforce a strict rule for underperforming SKUs. Whether that's a hard margin floor or a minimum sell-through threshold.

---

## The Executive Dashboard

<div align="center">
  <img width="1078" height="809" alt="image" src="https://github.com/user-attachments/assets/19b7f679-ba77-43df-b7b5-33e9aa7637ba" />
  <img width="1075" height="808" alt="image" src="https://github.com/user-attachments/assets/67019410-3771-4cc7-98da-f28be802062f" />
  <img width="1076" height="806" alt="image" src="https://github.com/user-attachments/assets/b787c6af-c31d-4ec8-80f7-6aefb41bb052" />
  <img width="865" height="769" alt="image" src="https://github.com/user-attachments/assets/c41aeb1a-f3e3-48b1-9cd9-be82983af828" />

  <br><br>

  <a href="https://app.fabric.microsoft.com/links/wAZyfUH3oX?ctid=1e8e4649-0a9f-46a9-bb55-6b5c118e04f3&pbi_source=linkShare" target="_blank" rel="noopener noreferrer">
    <img src="https://img.shields.io/badge/Built%20with-Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black" alt="Live Power BI Dashboard" />
  </a>
</div>

---

## Order Success & Revenue Optimization Model: Predictive Python Analysis

**The Problem:** Our Power BI dashboards gave leadership a perfect view of historical performance. But when the VP of Product asked, *"If we dedicate our next two sprints to fixing the cart experience, what is the exact dollar return?"*. We needed to step out of hindsight and into forecasting.

**The Solution:** To move beyond historical reporting, I engineered a Python-based order success model. I built this simulator to give executives a way to input hypothetical optimization scenarios and instantly see the projected impact on our bottom line. The model is designed to do four things: establish absolute baseline rates from raw logs, calculate baseline AOV from completed transactions, execute sensitivity analysis for single-stage improvements, and simulate compound growth scenarios.

**Establishing the Baselines:** First, I fed the model our raw, unfiltered event logs to map the true customer journey. The funnel started with **856,929 page views**. From there, we saw a **39.86% view-to-cart** rate. Mid-funnel intent remained strong with a **76.06% cart-to-checkout** rate and an **84.94% checkout-to-payment** rate. However, the final hurdle showed a **70.61% payment-to-purchase** completion.

Ultimately, this funnel yielded **155,800 completed purchases**, netting an **18.18% overall conversion rate**. By extracting the exact revenue from those completed transactions, the model established our baseline AOV at **$268.58**, putting our baseline modeled revenue at **$41.84M**.

**The Value of 1% (Sensitivity Analysis):** With the baselines set, the next step was to find our most lucrative targets. I tasked the model with isolating each lever. Holding all other rates constant. To reveal the exact dollar value of a +1% absolute improvement at any single stage:

<img width="1241" height="618" alt="image" src="https://github.com/user-attachments/assets/ef4fdf2c-a8f8-4b0f-81e9-1005f6838774" />

| Optimization Lever | Projected Revenue Lift |
|---|---:|
| +1% View to cart | **$1.05M** |
| +1% Payment to purchase | **$0.59M** |
| +1% Cart to checkout | **$0.55M** |
| +1% Checkout to payment | **$0.49M** |
| +1% Page views | **$0.42M** |

**Simulating Future-State Scenarios:** Knowing that improving the view-to-cart rate is our most valuable lever, I ran a few compound scenarios for executive planning. If Product simply deploys a UI fix that lifts view-to-cart by 5%, revenue scales from $41.84M to $47.09M (a lift of **+$5.25M**). If Growth pairs a 50K traffic bump with that same UI fix, we are looking at **$49.84M** (a **+$8.00M** lift). And if we can orchestrate a 5% improvement across all stages simultaneously, revenue surges to $56.91M. A massive **+$15.06M** in incremental value.

**A Note on Data Governance:** Because this Python model processes raw `Events.csv` logs, the baseline totals will slightly diverge from the filtered Power BI dashboards due to deduplication logic and differing revenue definitions (gross vs. net subsets). Until metric definitions are universally standardized across departments, use this model strictly for **relative prioritization**. It tells us exactly which lever is most valuable to pull today.

---

# Recommendations

#### The data tells a clear story that our funnel is remarkably healthy up until checkout. The highest ROI lies in **improving the initial view-to-cart rate** and **patching the payment-to-purchase leak**.
#### Here are the recommendations for the **Chief Commercial Officer**, **VP Product**, and **Head of Growth**.

### 1. Secure the Highest-Intent Revenue (Payment-to-Purchase)

- **Build a Failure Taxonomy:** We need immediate visibility. Separate user abandonment from gateway declines, address verification failures, and fraud blocks. Deploy a daily dashboard tracking failure codes by country, device, and payment method.
- **Engineer Recovery Paths:** For soft declines, implement automated retries with backoff, actively offer alternative payment methods, and ensure the cart state never resets upon failure.
- **Eliminate Checkout Shock:** Surface shipping costs, duties, and delivery dates earlier in the flow. Inject country-specific messaging to soothe cross-border anxiety.
- **Rapid Abandonment Recovery:** Deploy hyper-targeted SMS or email triggers within 1 to 3 hours for sessions that input payment data but fail to convert. Personalize these by country and hero product.

### 2. Capitalize on Top-Funnel Intent (View-to-Cart)

- **Optimize Hero Pages:** Start aggressively with the landing pages catching the bulk of our Google organic traffic. Tighten the value proposition, and make shipping/returns policies impossible to miss.
- **Fortify Product Detail Pages (PDPs):** Upgrade comparison tables, inject heavy trust signals/reviews, and ensure pricing transparency. The "Add to Cart" CTA must be firmly above the fold on all mobile views.
- **Reduce Cognitive Load:** Limit the paradox of choice. Tighten variant selections, default to our best-sellers, and introduce guided bundles for our premium SKUs.
- **A/B Testing Rhythm:** Establish a weekly experiment cadence. Crucially, measure success by incremental adds-to-cart and final purchases. Not just click-through rates.

### 3. Pour Fuel on High-Converting Channels

- **Defend the SEO Moat:** Google organic is our lifeblood. We must enforce strict technical SEO guardrails and commit to refreshing our highest-intent content on a quarterly basis.
- **Automate Lifecycle Revenue:** Email is already a proven winner. We need to expand beyond newsletters by building automated post-purchase onboarding, accessory upsell tracks, and dormant-user win-backs.
- **Discipline in Paid Acquisition:** For referral and YouTube traffic, restrict optimization strictly to high-AOV items. We must monitor assisted conversions closely to ensure we aren't artificially inflating our Direct channel metrics.

### 4. Global Expansion via Localization

- **The UK Pilot:** Because the UK dominates our revenue, they get the first roll-out. Localize all payment options, shipping messaging, and support hours to natively match the UK market.
- **The Roll-out Playbook:** Once the localized lift is proven in the UK, immediately port the architecture to Canada, the US, Australia, Singapore, and Germany, making the necessary regional tweaks.

### 5. Mitigate Concentration Risk & Drive AOV

- **Operational Defense of Top SKUs:** Establish automated safety stock rules and aggressive forecast buffers for TitanDesktop and QuantumCore X. A stockout here is catastrophic to our quarterly goals.
- **Value-Add Bundling:** Stop discounting. Instead, attach warranties and high-margin accessories to our anchor items. We need to test bundles that elevate Average Order Value without sacrificing our contribution margin.
- **Executive Merchandising Reviews:** Institute a mandatory weekly review of our top SKUs, evaluating them across availability, conversion rates, return rates, and real margin.

### 6. Institutionalize Data Governance

- **Create a Single Source of Truth:** Reconcile the Power BI dashboard logic with our raw event logs. We must have a company-wide consensus on the exact definitions of a 'page view', a 'purchase', and 'revenue'.
- **Deploy User-Based Funnels:** Event logs tell half the story. We must supplement them with distinct-user conversion tracking to prevent repeat session events from inflating our confidence.
- **Solve the Attribution Argument:** formally document whether we operate on a first-touch or last-touch model, and introduce multi-touch assisted views so our channel managers can plan budgets confidently.

## The Scorecard (Success Metrics)

- **Payment-to-Purchase Pullthrough:** Target an aggressive **+3 to +5 percentage point** recovery.
- **View-to-Cart Lift:** Target **+2 to +4 percentage points** on our highest-traffic landing pages.
- **Repeat Purchase Velocity:** Prove a sustained quarter-over-quarter increase driven by the new lifecycle email programs.
- **Revenue Diversification:** Actively monitor our reliance on the UK market and our top two SKUs, with a goal of spreading the dependency load.

---

## Open Questions for Leadership & Caveats

### Questions for Stakeholders

- **The Payments Black Box:** Do we currently have access to our gateway response codes? If so, we need to know exactly which failures can be salvaged with automated retries versus routing the user to a new payment method.
- **The Shipping Friction:** Where are users hitting the wall? Is abandonment tied to the raw cost of shipping, surprise import duties, slow delivery times, or vague return policies?
- **Attribution Rules of Engagement:** Is our `Session_Source` operating on last-touch, first-touch, or a custom rules-based model? This fundamentally shifts how we allocate our marketing budget.

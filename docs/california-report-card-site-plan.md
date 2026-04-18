# California Household Stability Report Card Site Plan

## Purpose

Build a public California report card site that operationalizes the framework's `California Household Stability Test`.

The site should answer one recurring question:

> Is California making stable ordinary life more affordable, reliable, and administratively workable, while preserving the productive systems that make affordability possible?

This site should become a major public output of the framework. The manifesto explains the governing logic. The report card shows whether California is actually passing its own test.

## Executive Recommendation

Build the report card as a static, data-driven public site that lives in the same repository as the manifesto, but with its own methodology, data pipeline, and release process.

Recommended public shape:

- `Manifesto`: the normative framework
- `Report Card`: the measurement system
- `Methods`: the audit trail showing how each metric is defined, sourced, updated, and graded

Recommended launch posture:

- Start with California only
- Publish a small, legible set of core metrics
- Show trends and methodology before trying to publish a grand composite score
- Link tightly to the manifesto conceptually, but keep methodology versioned independently so the data product remains credible

## Product Goals

1. Make the `California Household Stability Test` measurable.
2. Give the framework a public scorecard that can be updated on a predictable cadence.
3. Let users see statewide performance, regional variation, and trend direction.
4. Keep every metric tied to official or otherwise primary-source data whenever possible.
5. Make the methodology transparent enough that critics can inspect it instead of dismissing it.

## Non-Goals

1. Do not launch as a sprawling "everything dashboard."
2. Do not hide judgments in a black-box composite score.
3. Do not pretend every useful metric already has perfect statewide data.
4. Do not turn the site into a general California policy encyclopedia.

## Relationship to the Manifesto

The report card should be tightly linked to the manifesto, but not fused to it.

### Recommended linkage

- The manifesto remains the canonical statement of values, priorities, and jurisdictional logic.
- The report card becomes the canonical measurement artifact for California.
- Each metric page should link back to the relevant manifesto section.
- The report card homepage should summarize the `California Household Stability Test` in plain language.
- The methods section should cite the manifesto's four dimensions:
  - affordability
  - reliability
  - friction
  - productive durability

### Recommended separation

- Manifesto revisions should not silently rewrite historical report card methodology.
- The site should show both:
  - `Framework version`
  - `Methodology version`
- Historical metric series should remain reproducible even if the manifesto language evolves.

Recommended policy:

> Tight conceptual coupling, moderate operational coupling.

That means one repo and shared governance are good. One undifferentiated document tree is not.

## Core Site Structure

Recommended site map:

1. **Homepage**
   - One-sentence definition of the Household Stability Test
   - Four dimension cards
   - Current statewide status
   - Trend summary
   - Link to manifesto

2. **California Report Card**
   - Core metrics
   - Regional comparisons
   - Trendlines
   - Notes on update freshness

3. **Metric Detail Pages**
   - Definition
   - Why it matters
   - Source
   - Update cadence
   - Methodology
   - Historical trend
   - Related manifesto section

4. **Methods**
   - Data sources
   - Transformations
   - Grading logic
   - Known limitations
   - Version history

5. **Policy Review Checklist**
   - The five-question California checklist
   - Examples of how the test can be applied to policy proposals

6. **Manifesto**
   - Link out to the manifesto documents in this repository

7. **Change Log**
   - New metrics
   - Method changes
   - Source changes

## Scoring Model

Do not launch with a single opaque `A-F` grade.

Recommended launch model:

- Publish statuses by metric: `Improving`, `Flat`, `Worsening`
- Publish current condition by metric: `Good`, `Watch`, `Poor`
- Publish dimension summaries for:
  - affordability
  - reliability
  - friction
  - productive durability

Only add a single composite statewide score after at least two annual cycles of stable methodology.

Why:

- A single grade is rhetorically powerful but methodologically fragile.
- A dimension-based score is easier to defend and easier to improve.

## Core Launch Metrics

The launch set should be small enough to read in under five minutes and strong enough to matter.

### Launch metric table

| Dimension | Metric | What it answers | Primary source(s) | Update cadence | Launch priority |
| --- | --- | --- | --- | --- | --- |
| Affordability | Essential basics burden | How much of income an ordinary household must spend on basic systems | Derived composite from ACS, water, electricity, food, and basic-care proxies | Monthly/annual mixed | Core |
| Affordability | Residential water burden | Is drinking and household water affordable relative to income? | California State Water Board Affordability Dashboard, eAR, ACS | Annual | Core |
| Affordability | Residential electricity burden | Are electric bills consuming too much of household income? | CPUC residential usage and bill data, CPUC historical electric cost data, ACS | Monthly/annual mixed | Core |
| Affordability | Utility bill volatility | Are utility costs too unstable for normal household planning? | CPUC residential bill and rate data | Monthly | Core |
| Affordability | Staple food affordability index | Are staple healthy foods becoming harder to buy? | BLS CPI regional food-at-home data, USDA ERS Food Price Outlook, USDA Thrifty Food Plan | Monthly | Core |
| Reliability | Electric service reliability | Is the electric system dependable enough for normal life and work? | CPUC electric system reliability annual reports | Annual | Core |
| Reliability | Water service security / shutoff exposure | Are households losing or risking loss of residential water service? | State Water Board shutoff data, Water Shutoff Protection Act reporting | Annual | Core |
| Reliability | Drought and storage resilience | Is California's water system resilient enough to absorb dry periods? | California Water Watch, CDEC reservoir storage data, DWR SWP allocations | Daily/monthly | Core |
| Friction | Basic-care timely access | Can Californians get timely primary care appointments? | DMHC Timely Access Data | Annual | Core |
| Friction | Essential-support processing timeliness | How long does it take to secure key basic supports? | DHCS Medi-Cal processing standards/data, CDSS CalFresh timeliness data | Monthly | Core |
| Productive durability | Primary-care shortage exposure | Is the delivery base for basic care weakening? | HCAI workforce datasets, HRSA HPSA data | Quarterly/annual | Core |
| Productive durability | Agricultural water reliability | Is water supply stability for food production improving or weakening? | DWR SWP allocation data, California Water Watch, State Water Board water reporting where usable | Monthly/seasonal | Core |

## Phase 2 Metrics

These are aligned with the framework and worth adding once the core report card is stable.

| Dimension | Metric | Why it belongs | Primary source(s) |
| --- | --- | --- | --- |
| Affordability | Utility arrearage / disconnection rates | Shows real payment distress, not just average burden | CPUC disconnections report; State Water Board shutoff data |
| Affordability | Regional burden at 25th percentile income | Better captures low-income household stress | ACS plus the same cost inputs used in the basics burden metric |
| Reliability | PSPS exposure days | Important California-specific reliability burden | CPUC PSPS materials and utility event data |
| Friction | Documentation steps to secure support | Measures bureaucratic load directly | Custom maintained methodology based on application processes; state program rules |
| Productive durability | Farmland conversion rate | Tracks erosion of productive agricultural land | California Department of Conservation FMMP |
| Productive durability | Regional food processing and distribution capacity | Shows whether the supply chain behind affordable food is weakening | Census County Business Patterns; USDA Census of Agriculture |
| Productive durability | Essential infrastructure permitting time | Directly tests whether California process is blocking essentials | Likely requires custom data collection from agency reports and project filings |

## Metric Definitions and Sources

This section is the working source map for the first implementation cycle.

### 1. Essential basics burden

**Definition**

A derived metric estimating the share of household income consumed by a baseline bundle of essentials:

- water
- electricity
- staple food
- basic-care proxy costs

This should be published for at least:

- statewide median household
- regional median household
- lower-income reference household if feasible

**Recommended source inputs**

- U.S. Census Bureau, American Community Survey API for household income:
  - <https://www.census.gov/programs-surveys/acs/data/data-via-api.html>
- Water burden inputs:
  - California State Water Board Water System Financial Capacity and Community Affordability Dashboard:
    <https://www.waterboards.ca.gov/drinking_water/certlic/drinkingwater/afforddashboard.html>
  - California State Water Board Electronic Annual Report:
    <https://waterboards.ca.gov/drinking_water/certlic/drinkingwater/ear.html>
- Electricity burden inputs:
  - CPUC Data Dashboard / residential electric usage and bill data:
    <https://webtraining.cpuc.ca.gov/about-cpuc/transparency-and-reporting/dashboard>
  - CPUC Historical Electric Cost Data:
    <https://www.cpuc.ca.gov/industries-and-topics/electrical-energy/electric-costs/historical-electric-cost-data>
- Food inputs:
  - BLS Los Angeles CPI:
    <https://www.bls.gov/regions/west/news-release/consumerpriceindex_losangeles.htm>
  - BLS San Francisco CPI:
    <https://www.bls.gov/regions/west/news-release/ConsumerPriceIndex_SanFrancisco.htm>
  - USDA ERS Food Price Outlook:
    <https://www.ers.usda.gov/data-products/food-price-outlook/>
  - USDA Thrifty Food Plan:
    <https://www.fns.usda.gov/cnpp/thrifty-food-plan-2006>

**Implementation note**

This metric should be treated as a derived flagship indicator, not as the only number that matters. Every component should remain visible.

### 2. Residential water burden

**Definition**

Estimated water cost burden relative to household income, ideally by region and utility type.

**Primary sources**

- California State Water Board Affordability Dashboard:
  <https://www.waterboards.ca.gov/drinking_water/certlic/drinkingwater/afforddashboard.html>
- California State Water Board Electronic Annual Report:
  <https://waterboards.ca.gov/drinking_water/certlic/drinkingwater/ear.html>
- ACS income data:
  <https://www.census.gov/programs-surveys/acs/data/data-via-api.html>

**Why it belongs**

Water is a lead California pillar in the framework. This metric should be one of the report card's anchors.

### 3. Residential electricity burden

**Definition**

Estimated electric bill burden relative to household income.

**Primary sources**

- CPUC residential electric usage and bill data dashboard:
  <https://webtraining.cpuc.ca.gov/about-cpuc/transparency-and-reporting/dashboard>
- CPUC Historical Electric Cost Data:
  <https://www.cpuc.ca.gov/industries-and-topics/electrical-energy/electric-costs/historical-electric-cost-data>
- CPUC electric rate comparison tool:
  <https://ia.cpuc.ca.gov/embed/ERTPWSearchPagePhase2Prod.html>
- ACS income data:
  <https://www.census.gov/programs-surveys/acs/data/data-via-api.html>

**Why it belongs**

California power affordability is central to both household stability and productive competitiveness.

### 4. Utility bill volatility

**Definition**

Change in household electricity burden over time, including swings that make planning difficult.

**Primary sources**

- CPUC residential usage and bill data dashboard:
  <https://webtraining.cpuc.ca.gov/about-cpuc/transparency-and-reporting/dashboard>
- CPUC Historical Electric Cost Data:
  <https://www.cpuc.ca.gov/industries-and-topics/electrical-energy/electric-costs/historical-electric-cost-data>

**Why it belongs**

Volatility is its own burden. A household can fail the stability test even when annual averages look tolerable.

### 5. Staple food affordability index

**Definition**

A California-oriented basket of staple healthy goods, with trend and regional comparison views.

**Primary sources**

- BLS Los Angeles CPI:
  <https://www.bls.gov/regions/west/news-release/consumerpriceindex_losangeles.htm>
- BLS San Francisco CPI:
  <https://www.bls.gov/regions/west/news-release/ConsumerPriceIndex_SanFrancisco.htm>
- USDA ERS Food Price Outlook:
  <https://www.ers.usda.gov/data-products/food-price-outlook/>
- USDA Thrifty Food Plan:
  <https://www.fns.usda.gov/cnpp/thrifty-food-plan-2006>

**Implementation note**

There is no obvious single official California staple basket. The site should say that plainly and document the basket methodology in full.

### 6. Electric service reliability

**Definition**

Customer outage frequency and duration, plus major reliability events.

**Primary sources**

- CPUC Electric System Reliability Annual Reports:
  <https://www.cpuc.ca.gov/industries-and-topics/electrical-energy/infrastructure/electric-reliability/electric-system-reliability-annual-reports>
- CPUC reliability overview:
  <https://www.cpuc.ca.gov/industries-and-topics/electrical-energy/infrastructure/electric-reliability>

**Core reported measures**

- SAIDI
- SAIFI
- major event days if available

### 7. Water service security / shutoff exposure

**Definition**

Residential water shutoff risk and actual shutoffs for nonpayment or related household instability signals.

**Primary sources**

- State Water Board Water Shutoff Protection Act information:
  <https://www.waterboards.ca.gov/drinking_water/certlic/drinkingwater/shutoff-protection.html>
- State Water Board water shutoff reporting tool:
  <https://watershut-off.waterboards.ca.gov/>
- California State Water Board eAR:
  <https://waterboards.ca.gov/drinking_water/certlic/drinkingwater/ear.html>

**Implementation note**

This metric may launch as annual totals and later improve into utility-level or region-level mapping as data quality improves.

### 8. Drought and storage resilience

**Definition**

Track whether California is building or losing water resilience.

**Primary sources**

- California Water Watch data notes:
  <https://cww.water.ca.gov/about-the-data>
- DWR Water Storage & Supply:
  <https://water.ca.gov/What-We-Do/Water-Storage-And-Supply>
- CDEC via California Water Watch / DWR:
  <https://cdec.water.ca.gov/>
- SWP Water Contractors and allocation history:
  <https://water.ca.gov/Programs/State-Water-Project/Management/SWP-Water-Contractors>

**Suggested submeasures**

- major reservoir storage versus historical average
- SWP allocation trend
- severe drought share of state, if included

### 9. Basic-care timely access

**Definition**

Can patients get routine primary care in a timely way?

**Primary sources**

- DMHC Health Plan Timely Access Data:
  <https://www.dmhc.ca.gov/DataResearch/HealthPlanTimelyAccessData.aspx>
- DMHC annual Timely Access Report archive:
  <https://www.dmhc.ca.gov/>

**Suggested submeasures**

- average primary care wait time
- share of network providers meeting timely access standards

### 10. Essential-support processing timeliness

**Definition**

How long households wait to secure important support systems tied to basic stability.

**Primary sources**

- DHCS Medi-Cal processing standards and county performance guidance:
  - Help page:
    <https://www.dhcs.ca.gov/Medi-Cal/Pages/Help.aspx>
  - 2025 county letter on processing standards:
    <https://www.dhcs.ca.gov/services/medi-cal/eligibility/letters/Documents/25-08.pdf>
- CDSS CalFresh timeliness pages:
  - Timeliness of application processing:
    <https://www.cdss.ca.gov/inforesources/calfresh-resource-center/timeliness-of-application-processing>
  - CF 296 report:
    <https://www.cdss.ca.gov/inforesources/research-and-data/calfresh-data-tables/cf296>

**Implementation note**

This is a strong friction metric because it measures bureaucracy directly instead of inferring it.

### 11. Primary-care shortage exposure

**Definition**

How much of California lives in or is exposed to primary-care shortage conditions.

**Primary sources**

- HCAI Health Workforce Data:
  <https://hcai.ca.gov/workforce/health-workforce/workforce-data/>
- HCAI data resources / datasets:
  <https://hcai.ca.gov/data/datasets>
- HRSA shortage area tools:
  <https://data.hrsa.gov/topics/health-workforce/shortage-areas>

**Why it belongs**

This is a productive durability metric for the healthcare pillar, not just an access metric.

### 12. Agricultural water reliability

**Definition**

Track whether California is preserving stable water conditions for food production.

**Primary sources**

- DWR SWP allocation pages:
  <https://water.ca.gov/Programs/State-Water-Project/Management/SWP-Water-Contractors>
- California Water Watch:
  <https://cww.water.ca.gov/about-the-data>
- State Water Board water reporting systems:
  <https://water.waterboards.ca.gov/waterrights/water_issues/programs/water_diversion_reporting/>
  <https://www.waterboards.ca.gov/upward/calwatrs/>

**Implementation note**

This will likely need a mix of official water-supply proxies rather than a single perfect statewide series.

## Expansion Metrics Worth Adding

These are aligned with the framework and should be kept in the backlog from day one.

### Farmland conversion rate

- California Department of Conservation Farmland Mapping and Monitoring Program:
  <https://www.conservation.ca.gov/dlrp/fmmp/Pages/index.aspx>

### Regional food processing and distribution capacity

- U.S. Census County Business Patterns:
  <https://www.census.gov/programs-surveys/cbp.html>
- CBP datasets:
  <https://www.census.gov/programs-surveys/cbp/data/datasets.html>
- USDA Census of Agriculture:
  <https://www.nass.usda.gov/AgCensus/>

### Utility disconnections

- CPUC 2023 disconnections report:
  <https://www.cpuc.ca.gov/-/media/cpuc-website/divisions/office-of-governmental-affairs-division/reports/2023/disconnections-report-2023_pu-code-sec-910.pdf>

### PSPS exposure

- CPUC Public Safety Power Shutoff materials:
  <https://www.cpuc.ca.gov/PSPS>

## Recommended Threshold Approach

Do not invent false precision where California lacks clean statewide data.

Recommended threshold logic:

1. **Condition**
   - `Good`
   - `Watch`
   - `Poor`

2. **Trend**
   - `Improving`
   - `Flat`
   - `Worsening`

3. **Method note**
   - absolute threshold
   - benchmark comparison
   - trend only
   - proxy

Every metric page should clearly say which of the four it uses.

## Website Publishing Recommendation

### Recommended v1 publishing model

Keep the site in this repository and publish it as a static site.

Recommended repo layout:

```text
README.md
docs/
  california-report-card-site-plan.md
  federal-framework.md
  california-framework.md
report-card/
  app/
  data/
  methodology/
  scripts/
```

### Recommended hosting path

**Recommendation:** publish from the same repo, using GitHub Actions to build and deploy a static site.

**Recommended public URL progression:**

1. Phase 1:
   - GitHub Pages project URL for fast launch
2. Phase 2:
   - custom domain or subdomain such as `reportcard.<primary-domain>`

### Why same repo first

- Strong provenance between framework and report card
- One review workflow
- Easier versioning of methods alongside framework text
- Lower operational overhead

### Why not split into a separate repo immediately

- Too much distance between policy logic and measurement logic
- Harder to keep methodology synced with framework language
- Adds avoidable overhead before the product is real

## Hosting Options

### Option A: GitHub Pages

**Best for v1**

Why:

- very low operational overhead
- strong fit for static artifacts
- built-in compatibility with repo-based workflow
- good enough for a documentation-heavy public site

Official docs:

- GitHub Pages quickstart:
  <https://docs.github.com/en/pages/getting-started-with-github-pages>
- Creating a GitHub Pages site:
  <https://docs.github.com/en/enterprise-cloud@latest/pages/getting-started-with-github-pages/creating-a-github-pages-site>

### Option B: Cloudflare Pages

**Best if the site grows into a more polished public-facing product with previews and heavier traffic**

Why:

- fast static hosting
- good preview workflow
- easy custom domain handling

Official docs:

- Cloudflare Pages overview:
  <https://pages.cloudflare.com/>
- Static HTML on Cloudflare Pages:
  <https://developers.cloudflare.com/pages/framework-guides/deploy-anything/>

### Option C: Netlify

**Reasonable fallback**

Official docs:

- Netlify create deploys:
  <https://docs.netlify.com/site-deploys/create-deploys/>

### Recommendation summary

Use **GitHub Pages first** unless there is a strong reason to optimize hosting before the data product is stable.

Move to **Cloudflare Pages** only if one of these becomes true:

- the site needs richer preview environments
- custom-domain and edge performance become important enough to justify another platform
- the build gets more complex than GitHub Pages comfortably handles

## Data Pipeline Recommendation

The report card should be static at the presentation layer and versioned at the data layer.

Recommended workflow:

1. Pull source data from official sources
2. Normalize into reproducible local datasets
3. Build derived metrics
4. Emit versioned JSON or CSV snapshots
5. Build static pages from those snapshots
6. Publish site and preserve prior releases

### Recommended cadence

- Monthly refresh:
  - electricity burden
  - electricity volatility
  - food affordability
  - key water and drought indicators
- Quarterly refresh:
  - if any source supports cleaner quarterly healthcare or workload data
- Annual refresh:
  - water affordability
  - primary-care shortage exposure
  - farmland conversion
  - larger methodology review

### Versioning policy

Every public release should record:

- release date
- framework version
- methodology version
- source versions or source pull dates

## Governance Model

Recommended ownership model:

- **Framework owner**: maintains manifesto logic and metric intent
- **Methods owner**: maintains data definitions and transformations
- **Editor/reviewer**: checks whether the public interpretation still matches the framework

The site should not allow silent methodology drift.

Any change to:

- metric definition
- threshold logic
- weighting
- source substitution

should create a visible methodology note in the site change log.

## How Tight the Site Should Be to the Manifesto

Recommended answer: **close, but not dependent**.

What should be tightly linked:

- language of the Household Stability Test
- four measurement dimensions
- pillar references on metric pages
- cross-links in navigation

What should remain independent:

- release cadence
- data corrections
- methodology versioning
- historic score series

Practical rule:

> The manifesto should explain why the report card exists. The report card should show whether the framework's claims survive contact with reality.

## Recommended Launch Phases

### Phase 0: Spec

- finalize launch metrics
- finalize definitions
- finalize source map
- finalize methodology version `0.1`

### Phase 1: MVP site

- homepage
- California report card page
- 8 to 12 core metrics
- methodology page
- manifesto links
- trendlines where source history exists

### Phase 2: Regionalization

- county or region views where defensible
- regional food affordability view
- regional water/electricity burden comparisons
- shortage-area maps

### Phase 3: Policy scoring

- add scorecard overlays for major state policy proposals
- let users see how proposals fare against the five-question policy review checklist

## Key Risks and Mitigations

### Risk 1: too many metrics

**Mitigation**

Launch with a disciplined core set. Keep a visible backlog for expansions.

### Risk 2: false precision

**Mitigation**

Label every metric as exact, proxy, or composite. Publish methods openly.

### Risk 3: data gaps

**Mitigation**

Use official proxies where necessary and say when California lacks a good statewide source.

### Risk 4: the manifesto and the report card drift apart

**Mitigation**

Keep both in the same repo and version both separately.

### Risk 5: the site becomes a design project instead of a measurement project

**Mitigation**

Treat clarity, methodology, and update discipline as first-order product requirements.

## Final Recommendation

Build the report card.

This is one of the strongest things the framework can produce because it turns broad principles into auditable claims.

The site should be:

- public
- small at launch
- source-heavy
- methodology-first
- tightly tied to the California Household Stability Test

If the manifesto says California should be judged by whether it makes stable ordinary life more affordable and reliable, then the framework should publish that judgment in public and keep updating it.

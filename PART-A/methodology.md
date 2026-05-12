# Research Methodology
### DeepThought Federer Company Identification — Hyderabad Biotech + Diagnostics

---

## 1. Research Objective

Identify companies in Hyderabad's specialty biotech and diagnostics/life-science tools sectors that fit the "Federer company" profile: promoter-driven, technically differentiated, actively growing Indian manufacturers. These companies are potential customers for DeepThought, which helps Indian manufacturing businesses improve operations and execution.

The core research question for every company: **"Is this company a real manufacturer of technically differentiated products, or a service provider / trader wearing a manufacturer's label?"**

---

## 2. Research Workflow

```
Phase 1 — Build Raw Universe
  ├── Scrape 6–8 source directories
  ├── Collect ~45 raw company names
  └── Record source URL for each entry

Phase 2 — First Filter (fast rejection)
  ├── Remove CROs, testing labs, MNC subsidiaries
  ├── Remove PE-majority-owned companies
  ├── Remove pure consultancies and traders
  └── ~25–30 companies survive

Phase 3 — Deep Research per Company
  ├── Verify: product catalog exists?
  ├── Verify: manufacturing NIC code or IndiaMART manufacturer listing?
  ├── Verify: founder background (LinkedIn, company website, press)
  ├── Verify: growth signals (funding, hiring, new products)
  └── Flag: PE ownership, institutional co-ownership

Phase 4 — Score Each Company (C1–C6 rubric)
  ├── Apply scoring rubric with evidence citations
  ├── Assign Confidence Tier (T1/T2/T3)
  └── Flag uncertainty where evidence is thin

Phase 5 — QA Review
  ├── Check scoring consistency
  ├── Verify C4 scores match stated founder evidence
  ├── Reconcile conflicting sources (MCA vs. Crunchbase)
  └── Remove or downgrade high-risk inclusions

Phase 6 — Final Deliverables
  └── Compile CSV, documentation, scale-up strategy
```

---

## 3. Sources Used

### Primary Directories
| Source | Purpose |
|---|---|
| pharmchoices.com (Hyderabad Biotech List 2026) | Company name universe |
| IndiaMART (manufacturer filter) | Manufacturer status verification |
| Tracxn | Revenue, funding, employee count, founder names |
| Zauba Corp / Tofler | MCA-linked financials and director verification |
| Crunchbase | Founder backgrounds, funding history |

### Ecosystem Sources
| Source | Purpose |
|---|---|
| Scispot blog (Top 10 Hyderabad Biotech, March 2026) | Company discovery |
| builtin.com (22 Hyderabad biotech companies) | Company discovery |
| ADMI member list (Association of Diagnostics Manufacturers India) | Manufacturer verification |
| Genome Valley Wikipedia + labiotech.eu | Ecosystem context |
| MyCorporateInfo / Falcon Ebiz | MCA director verification |

### Verification Sources
| Source | Purpose |
|---|---|
| Company websites (direct fetch) | Product catalog, founder bios |
| LinkedIn (public profiles) | Founder background verification |
| Facebook public profiles | Founder credential cross-reference |
| RocketReach / ZoomInfo | Career history (treated as moderate confidence — not primary) |
| Retraction Watch | Integrity risk check (used for Oncosimis CEO verification) |
| medRxiv | Research publication verification |

---

## 4. Filtering Logic

### Immediate Rejection Criteria (any one = reject)
- Primary revenue from testing/analysis services for external clients → **CRO**
- MNC subsidiary or large listed corporation → **Not promoter-driven**
- PE/institutional majority ownership → **Not Federer**
- Pure trading, importing, or rebranding → **Non-manufacturer**
- Pure consulting/advisory → **Non-manufacturer**
- Government/cooperative ownership → **Institutional, not Federer**
- >500 employees → **Too large for DeepThought ICP**

### Inclusion Criteria (all required)
- Manufactures own branded products
- India-headquartered
- Some form of identifiable leadership (ideally technical founder)
- At least one differentiation signal (certification, grant, unique product, patent)
- Active in a growing sector

---

## 5. Scoring Rubric

| Criterion | Max | Weak (0) | Moderate (half) | Strong (full) |
|---|---|---|---|---|
| C1 — Manufacturer | 10 | Service/trading | Partial evidence | Own product + facility confirmed |
| C2 — India-Based | 5 | Foreign MNC HQ | — | India HQ confirmed |
| C3 — Differentiation | 25 | Commodity | ISO cert + distinct product | Patent / DSIR / BIRAC / unique validated product |
| C4 — Technical Founder | 20 | MBA/admin only | Technical but no PhD | PhD/IIT/CCMB/IISc + research history |
| C5 — Sector Tailwinds | 20 | Declining sector | Growing moderately | Strong secular tailwind (IVD, genomics, biologics) |
| C6 — Growth Signals | 20 | Stagnant | Some signals | Hiring + funding + new product + expansion |

**Classification Thresholds:**
- 80–100: Strong Federer
- 60–79: Probable Federer
- 40–59: Borderline
- Below 40: Reject

---

## 6. Confidence Tier Definitions

| Tier | Criteria | Action |
|---|---|---|
| **T1 — High Confidence** | 2+ independent verified sources; MCA/website/press confirms manufacturing; founder background confirmed from at least 2 sources | Include with standard evidence citation |
| **T2 — Medium Confidence** | 1 verified source + 1 secondary source; founder background partially confirmed; manufacturing claimed but not independently verified | Include with explicit uncertainty note |
| **T3 — Low Confidence** | Single source; founder unknown; manufacturing unconfirmed; revenue/size unknown | Include only with "Manual verification required" flag; do not use for outreach without verification |

---

## 7. AI Usage

**Role of AI in this research:**
- Claude (Anthropic) used for web search synthesis across multiple sources
- AI used for generating initial company name candidates from directory descriptions
- AI used to identify inconsistencies between sources (e.g., MCA director records vs. Crunchbase founder claims)
- AI used to draft personalization hooks based on verified product/growth data

**What AI did NOT do:**
- AI did not invent revenue figures — all financials sourced from Tracxn, Tofler, or MCA with FY year
- AI did not invent founder credentials — only stated what was verifiable with named source
- AI did not assume manufacturing capability from company name alone
- AI did not resolve the Oncosimis CEO identity question — flagged for manual verification

---

## 8. Hallucination Control Protocol

1. **Revenue Rule:** No revenue figure entered unless from MCA/Tracxn/Tofler with explicit financial year stated
2. **Founder Rule:** No credential entered unless from company website, LinkedIn, or press release; "Unknown" used explicitly when not found
3. **Manufacturing Rule:** Manufacturer status requires one of: (a) IndiaMART manufacturer listing, (b) company website product catalog, (c) MCA NIC code in manufacturing range 21001–33999, or (d) ISO 13485 / GMP manufacturing certification
4. **Dual-Source Rule:** Any company scored 70+ must have at least 2 independent sources confirming manufacturing and founder background
5. **Uncertainty Labeling:** Every unverified claim is labeled "Manual verification recommended" or "Source: [single source name only]"
6. **Integrity Check:** For companies where founder/director names returned concerning results in external databases (e.g., research retractions), the company was removed from the shortlist pending manual verification

---

## 9. Definition of "Manufacturer"

For this research, a company qualifies as a manufacturer (C1 = 10) only if:
- It has its own product brand (not a white-label reseller)
- It has a production facility (own or leased with manufacturing operations)
- Products are registered in the company's name on a regulatory database (CDSCO/MDNet) or certified under ISO 13485 / WHO GMP

A company that sequences samples, stores biospecimens, or assembles kits from imported components without proprietary chemistry is classified as C1 = 5 (partial) or C1 = 3 (low).

---

## 10. Limitations

- LinkedIn profiles were not directly accessed (paywalled for full profiles) — career histories sourced from Facebook public profiles, company websites, and aggregator sites (RocketReach/ZoomInfo treated as medium confidence)
- Financial data for private companies is incomplete — many companies do not file full P&L with MCA
- Three companies (D-NOME, Pariksha Biotech, Amplikon Biosystems) remain at T3 confidence due to single-source evidence — require on-ground verification before outreach

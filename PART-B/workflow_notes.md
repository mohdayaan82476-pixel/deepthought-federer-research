# Workflow Notes
### Practical Execution Notes for Analysts

---

## How to Use the companies.csv

1. **Start with Confidence Tier:** T1 companies are ready for outreach. T2 need one verification call first. T3 should not be contacted until MCA and website are verified.
2. **Use the Personalization Hook column** as the first line of a cold email or LinkedIn message — it is designed to be copy-paste ready with minor editing.
3. **The Outreach Contact column** has the best available email. For companies where this field is "N/A — verify first," do not attempt outreach.

---

## Common Mistakes to Avoid

**Mistake 1: Treating IndiaMART listing as proof of manufacturing**
IndiaMART allows companies to list as "Manufacturer and Supplier" without verification. Always check for a second signal: product catalog on company website, ISO 13485 certificate, or CDSCO registration.

**Mistake 2: Using RocketReach/ZoomInfo revenue as ground truth**
These aggregators estimate revenue algorithmically for Indian private companies and are frequently wrong by 2–5x. Use Tracxn, Tofler, or MCA filings only.

**Mistake 3: Assuming BIRAC funding = manufacturing**
BIRAC BIG grants fund early-stage startups, many of which are still in R&D phase with no commercial manufacturing. Verify whether the company has moved from R&D to production before scoring C1 as 10.

**Mistake 4: Confusing founder name with technical credential**
A company called "Dr. [Name] Biotech" does not guarantee a PhD founder. Always trace the credential: PhD from which institution, in which field, what lab/research experience.

**Mistake 5: Counting service revenue as product revenue**
A company that earns ₹20Cr from CRO services and ₹2Cr from product sales is a CRO with a product side-hustle — not a manufacturer. The primary revenue source determines the classification.

---

## Segment Definitions for This Assignment

| Segment | Include | Exclude |
|---|---|---|
| Specialty Biotech | Recombinant proteins, biosimilar mAbs, fermentation products, gonadotropins, monoclonal antibodies, biologics | Generic biosimilars with no IP, commodity fermentation |
| Diagnostics & Life-Science Tools | IVD kits, PCR/NAT assays, IHC reagents/antibodies, point-of-care devices, genomics tools, ELISA kits | Testing lab services, CRO services, diagnostic imaging |

---

## Federer vs. Non-Federer Decision Tree

```
Is the company's primary revenue from services?
  YES → REJECT (CRO, testing lab, consulting)
  NO → Continue

Does an MNC, PE firm, or government entity own majority?
  YES → REJECT
  NO → Continue

Can you identify a specific manufactured product with the company's brand?
  NO → Flag as T3, do not score until verified
  YES → Continue

Is the company founder/promoter identifiable as technically qualified?
  NO (unknown) → C4 = 5 max
  YES (BSc + domain) → C4 = 10
  YES (MSc + research) → C4 = 15
  YES (PhD/IIT + research) → C4 = 20

Does the company have visible growth signals in last 24 months?
  (hiring data / new product / funding / expansion)
  NO → C6 = 0–5
  SOME → C6 = 10
  STRONG → C6 = 20

Is the product differentiated vs. commodity?
  COMMODITY (generic API, plain reagent, white-label) → C3 = 0–10
  SOME DIFFERENTIATION (ISO cert, distinct product category) → C3 = 12
  HIGH DIFFERENTIATION (patent / DSIR / BIRAC / ICMR validation) → C3 = 25
```

---

## Notes on Specific Companies

**Sanzyme Ltd. — Promoter Check Required**
Before outreach, verify via MCA shareholding data whether Jay Soman is a promoter or a hired MD. If institutional/employee ownership dominates, Sanzyme is not a Federer. Call the investor relations or admin contact at Sanzyme to ask about ownership structure if MCA data is inconclusive.

**D-NOME — Verify Existence First**
Search MCA21 portal for "D-NOME Private Limited" to confirm legal registration. If found, fetch CIN and director names. If not found, the company may operate under a different legal name. Check Scispot article for any linked website or founder mention.

**Mapmygenome — Clarify Revenue Model**
The critical question is: does Mapmygenome manufacture the Genomepatri kit (physical product with their assay chemistry), or do they collect a saliva sample, run it on an Illumina sequencing array, and generate a personalized report? If the latter, C1 = 5 (data/service product, not a physical manufactured kit). Email or call their customer support and ask: "Is the Genomepatri kit manufactured in-house in Hyderabad?"

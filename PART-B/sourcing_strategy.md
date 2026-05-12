# Sourcing Strategy
### How to Find Federer Companies Across India

---

## 1. The Core Sourcing Challenge

Most companies in biotech and diagnostics are not discoverable from a single database. They exist across directories, industrial estates, regulatory registries, grant recipient lists, and ecosystem reports — each capturing a different slice of the universe. The sourcing job is to triangulate across all of them and eliminate duplicates.

**Target profile to source for:** Indian-promoter-owned, manufacturing-focused, 20–300 employees, technically differentiated, active in biotech/diagnostics/life science tools.

---

## 2. Tier 1 Sources (Verified Manufacturers)

These sources confirm manufacturing status by design.

### ADMI — Association of Diagnostics Manufacturers India
- **URL:** admi-india.org/members
- **Coverage:** 500+ verified diagnostic kit and reagent manufacturers, all India
- **Why it's good:** Membership requires manufacturing activity — traders cannot join
- **How to use:** Download full member list → filter by city → cross-reference with MCA

### BIRAC BIG Grant Awardees (All 24 Rounds)
- **URL:** birac.nic.in → Funding → BIG → Beneficiaries list
- **Coverage:** ~800 startups across all rounds; all are technical product companies
- **Why it's good:** BIRAC grant = government-validated technical manufacturing startup
- **How to use:** Filter by sector (Diagnostics/Biotech) + state → collect company names + contact

### ABLE — Association of Biotech Led Enterprises
- **URL:** ableindia.in → Members
- **Coverage:** ~200 biotech companies; mix of manufacturers and CROs
- **Why it's good:** Verified biotech companies; screened for R&D and manufacturing
- **How to use:** Download member directory → filter manufacturers vs. service companies

### Pharmexcil Export Member List
- **URL:** pharmexcil.com → Members
- **Coverage:** Pharma and biotech exporters — all have manufacturing by definition
- **How to use:** Filter by product type (biotech/diagnostics/reagents) + state

---

## 3. Tier 2 Sources (Good for Volume, Needs Filtering)

### IndiaMART (Manufacturer Filter)
- **Search pattern:** "[product] manufacturer [city]"
- **Filter:** Business Type = Manufacturer Only (not Distributor or Trader)
- **Key search terms:** diagnostic kit manufacturer, recombinant protein manufacturer, enzyme manufacturer, IVD reagent manufacturer, PCR kit manufacturer, immunoassay kit manufacturer
- **Yield:** High volume; ~30% will be actual manufacturers after verification

### DPIIT Startup India Portal
- **URL:** startupindia.gov.in → Recognised Startups
- **Filter:** Industry = Biotechnology; State = [target state]
- **Coverage:** 100,000+ startups; ~2–5% are relevant manufacturers per state
- **Yield after filter:** ~200 per major state

### MCA Company Search (NIC Code Filter)
- **NIC codes for target:** 2100x (pharma/biotech manufacturing), 3200x (medical devices), 2660x (IRE instruments)
- **How to use:** MCA21 portal → company search → filter by NIC code + state
- **Why it's good:** Directly finds legal manufacturers by business activity registration

---

## 4. Tier 3 Sources (Signal Amplifiers)

### Industrial Estate Company Lists
| Estate | City | Coverage |
|---|---|---|
| Genome Valley | Hyderabad | 200+ companies; biotech cluster |
| Medical Device Park Sultanpur | Hyderabad | 55 companies; all GMP manufacturers |
| ALEAP Industrial Estate | Hyderabad | Mixed manufacturing |
| IDA Nacharam / IDA Jeedimetla | Hyderabad | Mixed industrial; some biotech |
| TICEL Bio Park | Chennai | 80+ biotech companies |
| Hinjewadi / Balewadi cluster | Pune | 100+ life science companies |
| Electronic City / Bommasandra | Bangalore | 200+ biotech/pharma companies |

### Ecosystem Reports
- Scispot blog (annual "Top X Hyderabad/Bangalore biotech" lists)
- BuiltIn city-specific company lists
- Telangana/Karnataka Life Sciences government directories
- BioAsia exhibitor lists (annual Hyderabad event — verified companies only)

### LinkedIn Company Search
- **Filters:** Industry = Biotechnology + Medical Device; Size = 11–200 employees; Location = [city]; Keywords = "manufacturer" OR "in-house" OR "we develop" OR "proprietary"
- **Yield:** High relevance; ~50% hit rate for genuine manufacturers

---

## 5. City Prioritization

| Priority | City | Reason | Estimated Federer Companies |
|---|---|---|---|
| 1 | Hyderabad | Genome Valley ecosystem; Medical Device Park; largest concentration | 40–60 |
| 2 | Bangalore | TICEL Bio Park; Electronic City; 2nd largest biotech cluster | 50–80 |
| 3 | Pune | Pharma + medtech manufacturing belt; Hinjewadi cluster | 30–50 |
| 4 | Delhi NCR | Faridabad diagnostics cluster; Noida pharma; CSIR ecosystem | 25–40 |
| 5 | Ahmedabad | Pharma-to-biotech corridor; strong manufacturing base | 20–35 |
| 6 | Chennai | TICEL; SRM; IIT Madras spinoffs | 15–25 |
| 7 | Mumbai | Smaller biotech cluster; higher proportion of large corps | 10–20 |

**Total estimated Federer-eligible manufacturers across India:** 200–300

---

## 6. Filtering Strategy at Scale

### Fast Rejection Rules (automated)
```python
REJECT if any:
- company_name contains: ["Laboratories", "Diagnostics Lab", "Testing", "Research Services", "Consulting", "Advisory"]
  → EXCEPTION: "Diagnostics" alone does not reject; "Diagnostics Lab" or "Diagnostics Services" does
- employee_count > 500
- parent_company is known MNC (Novartis, GSK, Pfizer, Eurofins, Charles River, etc.)
- primary_business_keyword in ["CRO", "contract research", "testing services", "fee per sample"]
- ownership contains: PE firm name (Quadria, Temasek, ChrysCapital, etc.)
```

### Manual Review Triggers
```
ESCALATE to manual review if:
- Revenue > ₹100Cr (may be too large or government-contract-driven)
- Company name includes both "manufacturing" AND "services"
- Founding year < 2000 (may be established/stagnant — verify growth signals)
- Only source is IndiaMART (needs second source confirmation)
```

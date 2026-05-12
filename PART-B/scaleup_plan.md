# Scale-Up Plan
### 1000 Companies in One Month — Execution Blueprint

---

## Overview

**Goal:** Build a verified, scored list of 1000 Federer-candidate companies across India within one calendar month.

**Team assumption:** 1 analyst (internship level) + AI tools + 4–6 hours/day research time.

**Yield assumption:** Of 1000 companies researched, expect ~150–200 to score as Probable or Strong Federer.

---

## Four-Week Execution Plan

---

### Week 1 — Build Raw Database (Target: 2000 raw entries)

**Objective:** Collect company names, city, and source URL. No deep research yet.

**Daily tasks:**
| Day | Task | Target Output |
|---|---|---|
| Mon | Download ADMI full member list; BIRAC BIG awardees rounds 1–24 | 700 entries |
| Tue | DPIIT Startup India portal: Biotechnology + Medical Device, all states | 400 entries |
| Wed | IndiaMART searches: 15 product keywords × 6 cities | 400 entries |
| Thu | LinkedIn company search: 6 cities × 3 keyword combinations | 300 entries |
| Fri | Ecosystem reports: BioAsia 2024/2025 exhibitor lists; TICEL; Genome Valley; state directories | 200 entries |

**Deliverable:** `raw_universe.csv` — 2000 rows with: Company Name, City, Segment, Source URL, Website URL (if found)

**Deduplication:** Remove exact-name duplicates. Estimated survivors: ~1600 unique companies.

---

### Week 2 — First Filter + MCA Enrichment (Target: 800–1000 survivors)

**Objective:** Apply fast rejection rules; add MCA data (NIC code, director names, paid-up capital).

**Automated steps (Python script):**
```python
# Step 1: Fast rejection by name keywords
REJECT_KEYWORDS = [
    "laboratory services", "testing lab", "diagnostics lab",
    "contract research", "consulting", "advisory", "CRO",
    "Novartis", "GSK", "Pfizer", "Eurofins", "Sanofi", "AstraZeneca",
    "Abbott", "Roche", "Siemens Healthineers"
]

# Step 2: Flag for review
FLAG_KEYWORDS = [
    "hospitals", "clinic", "healthcare services",
    "trading", "import", "distribution"
]
```

**Manual steps:**
- MCA lookup for each surviving company: NIC code, paid-up capital, director names
- Flag any with paid-up capital < ₹5L (very small, may be shell) or > ₹50Cr (likely large)
- Flag any director name matching known PE firms or large corp subsidiaries

**Deliverable:** `filtered_companies.csv` — 800–1000 rows with: + NIC Code, Director Names, Paid-Up Capital, First-Filter Result

---

### Week 3 — AI Scoring Pass (Target: 800 companies scored)

**Objective:** Score C1–C6 for all surviving companies using LLM + website scraping.

**Process per company (automated):**
1. Fetch company website (Python requests + BeautifulSoup)
2. Extract: product catalog keywords, founder names, certification mentions
3. Pass to LLM prompt:

```
Given this company description and website content:
[COMPANY_DESCRIPTION]

Score each criterion (0, half marks, or full marks):
C1 - Manufacturer (10): Does this company make its own products?
C3 - Differentiation (25): Are products technically differentiated (patents, DSIR, certifications, unique product)?
C4 - Technical Founder (20): Is the founder/leadership technically qualified (PhD, IIT, research background)?
C6 - Growth Signals (20): Are there growth signals (hiring, funding, new products, expansion)?

Output ONLY: C1=[score], C3=[score], C4=[score], C6=[score], reason=[one line]
```

4. C2 (India-based) = 5 for all surviving companies (already confirmed India HQ)
5. C5 (Sector tailwinds) = assigned by segment: Diagnostics = 20, Genomics = 20, Specialty Biotech = 20, API/Commodity = 10
6. Compute total score; flag confidence tier

**Human review:** All companies scoring ≥ 60 get a 5-minute manual spot-check

**Deliverable:** `scored_companies.csv` — 800 rows with C1–C6 scores, totals, confidence tier

---

### Week 4 — Human QA + Final List (Target: 1000 final + 200 Federer candidates)

**Objective:** Manually verify top 200 scorers; produce final submission-ready list.

**Monday–Wednesday: Manual verification sprint**
- For each company scoring ≥ 60: verify manufacturer status (product catalog + MCA NIC), founder background (LinkedIn/website), check for PE flag (Tracxn), check employee count (not >500)
- Remove false positives — estimated 30–40% of auto-scored ≥60 companies will fail manual check

**Thursday: Personalization hooks**
- Write specific outreach hooks for all Probable + Strong Federer companies
- Hook formula: [Recent specific event] + [Operational pain point it creates] + [Opening question]

**Friday: Final output**
- `final_1000_companies.csv` — all 1000 companies with scores and verdicts
- `federer_prospects_200.csv` — top 200 Probable + Strong Federers with personalization hooks
- `rejected_log.csv` — all rejected companies with reasons

**Deliverable:** Final scored database ready for DeepThought sales team use

---

## Yield Assumptions

| Stage | Count | Assumption |
|---|---|---|
| Raw universe | 2000 | From 6 sources across 7 cities |
| After deduplication | 1600 | ~20% duplicates across sources |
| After fast filter | 1000 | ~37% rejected (CRO, MNC, traders, too large) |
| After AI scoring (≥40) | 400 | ~40% score above Borderline |
| After human QA (≥60, verified) | 150–200 | ~50% of auto-60+ pass manual check |
| **Final Federer candidates** | **150–200** | Probable + Strong Federers |

---

## Automation Stack

| Task | Tool | Notes |
|---|---|---|
| Web scraping directories | Python (requests + BeautifulSoup) | IndiaMART, ADMI, BIRAC pages |
| Name-based fast rejection | Python (keyword matching) | Simple string matching |
| MCA lookup | Python + MCA21 API or Zauba scrape | Director names, NIC codes |
| Website content extraction | Python (requests + text extraction) | Product catalog keywords |
| LLM scoring | Claude API or GPT-4o API | C1/C3/C4/C6 scoring from text |
| Deduplication | Python (fuzzy matching — fuzzywuzzy) | Company name normalization |
| Final CSV | pandas | Standard data manipulation |

---

## Quality Control Framework

### Anti-Hallucination Checks
- Revenue: Only from Tracxn/Tofler/MCA — never from aggregator estimates
- Founder credentials: Only from website or LinkedIn — never from RocketReach revenue estimates
- Manufacturing: Only confirmed if website has product catalog OR IndiaMART manufacturer listing OR ISO 13485 mention

### False Positive Reduction
- Dual-source rule: Score ≥ 70 requires 2+ independent sources
- Integrity check: Director/founder names run against Retraction Watch and known PE owner databases
- Segment check: Companies in veterinary/industrial/food sectors excluded unless explicitly within scope

### Weekly QC Checkpoints
- End of Week 1: Check that raw universe has no obvious large corp names (>5 MNC names in list = sourcing problem)
- End of Week 2: Verify NIC code distribution — target >60% in manufacturing range (21xxx–33xxx)
- End of Week 3: Spot-check 10 random LLM-scored companies manually — if >3 are wrong, recalibrate prompt
- End of Week 4: Final analyst sign-off on all Strong Federer classifications

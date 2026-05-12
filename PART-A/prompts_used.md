# Prompts and Search Queries Used
### DeepThought Federer Research — AI Usage Documentation

---

## 1. Web Search Queries Used

### Company Discovery Queries
```
diagnostic kit manufacturer Hyderabad biotech company India
recombinant protein manufacturer Hyderabad biotech startup India 2022 2023 2024
enzyme manufacturer Hyderabad "in-house" OR "we manufacture" life science tools India SME
Hyderabad biotech startup manufacturer BIRAC grant funded 2020 2021 2022 2023 diagnostics genomics
Hyderabad life science diagnostics tools manufacturer startup "Genome Valley" promoter founder technical product
"diagnostic kit manufacturer" Hyderabad site:indiamart.com
biotech manufacturer Hyderabad "we manufacture"
"life science tools" manufacturer Hyderabad -CRO -laboratory services
BIRAC grant recipient Hyderabad diagnostics
Hyderabad biotech startup manufacturer 2022 2023 2024
```

### Company-Specific Verification Queries
```
Huwel Lifesciences Hyderabad PCR diagnostic kit manufacturer founder promoter
Mapmygenome Hyderabad founder CEO genomics diagnostic manufacturer
Clonz Biotech Hyderabad biosimilar monoclonal antibody manufacturer founder CEO
Narasimha Rao Nedunuri Clonz Biotech background technical
PathNSitu Biotechnologies Hyderabad founder CEO director name background
Kamal Prasad PathNSitu Biotechnologies founder background Diagnostic BioSystems QC manager IHC
Oncosimis Biotech Hyderabad MCA director founder name CIN U registration
Sudarsanareddy Lokireddy Oncosimis Biotech background PhD scientist
Cytobiologics Promea Therapeutics founder director Rajesh Tummuru Gopi Lekkala background PhD
Rajesh Tummuru Promea Therapeutics MBBS Vanderbilt MBA Biotrum background qualification
Sapien Biosciences Hyderabad founder Jugnu Jain background Apollo joint venture ownership structure
PopVax Hyderabad mRNA vaccine manufacturer founder funding 2024 2025
Sanzyme Hyderabad fermentation probiotic gonadotropin manufacturer founder promoter growth
D-NOME Pvt Ltd Hyderabad portable PCR manufacturer
Amplikon Biosystems Hyderabad diagnostic manufacturer founder
```

### Integrity Verification Queries
```
Sudarsanareddy Lokireddy PhD revoked NTU Singapore research fraud
Oncosimis Biotech Hyderabad CCMB research paper COVID antibody detection
```

---

## 2. Web Pages Fetched Directly

| URL | Purpose |
|---|---|
| https://www.clonzbio.com/about/management-clonz-bio/narasimha-rao-nedunuri/ | Founder bio verification |
| https://www.pathnsitu.com/aboutus.php | Company description + manufacturer claim |
| https://sapienbio.co.in/about-us/board-of-directors/ | Jugnu Jain credential verification |
| https://sapienbio.co.in/welcome/ | Company founding announcement |
| https://pharmchoices.com/biotech-companies-in-hyderabad-telangana-2/ | Raw company universe |

---

## 3. AI Prompts Used in Research

### Company Universe Generation
```
"List biotech and diagnostics companies in Hyderabad India that manufacture 
their own products. Include only companies with physical manufacturing 
operations, not CROs or testing labs. Focus on: specialty biotech, 
recombinant proteins, diagnostic kits, genomics tools, enzyme manufacturers."
```

### Scoring Consistency Check
```
"For each company, score C1 through C6 using this rubric:
C1 = 10 if own manufacturing confirmed, 5 if partial, 0 if service only.
C4 = 20 if PhD/IIT/research founder with evidence, 10 if technical but 
moderate, 0 if MBA/admin only.
Flag any scoring where the evidence doesn't support the score."
```

### Personalization Hook Generation
```
"Write a 2-3 sentence personalization hook for outreach to [COMPANY] that:
1. References a specific recent product launch, certification, or funding event
2. Identifies the specific operational pain point they are likely facing
3. Ends with a question the founder would genuinely want to answer
Do not use generic language. Cite the specific event that triggers the pain point."
```

### Rejection Reasoning
```
"Evaluate whether [COMPANY] should be rejected as a Federer prospect.
Check for: CRO model, PE ownership, MNC subsidiary, government ownership, 
service-only revenue, too large (>500 employees).
If any rejection criterion is met, state which one and why it disqualifies 
the company. Do not use diplomatic language."
```

---

## 4. Limitations of AI-Assisted Research

| Limitation | How It Was Handled |
|---|---|
| AI can confabulate company revenue | All revenue cross-checked against Tracxn/Tofler/MCA with FY cited |
| Aggregators (RocketReach, ZoomInfo) are unreliable for Indian SME revenue | Used only for career history, not financials |
| LinkedIn full profiles are paywalled | Cross-referenced with company website bios and Facebook public profiles |
| AI cannot resolve name-based identity ambiguity | Flagged for manual verification (Oncosimis case) |
| Single-source company entries may be phantom companies | T3 confidence tier applied; flagged for MCA verification |

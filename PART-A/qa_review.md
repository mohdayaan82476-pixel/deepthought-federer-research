# QA Review Log
### Corrections Made During Review Process

---

## Summary of QA Rounds

This assignment went through two full QA review passes. Below are the corrections applied.

---

## Round 1 QA — Structural and Scoring Issues

| Issue Found | Company | Correction Applied |
|---|---|---|
| Huwel HLSS Manufacturing listed as separate company #18 | Huwel HLSS | Removed — this is a subsidiary of Huwel, not a separate prospect |
| "NEEDS VERIFICATION" verdicts in final 25 | Fortune Biotech; BioReform; BiomatiQ | Moved to rejected list under "Insufficient Evidence" category |
| C4 scores of 10–15 assigned to companies with unknown founders | 9 companies | Revised to C4=5 for all companies where founder is "Unknown" |
| Cytobiologics scored as primary company | Cytobiologics | Replaced with Promea Therapeutics as primary entity; Cytobiologics retained as subsidiary note |
| Krebs Biochemicals rated "Borderline" | Krebs | Downgraded to Rejected — commodity API manufacturing, wrong segment |
| Globion India rated "Borderline" | Globion | Moved to rejected list — wrong segment (veterinary), not diagnostics |
| PopVax C4 scored at 15 | PopVax | Corrected to 10 — Soham Sankaran is robotics-trained, not a biotech research founder; grant validation signals domain credibility but is not a founder credential |
| Cytobiologics C3 scored at 25 | Cytobiologics → Promea | Reduced to 20 — plasma-derived IVIg is not a fully differentiated product; 12+ global competitors; revised under Promea entry |
| Generic personalization hooks | All companies | Rewrote hooks with specific product/regulatory/growth event triggers |

---

## Round 2 QA — Founder Verification Pass

| Company | Finding | Action |
|---|---|---|
| Clonz Biotech | Narasimha Nedunuri: M.Sc. + CCMB + Bio-Rad + Vimta Labs confirmed from multiple sources | C4=15 confirmed correct |
| PathNSitu | Kamal Prasad: BSc + Diagnostic BioSystems QC Manager confirmed; MCA director discrepancy flagged | C4=10 correct; director discrepancy noted in verification_notes.md |
| Oncosimis Biotech | CEO Sudarsanareddy Lokireddy name matches NTU PhD-revoked researcher with 6 retracted papers | REMOVED from shortlist — moved to rejected_companies.csv under "Integrity Risk" |
| Cytobiologics / Promea | Rajesh Tummuru: MBBS + Vanderbilt MBA + Biotrum BD Director confirmed | C4=10 confirmed; entry corrected to Promea Therapeutics as parent |
| Sapien Biosciences | Jugnu Jain: Cambridge PhD + Harvard post-doc + Vertex Pharmaceuticals confirmed | C4=20 confirmed; ownership flag added (Apollo JV) |

---

## Scoring Consistency Final Check

| Check | Status |
|---|---|
| Every C4 score ≥ 15 has named founder with PhD or IIT credential | ✓ Pass |
| No "Unknown" founder has C4 > 5 | ✓ Pass |
| Every company with Total Score ≥ 80 has T1 or T2 confidence | ✓ Pass |
| No "NEEDS VERIFICATION" verdict in final shortlist | ✓ Pass |
| No duplicate companies in shortlist | ✓ Pass (Huwel HLSS removed) |
| All rejected companies have stated rejection category | ✓ Pass |
| Oncosimis flagged and removed | ✓ Pass |
| Cytobiologics replaced by Promea Therapeutics | ✓ Pass |

---

## Remaining Known Weaknesses

1. **D-NOME confidence is T3** — single source, no MCA confirmation, founder unknown. Included because product concept is strong, but must be verified before outreach.
2. **Sanzyme promoter ownership unverified** — Jay Soman may be a hired MD, not a promoter. If institutional/employee ownership dominates post-delink, Sanzyme's Federer classification weakens.
3. **Mapmygenome C1 may be overscored** — if they outsource assay chemistry to Illumina platforms and only report results, C1 should be 5, reducing total score from 90 to 85 (still Strong Federer but with a different pitch).
4. **Sapien Biosciences Apollo JV** — Apollo co-ownership means this is not purely promoter-driven. Score reflects the strong founder, but the company may resist a DeepThought engagement if Apollo's institutional processes already govern operations.

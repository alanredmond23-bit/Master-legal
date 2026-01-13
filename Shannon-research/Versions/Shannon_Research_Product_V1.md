# Shannon Research Product Deployment Guide - V1
**Case:** US v. Redmond, EDPA 24-376 (27 counts) + Bankruptcy (Judge Mayer)
**Date:** January 2026
**Classification:** PRIVILEGED & CONFIDENTIAL — ATTORNEY WORK PRODUCT

---

## EXECUTIVE SUMMARY

### Mission
Build a **tendency + predictability engine** for EDPA criminal and bankruptcy cases that enables:
1. Motion drafting acceleration (plug-and-play citable excerpts)
2. Predictive response planning (ABCD counter-punch trees)
3. Credibility pressure mapping (cooperators/agents/selection bias vulnerabilities)
4. Full docket mastery (criminal + bankruptcy cases, all attachments indexed)

### Hard Deliverables
| # | Deliverable | Format | Target |
|---|-------------|--------|--------|
| 1 | Master dataset | XLSX (14 tabs) | Completed workbook |
| 2 | Final report | 25-60 pages | PDF/DOCX |
| 3 | Citable paragraphs | Library (50-150) | Tab 11 + Appendix |
| 4 | ABCD prediction trees | By motion type | Tab 12 + Report |
| 5 | Docket + attachments | 100% indexed | Tab 13 + folders |

---

## PART 1: SWIMLANE EXECUTION ORDER

**CRITICAL RULE:** Complete ONE swimlane fully before starting the next. Do not mix.

| # | Swimlane | Target Count | Est. Hours | Definition of Done |
|---|----------|--------------|------------|-------------------|
| 1 | **Judge Schemel** (EDPA 10y) | 60 cases + 30 exemplars | 20-30 hrs | Case index + exemplars + 20 citable paragraphs + 10 ABCD trees |
| 2 | **Judge Mayer** (EDPA BK 10y) | 30 cases + 15 exemplars | 10-15 hrs | Case index + exemplars + 15 citable paragraphs + 5 ABCD trees |
| 3 | **EDPA DOJ House Style** (all judges 10y) | 90 cases + 30 exemplars | 30-40 hrs | Opposition templates + patterns + 20 citable paragraphs |
| 4 | **AUSA Dalke** (EDPA 10y) | 15 cases + 10 exemplars | 8-12 hrs | Profile + patterns + 10 citable paragraphs + 5 ABCD trees |
| 5 | **Agent Crawley** (EDPA 10y) | 15 matters + 10 exemplars | 8-12 hrs | AOPC patterns + Franks vulnerabilities + 10 citable paragraphs |
| 6 | **DOJ Nationwide Sample** (10y) | 40 matters + 20 exemplars | 15-25 hrs | Trends + 15 citable paragraphs + 5 ABCD trees |
| 7 | **Brady/Giglio/Napue Library** | 40 authorities + 20 applications | 10-15 hrs | Master library + Schemel exemplars |
| 8 | **Full Docket + Attachments** | 100% indexed | 6-12 hrs | Criminal + BK dockets complete |

**TOTAL: 107-161 hours (~4-6 weeks at 4-6 hrs/day)**

### Weekly Plan Template
| Week | Swimlanes | Hours |
|------|-----------|-------|
| Week 1 | Schemel (complete) | 25-30 |
| Week 2 | Mayer + Start EDPA DOJ | 25-30 |
| Week 3 | EDPA DOJ (complete) + Dalke | 30-35 |
| Week 4 | Crawley + Nationwide + Brady Library | 25-30 |
| Week 5 | Docket pulls + Final report drafting | 15-25 |

---

## PART 2: TOOL SOPS

### 2.1 WESTLAW EDGE SOP

#### Setup Checklist
- [ ] Confirm subscription includes Litigation Analytics
- [ ] Set jurisdiction filter: EDPA
- [ ] Set date range: Last 10 years
- [ ] Establish folder naming convention

#### STEP 1: Judge Analytics (Schemel / Mayer)
1. Navigate: **Specialty Areas → Litigation Analytics → Judges**
2. Search: "Schemel" + Court = EDPA + Date = last 10y
3. Export/Record:
   - Motion grant rates by type
   - Average time to rule
   - Case-type distribution
4. Screenshot the analytics dashboard
5. Repeat for Mayer (bankruptcy; if not supported, use docket-driven method)

#### STEP 2: Docket Universe Build
1. Navigate: **Dockets → Advanced Search**
2. Filters:
   - Court = EDPA
   - Judge = Schemel
   - Date = last 10y
3. Export case list fields: case number, caption, filed/closed, nature
4. For each relevant case:
   - Open docket report
   - Filter to key motion types: suppress, Franks, Brady/Giglio compel, continuance, sever, Rule 12
   - Download PDFs: motion/opposition/reply/order + exhibits

#### STEP 3: DOJ-only Subset
- Same query + Party = "United States" (or "USA")
- Tag in workbook as "DOJ case"

#### STEP 4: EDPA DOJ House Style (All Judges)
- Court = EDPA; Party = USA; Date = last 10y
- Sample minimum 30 per motion type:
  - Continuance opposition
  - Brady/Giglio timing fights
  - Suppression/Franks opposition
  - Severance opposition

#### STEP 5: Dalke / Crawley
**Dalke:**
- Search dockets by attorney name
- Export cases
- Pull motions/oppositions he authored

**Crawley:**
- Search within documents: "Crawley" AND "Affidavit" AND "probable cause"
- Collect AOPCs and Franks/suppression litigation

#### STEP 6: Export + Storage Standard
```
/Research_Product/
├── Schemel/{case_number}/
├── Mayer/{case_number}/
├── EDPA_DOJ/{case_number}/
├── Dalke/{case_number}/
└── Crawley/{case_number}/
```

**Naming Convention:**
`YYYY-MM-DD_Docket#_DocType_Party_ShortTitle.pdf`

**Example:** `2024-03-15_Doc45_MotSuppress_USA_Jones.pdf`

---

### 2.2 COCOUNSEL 2.0 SOP

#### Skills to Use
| Skill | Purpose |
|-------|---------|
| **Summarize** (detailed) | Extract motion type, standard, outcome |
| **Timeline** | Procedural chronology |
| **Review Documents** | Q&A across packet |
| **Compare Documents** | Motion vs opposition; affidavit vs contradictions |
| **Prepare for Deposition** | Credibility question sets |

#### Work Unit Definition
**ONE work unit = ONE exemplar packet:**
- Motion + Opposition + Reply + Order (+ transcript if available)
- Process ONE at a time. Do not batch.

#### Prompt Templates (Copy/Paste Ready)

**EXTRACTION PROMPT:**
```
Extract from this packet:
(a) motion type
(b) legal standard applied (quote with pinpoint cite)
(c) judge's reasoning
(d) facts relied upon
(e) outcome
(f) timeline
(g) best 3 citable paragraphs with pinpoint cites
(h) what strategy caused the outcome

Output as a table.
```

**CODING PROMPT:**
```
Tag the outcome as Granted/Denied/Part.
Identify whether court:
- criticized DOJ
- ordered a hearing
- compelled discovery
- dismissed counts
- suppressed evidence
- imposed sanctions
```

**ABCD TREE PROMPT:**
```
Based on this exemplar, predict DOJ's likely response to a similar motion.
Output an ABCD tree:
A: DOJ likely move
B: Defense response
C: DOJ escalation
D: Defense counter (hearing request / order language)
```

**QUOTE HARVESTING PROMPT:**
```
Extract 1-3 paragraphs verbatim that:
- A judge could adopt into an order
- Support our motion position
- Criticize DOJ conduct or reasoning

Include exact page/paragraph pinpoint citation.
```

**CREDIBILITY/BIAS PROMPT:**
```
Identify any language discussing:
- Cooperator credibility issues
- Selection bias in evidence presentation
- Omissions in affidavits
- Agent methodology criticism

Quote verbatim with pinpoints.
```

#### Quality Control Rules
- [ ] Verify every citation against PDF page/paragraph
- [ ] If using a quote, capture EXACT pinpoint
- [ ] Do not rely on summaries—confirm in source PDF
- [ ] Update workbook tab immediately after processing

---

### 2.3 COST STRATEGY: WESTLAW vs PACER

#### PACER Facts (Accurate)
| Rule | Detail |
|------|--------|
| Base cost | $0.10 per page |
| Document cap | $3.00 per document (30 pages) |
| Cap exceptions | Transcripts, searches, non-case-specific reports |
| Fee waiver | Fees waived if ≤$30/quarter |
| Transcript note | No 30-page cap; often no "free look" |

#### Decision Matrix

| Task | Tool | Why |
|------|------|-----|
| Judge tendencies/time-to-rule | Westlaw Edge | Litigation Analytics |
| Attorney success rate proxies | Westlaw Edge | Attorney Analytics |
| Targeted exemplars (speed matters) | Westlaw Edge | Better search |
| Full docket pull | PACER | Cheaper ($3 cap) |
| Bulk attachments | PACER | Predictable cost |
| Our case docket + attachments | PACER | Complete record |
| Automated alerts | Monitoring tool | If subscription economics justify |

#### 12 Rules to Control PACER Costs
1. Always preview billable pages before downloading
2. Use $3 cap to your advantage—download full docs, not partial
3. Avoid uncapped searches (use Westlaw for search, PACER for docs)
4. Track quarterly spend—stay under $30 if possible
5. Transcripts: consider buying from reporter if cheaper
6. Batch downloads in single session to track costs
7. Don't re-download—save everything first time
8. Use case-specific reports (capped) over general reports (uncapped)
9. Export docket sheet before pulling individual attachments
10. Never run speculative searches on PACER
11. Set browser to confirm before each download
12. Reconcile downloaded files against docket entry count

---

## PART 3: WORKBOOK SPECIFICATION

### Tab Structure + Colors

| Tab | Color | Hex | Purpose |
|-----|-------|-----|---------|
| 00_README | Gray | #404040 | Instructions |
| 01_Swimlanes_Plan | Navy | #1F4E79 | Progress tracking |
| 02_Schemel_CaseIndex | Green | #00B050 | Case list |
| 03_Schemel_Exemplars | Green | #00B050 | Motion packets |
| 04_Mayer_CaseIndex | Blue | #00B0F0 | BK case list |
| 05_Mayer_Exemplars | Blue | #00B0F0 | BK motion packets |
| 06_EDPA_DOJ_CaseIndex | Gold | #FFC000 | DOJ house style |
| 07_DOJ_Nationwide_Sample | Gold | #FFC000 | National trends |
| 08_Dalke_Profile | Red | #C00000 | AUSA patterns |
| 09_Crawley_Profile | Red | #C00000 | Agent patterns |
| 10_Brady_Giglio_Napue_Library | Purple | #7030A0 | Disclosure law |
| 11_Most_Citable_Paragraphs | Purple | #7030A0 | Quote bank |
| 12_Prediction_Engine | Dark Blue | #002060 | ABCD trees |
| 13_Docket_Attachments_Index | Black | #000000 | Full docket |

### Column Headers by Tab

#### 02_Schemel_CaseIndex / 04_Mayer_CaseIndex / 06_EDPA_DOJ_CaseIndex
| A | B | C | D | E | F | G | H | I | J | K | L |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Case# | Caption | Filed | Closed | Nature | Judge | Key Motions | Outcome | Tags | PDF Path | Notes | Status |

#### 03_Schemel_Exemplars / 05_Mayer_Exemplars
| A | B | C | D | E | F | G | H | I | J | K |
|---|---|---|---|---|---|---|---|---|---|---|
| Case# | Motion Type | Standard Applied | Facts Relied Upon | Outcome | Reasoning | What Won | Citable Quote | Pinpoint Cite | PDF Path | ABCD Tree Done |

#### 08_Dalke_Profile / 09_Crawley_Profile
| A | B | C | D | E | F | G | H | I | J | K | L |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Case# | Caption | Date | Document Type | Key Arguments | Citations Used | Language Patterns | Judge Response | Outcome | Vulnerabilities | PDF Path | Notes |

#### 11_Most_Citable_Paragraphs
| A | B | C | D | E | F | G | H | I |
|---|---|---|---|---|---|---|---|---|
| Source Case | Motion Type | Use Case | Verbatim Quote | Pinpoint Cite | What It Proves | Judge | AUSA | Tags |

#### 12_Prediction_Engine
| A | B | C | D | E | F | G | H | I |
|---|---|---|---|---|---|---|---|---|
| Motion Type | Actor | A: DOJ Move | B: Defense Response | C: DOJ Escalation | D: Defense Counter | Source Exemplar | Confidence | Notes |

### Entry Rules
- **No blank required fields** (Case#, Motion Type, Outcome always filled)
- **Pinpoint cites required** for all quotes (page/paragraph)
- **PDF paths must be valid** and match folder structure
- **Tags use consistent taxonomy** (see below)

### Tag Taxonomy
```
MOTION TYPES: continuance, compel, suppress, franks, sever, rule12, brady, giglio, sanctions
OUTCOMES: granted, denied, partial, hearing-ordered, dismissed
TRIGGERS: doj-criticized, discovery-compelled, evidence-suppressed, counts-dismissed
ACTORS: schemel, mayer, dalke, crawley, doj-edpa, doj-nationwide
```

---

## PART 4: ADDITIONAL RESEARCH ARTIFACTS

### A. DOJ Opposition Template Library
**Purpose:** Predict DOJ arguments by capturing their boilerplate

**Outputs:**
1. Categorized opposition outlines by motion type
2. Verbatim standard paragraphs with pinpoints
3. Favorite authorities cited
4. Predictive checklist: what DOJ argues first, concedes, uses as fallback
5. Counter-module mapping: DOJ paragraph → Defense counter

### B. Judge Citation Fingerprint (Schemel)
**Purpose:** Build "judge persuasion map"

**Outputs:**
- Top cited cases by Judge Schemel (overall + by motion category)
- Top legal topics/Key Numbers in his crim-pro opinions
- "Trigger authorities": cases he reaches for when granting vs denying
- Shortlist: 20-40 citable cases most likely to resonate

### C. Appeals Sensitivity Profile
**Purpose:** Frame relief to avoid reversal

**Outputs:**
- Categories where rulings commonly appealed
- Affirmed/reversed rates (where available)
- "Safe relief" vs "risk relief" framing recommendations

### D. Standing Orders / Chamber Rules Pack
**Purpose:** Avoid procedural losses

**Outputs:**
- Schemel procedural preferences
- Mayer procedural preferences
- EDPA local rules on continuances, discovery, sealing, page limits
- Filing compliance checklist

### E. Discovery Dispute Outcomes Dataset
**Purpose:** Support Day 10/20/30/45/60 schedule argument

**Outputs:**
- Dataset: case, judge, dispute type, outcome
- Best paragraph from each order
- Trend summary: what's "reasonable" production timing

### F. Cooperator Credibility Pattern Book
**Purpose:** Map Giglio attack vectors

**Outputs:**
- Credibility attacks courts credit
- Disclosure items courts order (benefits, payments, 302 drafts)
- Exemplar orders requiring additional Giglio disclosures
- Question bank for meet-and-confer "pin-downs"

### G. Affidavit Construction & Selection-Bias Playbook
**Purpose:** Franks/suppression readiness

**Outputs:**
- Taxonomy of omission types (context, regulator, timing, alternative explanation)
- Taxonomy of selection bias (clipping, non-random, "most egregious," ignoring verification)
- Exemplar rulings with quotes + pinpoints

### H. PACER Full-Docket Pull SOP
**Purpose:** Efficient bulk downloads

**Outputs:**
- Step-by-step docket + attachment pull
- Naming convention
- "Avoid these traps" checklist
- QC: entry count vs file count reconciliation

### I. CoCounsel Bulk-Extraction Pack
**Purpose:** Fast structured extraction

**Outputs:**
- 12 reusable prompts:
  - 1-4: Judge order extraction
  - 5-8: Motion/opposition structure extraction
  - 9-10: Affidavit vs record compare
  - 11-12: ABCD prediction trees

### J. DOJ Posture Shift Signals
**Purpose:** Predict posture changes from docket activity

**Outputs:**
- Docket events correlating with posture changes
- Weekly checklist for our dockets
- "Likely next DOJ move" field for prediction engine

### K. Mayer Bankruptcy Tendency Pack
**Purpose:** BK-specific analysis

**Outputs:**
- Outcome tendencies by motion type
- Standard paragraphs he uses
- Best citable orders with pinpoints
- Prediction trees for UST/SBA/trustee moves

### L. Weekly Intel Update Loop
**Purpose:** Keep engine current

**Outputs:**
- 30-minute weekly checklist
- Intake rules for new filings
- Where to log changes in workbook
- When to trigger new exemplar extraction
- When to update ABCD trees

---

## PART 5: FINAL REPORT TEMPLATE

### Structure (25-60 pages)

1. **Executive Summary** (2-3 pages)
   - Top 10 predictable DOJ moves + our counters
   - Top 10 leverage moves
   - Key findings snapshot

2. **Judge Schemel Profile** (5-8 pages)
   - Grant/deny patterns by motion type
   - Trigger phrases and reasoning patterns
   - Time-to-rule analysis
   - Exemplar quotes (top 10)

3. **Judge Mayer Profile** (4-6 pages)
   - Bankruptcy tendencies
   - Sanctions posture
   - SBA/trustee/UST dynamics
   - Exemplar quotes (top 5)

4. **EDPA DOJ House Style** (5-8 pages)
   - Common opposition structure
   - Delay tactics and timing patterns
   - Discovery posture
   - Favorite authorities

5. **AUSA Dalke Profile** (3-5 pages)
   - Argument templates
   - Citation patterns
   - Language fingerprint
   - Predicted counters

6. **Agent Crawley Profile** (3-5 pages)
   - Affidavit sourcing patterns
   - Selection methodology
   - Omission types
   - Franks vulnerabilities

7. **DOJ Nationwide Trends** (3-5 pages)
   - Brady/Giglio/Napue enforcement patterns
   - Franks outcomes nationally
   - Continuance posture in complex cases

8. **ABCD Prediction Trees** (5-10 pages)
   - By motion type: continuance, compel, franks, suppress, sever
   - By actor: DOJ, judge, agent

9. **Appendix: Most Citable Paragraphs** (10-20 pages)
   - 50-150 excerpts organized by use case
   - Full pinpoint citations

### Style Requirements
- Clinical, evidence-driven
- Tables and bullet summaries
- Pinpoint citations to PDFs
- No speculation—only documented patterns
- Verbatim quotes where possible

---

## PART 6: QUALITY GATES

### Per-Swimlane Checklist
Before marking swimlane complete:
- [ ] Case index 100% filled (all required fields)
- [ ] All exemplars saved with correct naming
- [ ] All coded tags complete and consistent
- [ ] Minimum citable paragraphs extracted
- [ ] ABCD trees created (5-10 per swimlane)
- [ ] Cross-checked citations against source PDFs
- [ ] Workbook tab updated and saved

### Final QC Checklist
Before final report delivery:
- [ ] All 14 workbook tabs complete
- [ ] All target counts met or exceeded
- [ ] All quotes verified against source
- [ ] All PDFs organized in folder structure
- [ ] All ABCD trees have source exemplar reference
- [ ] Report formatted consistently
- [ ] Appendix pagination correct

---

## APPENDIX A: LEGAL ANCHORS (Must Cite Accurately)

| Doctrine | Citation | Key Rule |
|----------|----------|----------|
| Speedy Trial "Ends of Justice" | 18 U.S.C. § 3161(h)(7)(A)-(B) | Continuances require on-record findings |
| Franks | Franks v. Delaware, 438 U.S. 154 (1978) | Substantial preliminary showing of knowing/reckless falsity |
| Leon Good Faith | United States v. Leon, 468 U.S. 897 (1984) | Does not apply when judge misled by Franks defect |
| Brady | Brady v. Maryland, 373 U.S. 83 (1963) | Government must disclose exculpatory evidence |
| Giglio | Giglio v. United States, 405 U.S. 150 (1972) | Must disclose impeachment evidence |
| Napue | Napue v. Illinois, 360 U.S. 264 (1959) | Duty to correct false testimony |

---

## APPENDIX B: FILE NAMING CONVENTIONS

### PDF Documents
`YYYY-MM-DD_Docket#_DocType_Party_ShortTitle.pdf`

**DocType codes:**
- `Mot` = Motion
- `Opp` = Opposition
- `Rep` = Reply
- `Ord` = Order
- `Op` = Opinion
- `Aff` = Affidavit/AOPC
- `Tr` = Transcript
- `Ex` = Exhibit

**Examples:**
- `2024-03-15_Doc45_MotSuppress_Def_Jones.pdf`
- `2024-03-22_Doc52_OppSuppress_USA_Jones.pdf`
- `2024-04-10_Doc67_OrdSuppress_Ct_Jones.pdf`

### Folders
```
/Research_Product/
├── 01_Schemel/
│   ├── 24-cr-123/
│   └── 23-cr-456/
├── 02_Mayer/
├── 03_EDPA_DOJ/
├── 04_Dalke/
├── 05_Crawley/
├── 06_Nationwide/
├── 07_Brady_Giglio/
└── 08_Our_Cases/
    ├── Criminal_24-376/
    └── Bankruptcy/
```

---

*Classification: PRIVILEGED & CONFIDENTIAL — ATTORNEY WORK PRODUCT*
*Case: US v. Redmond, EDPA 24-376*

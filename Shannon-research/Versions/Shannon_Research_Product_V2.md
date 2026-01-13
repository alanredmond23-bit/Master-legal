# Shannon Research Product Deployment Guide - V2
**Case:** US v. Redmond, EDPA 24-376 (27 counts) + Bankruptcy (Judge Mayer)
**Date:** January 2026
**Classification:** PRIVILEGED & CONFIDENTIAL — ATTORNEY WORK PRODUCT

---

## EXECUTIVE SUMMARY

### Mission
Build a **tendency + predictability engine** for EDPA criminal and bankruptcy cases in **5 working days**.

### Hard Deliverables
| # | Deliverable | Format | Day Due |
|---|-------------|--------|---------|
| 1 | Master dataset | XLSX (14 tabs) | Day 4 |
| 2 | Final report | 25-60 pages | Day 5 |
| 3 | Citable paragraphs | Library (50-150) | Day 3 |
| 4 | ABCD prediction trees | By motion type | Day 4 |
| 5 | Docket + attachments | 100% indexed | Day 4 |

### 5-Day Sprint Schedule
| Day | Focus | Output |
|-----|-------|--------|
| **DAY 1** | Schemel + Mayer | Case indexes + 20 exemplars + 15 citable quotes |
| **DAY 2** | Crawley + Dalke + DOJ EDPA | Profiles + patterns + 15 citable quotes |
| **DAY 3** | Nationwide + Motion Library | Trends + doctrine library + 20 citable quotes |
| **DAY 4** | Dockets + ABCD trees | 100% dockets indexed + prediction engine |
| **DAY 5** | Final report + QC | 25-60 page report + verified workbook |

**TOTAL: 38-40 hours over 5 days**

---

# STEP ONE: SETUP (Day 1 Morning - 1 hour)

## 1.1 Create Westlaw Folder Hierarchy

In Westlaw Edge, create this folder structure:
```
📁 EDPA_24-376_Research/
├── 📁 01_Judges/
│   ├── 📁 Schemel_Cases/
│   └── 📁 Mayer_Cases/
├── 📁 02_Prosecutors/
│   ├── 📁 Dalke_Cases/
│   └── 📁 Crawley_AOPCs/
├── 📁 03_DOJ_Patterns/
│   ├── 📁 EDPA_Oppositions/
│   └── 📁 Nationwide_Sample/
├── 📁 04_Motion_Library/
│   ├── 📁 Brady_Giglio/
│   ├── 📁 Franks/
│   ├── 📁 Selective_Vindictive/
│   ├── 📁 Daubert/
│   └── 📁 MTD/
└── 📁 05_Our_Dockets/
    ├── 📁 Criminal_24-376/
    └── 📁 Bankruptcy/
```

## 1.2 Configure CoCounsel Database

1. Open CoCounsel → "Search a Database" skill
2. Create new database: `EDPA_24376_Research_[YYYYMMDD]`
3. Set up tags using motion codes M01-M12 (see Motion Types below)

## 1.3 Set Up Workbook

1. Open `EDPA_Intel_Workbook_V2.xlsx`
2. Verify all 14 tabs present
3. Enable auto-filter on all column headers
4. Set freeze panes on row 1

## 1.4 Confirm Subscriptions

- [ ] Westlaw Edge with Litigation Analytics
- [ ] CoCounsel 2.0 access
- [ ] PACER account active

---

# STEP TWO: JUDGE SCHEMEL DEEP DIVE (Day 1 - 4 hours)

## 2.1 Pull Judge Analytics Dashboard

1. Navigate: **Westlaw → Litigation Analytics → Judges**
2. Search: `Schemel` + Court = EDPA + Date = last 10 years
3. Export/screenshot:
   - Motion grant rates by type
   - Average time to rule
   - Case-type distribution
4. Save to: `01_Judges/Schemel_Cases/Analytics_Screenshot.png`

## 2.2 Build Case Index (Target: 60 cases)

1. Navigate: **Westlaw → Dockets → Advanced Search**
2. Filters:
   - Court = EDPA
   - Judge = Schemel
   - Date = last 10 years
   - Nature = Criminal
3. Export case list to Tab `02_Schemel_CaseIndex`
4. Fill all columns: Case#, Caption, Filed, Closed, Nature, Judge, Key Motions, Outcome

## 2.3 Extract 15 Exemplars

For each relevant case with key motions:
1. Download: Motion + Opposition + Reply + Order
2. Save to folder: `01_Judges/Schemel_Cases/{case_number}/`
3. Use naming: `YYYY-MM-DD_Doc#_DocType_Party_ShortTitle.pdf`
4. Log in Tab `03_Schemel_Exemplars`

## 2.4 Harvest 10 Citable Paragraphs

Use CoCounsel with this prompt:
```
Extract 1-3 paragraphs verbatim that:
- A judge could adopt into an order
- Support our motion position
- Criticize DOJ conduct or reasoning

Include exact page/paragraph pinpoint citation.
```

Log in Tab `11_Most_Citable_Paragraphs`

---

# STEP THREE: JUDGE MAYER ANALYSIS (Day 1 - 3 hours)

## 3.1 Pull Bankruptcy Case List

1. Navigate: **Westlaw → Dockets → Advanced Search**
2. Filters:
   - Court = EDPA Bankruptcy
   - Judge = Mayer
   - Date = last 10 years
3. If Litigation Analytics unavailable, use docket-driven method

## 3.2 Build Case Index (Target: 30 cases)

1. Export to Tab `04_Mayer_CaseIndex`
2. Focus on: adversary proceedings, sanctions, SBA/UST matters

## 3.3 Extract 10 Exemplars

1. Download motion packets for key rulings
2. Save to: `01_Judges/Mayer_Cases/{case_number}/`
3. Log in Tab `05_Mayer_Exemplars`

## 3.4 Harvest 5 Citable Paragraphs

Same CoCounsel prompt as Step 2.4
Log in Tab `11_Most_Citable_Paragraphs`

---

# STEP FOUR: AGENT CRAWLEY PROFILE (Day 2 - 3 hours)

## 4.1 Search for All Crawley Affidavits

1. Navigate: **Westlaw → Search within documents**
2. Query: `"Crawley" AND "Affidavit" AND "probable cause"`
3. Filter: EDPA, last 10 years

## 4.2 Index AOPC Patterns

For each affidavit found:
1. Note: Sources cited, methodology, language patterns
2. Log in Tab `09_Crawley_Profile`
3. Flag any: omissions, cherry-picking, selection bias

## 4.3 Flag Franks Vulnerabilities

Look for:
- Context omissions
- Timing manipulations
- Alternative explanation ignored
- Regulator findings mischaracterized

## 4.4 Extract 10 Citable Paragraphs

CoCounsel prompt:
```
Identify any language discussing:
- Agent methodology criticism
- Omissions in affidavits
- Selection bias in evidence presentation

Quote verbatim with pinpoints.
```

---

# STEP FIVE: AUSA DALKE PROFILE (Day 2 - 2 hours)

## 5.1 Pull Dalke Case History

1. Search dockets by attorney name: `Dalke`
2. Export cases to Tab `08_Dalke_Profile`
3. Target: 15 cases minimum

## 5.2 Map Argument Templates

For each case:
1. Pull motions/oppositions Dalke authored
2. Note: Opening arguments, favorite citations, language patterns
3. Identify: What he concedes, what he fights hardest

## 5.3 Extract 5 Citable Paragraphs

Focus on: Dalke losses, judge criticisms, successful defense counters

---

# STEP SIX: DOJ EDPA HOUSE STYLE (Day 2 - 3 hours)

## 6.1 Sample 30 Oppositions by Motion Type

Target minimum per type:
- Continuance opposition: 8
- Brady/Giglio opposition: 8
- Suppression/Franks opposition: 8
- Severance opposition: 6

## 6.2 Document Boilerplate Patterns

Create template library:
1. Standard opening paragraphs
2. Favorite authorities cited
3. Typical concession language
4. Fallback arguments

## 6.3 Build Counter-Argument Matrix

| DOJ Argument | Our Counter | Source Case |
|--------------|-------------|-------------|
| [Pattern 1] | [Response] | [Citation] |

Log in Tab `06_EDPA_DOJ_CaseIndex`

---

# STEP SEVEN: DOJ NATIONWIDE TRENDS (Day 3 - 4 hours)

## 7.1 Sample 40 Matters Across Districts

1. Search: Brady/Giglio/Franks motions nationwide
2. Filter: Last 5 years, favorable defense outcomes
3. Target districts: SDNY, CDCA, NDGA, EDVA

## 7.2 Identify National Patterns

Compare to EDPA norms:
- Grant rates
- Hearing frequency
- Discovery timelines
- Sanctions frequency

## 7.3 Log to Tab `07_DOJ_Nationwide_Sample`

---

# STEP EIGHT: MOTION DOCTRINE LIBRARY (Day 3 - 4 hours)

## 8.1 Build Authority List for All 12 Motion Types

| Code | Motion Type | Priority | Key Authority |
|------|-------------|----------|---------------|
| M01 | Brady/Giglio Motion to Compel | 4 | Brady v. Maryland, 373 U.S. 83 |
| M02 | Franks Motion + Suppression | 4 | Franks v. Delaware, 438 U.S. 154 |
| M03 | Vindictive/Selective Prosecution | 3 | United States v. Armstrong, 517 U.S. 456 |
| M04 | Improper Prosecutorial Appointment | 5 | 28 U.S.C. § 541 |
| M05 | Compel Discovery Status Order | 3 | Fed. R. Crim. P. 16 |
| M06 | Daubert Challenges | 2 | Daubert v. Merrell Dow, 509 U.S. 579 |
| M07 | Motions in Limine | 2 | Fed. R. Evid. 403 |
| M08 | Continuance Motion | 1 | 18 U.S.C. § 3161 |
| M09 | Count-by-Count MTD | 4 | Fed. R. Crim. P. 12(b) |
| M10 | Sanctions Motion | 3 | Fed. R. Crim. P. 16(d) |
| M11 | Napue (False Testimony) | 4 | Napue v. Illinois, 360 U.S. 264 |
| M12 | Leon Good Faith Exception | 3 | United States v. Leon, 468 U.S. 897 |

## 8.2 Extract Key Holdings

For each motion type, identify:
1. Elements/standard
2. Burden of proof
3. Schemel's interpretation (if any)
4. Best quote for our facts

## 8.3 Map to Our Case Facts

Create application matrix in Tab `10_Motion_Doctrine_Library`

---

# STEP NINE: DOCKET MASTERY (Day 4 - 5 hours)

## 9.1 Pull 100% Criminal Docket (24-376)

1. Login to PACER
2. Pull full docket sheet for case 24-376
3. Download ALL attachments
4. Budget: ~$50-100 (stay under $3/doc cap)

## 9.2 Pull 100% Bankruptcy Docket

Same process for bankruptcy case

## 9.3 Index All Attachments

Log every document in Tab `13_Docket_Attachments_Index`:
- Docket entry number
- Date
- Description
- File path
- Relevance tag

## 9.4 Reconcile Entry Count vs File Count

**CRITICAL QC:** Docket entry count MUST equal file count
- If mismatch, identify missing docs
- Re-download any gaps

---

# STEP TEN: PREDICTION ENGINE (Day 4 - 3 hours)

## 10.1 Build ABCD Trees by Motion Type

For each of the 12 motion types, create tree:
```
A: DOJ likely move
B: Defense response
C: DOJ escalation
D: Defense counter (hearing request / order language)
```

Use CoCounsel prompt:
```
Based on this exemplar, predict DOJ's likely response to a similar motion.
Output an ABCD tree:
A: DOJ likely move
B: Defense response
C: DOJ escalation
D: Defense counter (hearing request / order language)
```

## 10.2 Map DOJ Likely Moves

Cross-reference:
- Dalke patterns (Tab 08)
- DOJ EDPA house style (Tab 06)
- Historical outcomes (Schemel tendencies)

## 10.3 Script Defense Counters

Log all trees in Tab `12_Prediction_Engine`

---

# STEP ELEVEN: FINAL REPORT (Day 5 - 6 hours)

## 11.1 Compile All Sections

Report Structure (25-60 pages):
1. Executive Summary (2-3 pages)
2. Judge Schemel Profile (5-8 pages)
3. Judge Mayer Profile (4-6 pages)
4. EDPA DOJ House Style (5-8 pages)
5. AUSA Dalke Profile (3-5 pages)
6. Agent Crawley Profile (3-5 pages)
7. DOJ Nationwide Trends (3-5 pages)
8. ABCD Prediction Trees (5-10 pages)
9. Appendix: Most Citable Paragraphs (10-20 pages)

## 11.2 Verify All Citations

**CRITICAL:** Every quote must be verified against source PDF
- Check page numbers
- Check paragraph numbers
- Confirm exact wording

## 11.3 Format Appendices

Organize citable paragraphs by:
1. Motion type
2. Use case
3. Judge

## 11.4 Quality Control Checklist

Before delivery:
- [ ] All 14 workbook tabs complete
- [ ] All target counts met or exceeded
- [ ] All quotes verified against source
- [ ] All PDFs organized in folder structure
- [ ] All ABCD trees have source exemplar reference
- [ ] Report formatted consistently
- [ ] Appendix pagination correct

---

## DAILY WORKFLOW PATTERN

```
EACH DAY:
Morning (3 hrs):   GRAB → Document collection from Westlaw/PACER
Midday (3 hrs):    ANALYZE → CoCounsel extraction + coding
Afternoon (2 hrs): RECORD → Update spreadsheet + verify cites
```

---

## TOOL SOPS

### Westlaw Edge SOP

#### Judge Analytics
1. Navigate: **Specialty Areas → Litigation Analytics → Judges**
2. Search: Judge name + Court + Date range
3. Export: Grant rates, time-to-rule, case distribution

#### Docket Search
1. Navigate: **Dockets → Advanced Search**
2. Filters: Court, Judge, Date, Nature
3. Export: Case list with all fields

#### DOJ Subset
- Add filter: Party = "United States" or "USA"
- Tag in workbook as "DOJ case"

### CoCounsel 2.0 SOP

#### Skills to Use
| Skill | Purpose |
|-------|---------|
| **Summarize** | Extract motion type, standard, outcome |
| **Timeline** | Procedural chronology |
| **Review Documents** | Q&A across packet |
| **Compare Documents** | Motion vs opposition |
| **Search a Database** | Query uploaded documents |

#### Prompt Templates

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

**ABCD TREE PROMPT:**
```
Based on this exemplar, predict DOJ's likely response.
Output:
A: DOJ likely move
B: Defense response
C: DOJ escalation
D: Defense counter
```

**QUOTE HARVESTING PROMPT:**
```
Extract 1-3 paragraphs verbatim that:
- A judge could adopt into an order
- Support our motion position
- Criticize DOJ conduct

Include exact page/paragraph pinpoint citation.
```

### Spreadsheet vs CoCounsel Decision

**USE BOTH:**
- CoCounsel: Document analysis, quote extraction, timeline building
- Spreadsheet: Structured tracking, cross-referencing, final output

**WHY BOTH:**
- CoCounsel can't export structured data well
- Spreadsheet can't analyze PDFs
- Workflow: CoCounsel EXTRACT → Spreadsheet TRACK

---

## COST STRATEGY

### PACER Rules
| Rule | Detail |
|------|--------|
| Base cost | $0.10 per page |
| Document cap | $3.00 per document (30 pages) |
| Fee waiver | Fees waived if ≤$30/quarter |
| Transcript note | No 30-page cap |

### Decision Matrix
| Task | Tool | Why |
|------|------|-----|
| Judge tendencies | Westlaw Edge | Litigation Analytics |
| Targeted exemplars | Westlaw Edge | Better search |
| Full docket pull | PACER | Cheaper ($3 cap) |
| Our case docket | PACER | Complete record |

---

## WORKBOOK SPECIFICATION

### Tab Structure
| Tab | Color | Purpose |
|-----|-------|---------|
| 00_README | #404040 | Instructions |
| 01_Swimlanes_Plan | #1F4E79 | Progress tracking |
| 02_Schemel_CaseIndex | #00B050 | Judge case list |
| 03_Schemel_Exemplars | #00B050 | Motion packets |
| 04_Mayer_CaseIndex | #00B0F0 | BK case list |
| 05_Mayer_Exemplars | #00B0F0 | BK motion packets |
| 06_EDPA_DOJ_CaseIndex | #FFC000 | DOJ house style |
| 07_DOJ_Nationwide_Sample | #FFC000 | National trends |
| 08_Dalke_Profile | #C00000 | AUSA patterns |
| 09_Crawley_Profile | #C00000 | Agent patterns |
| 10_Motion_Doctrine_Library | #7030A0 | All 12 motion types |
| 11_Most_Citable_Paragraphs | #7030A0 | Quote bank |
| 12_Prediction_Engine | #002060 | ABCD trees |
| 13_Docket_Attachments_Index | #000000 | Full docket |

### Tag Taxonomy
```
MOTION TYPES: brady-giglio, franks, vindictive, appointment, compel-discovery, daubert, limine, continuance, mtd-counts, sanctions, napue, leon
OUTCOMES: granted, denied, partial, hearing-ordered, dismissed
ACTORS: schemel, mayer, dalke, crawley, doj-edpa, doj-nationwide
```

---

## GLOSSARY: KEY LEGAL TERMS

| Term | Definition | Citation |
|------|------------|----------|
| **302** | FBI interview report form | FBI FD-302 |
| **AOPC** | Application for Order Permitting Capture (wiretap/surveillance warrant) | 18 U.S.C. § 2518 |
| **Brady Material** | Evidence favorable to the accused that is material to guilt or punishment | Brady v. Maryland, 373 U.S. 83 (1963) |
| **Daubert Standard** | Federal standard for admissibility of expert testimony based on reliability | Daubert v. Merrell Dow, 509 U.S. 579 (1993) |
| **Franks Hearing** | Evidentiary hearing to challenge false statements in warrant affidavits | Franks v. Delaware, 438 U.S. 154 (1978) |
| **Giglio Material** | Impeachment evidence about government witnesses | Giglio v. United States, 405 U.S. 150 (1972) |
| **Good Faith Exception (Leon)** | Exception to exclusionary rule when officers rely on facially valid warrant | United States v. Leon, 468 U.S. 897 (1984) |
| **Motion in Limine** | Pre-trial motion to exclude prejudicial evidence | Fed. R. Evid. 403 |
| **MTD** | Motion to Dismiss | Fed. R. Crim. P. 12(b) |
| **Napue Violation** | Using or failing to correct known false testimony | Napue v. Illinois, 360 U.S. 264 (1959) |
| **Rule 16** | Criminal discovery rule requiring government disclosure | Fed. R. Crim. P. 16 |
| **Selective Prosecution** | Defense claiming defendant singled out based on protected class | United States v. Armstrong, 517 U.S. 456 (1996) |
| **Speedy Trial Act** | Statutory time limits for federal criminal trials | 18 U.S.C. § 3161 |
| **USSG** | United States Sentencing Guidelines | USSG Manual |
| **Vindictive Prosecution** | Defense claiming prosecution was retaliation for exercising rights | Blackledge v. Perry, 417 U.S. 21 (1974) |

---

## FILE NAMING CONVENTIONS

### PDF Documents
`YYYY-MM-DD_Doc#_DocType_Party_ShortTitle.pdf`

**DocType codes:**
- `Mot` = Motion
- `Opp` = Opposition
- `Rep` = Reply
- `Ord` = Order
- `Aff` = Affidavit/AOPC

**Examples:**
- `2024-03-15_Doc45_MotSuppress_Def_Jones.pdf`
- `2024-03-22_Doc52_OppSuppress_USA_Jones.pdf`
- `2024-04-10_Doc67_OrdSuppress_Ct_Jones.pdf`

---

*Classification: PRIVILEGED & CONFIDENTIAL — ATTORNEY WORK PRODUCT*
*Case: US v. Redmond, EDPA 24-376*

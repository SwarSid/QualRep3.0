# CGP Insight Engine

Zero-cost, no-API qual research tool for CGP (Comprehensive Genomic Profiling) vendor studies. Upload your HCP response Excel and get instant, traceable insights — every answer backed by respondent ID and verbatim evidence.

---

## Deploy to Streamlit Cloud (free, ~5 min)

1. Create a new GitHub repo
2. Upload **`app.py`**, **`requirements.txt`**, and **`README.md`**
3. Go to [share.streamlit.io](https://share.streamlit.io) → New app
4. Select your repo → `app.py` → Deploy
5. Share the URL — no login required, no cost per user

---

## Excel format expected

| Column | How detected | Required? |
|---|---|---|
| Verbatim response | Longest average string column | ✅ Required |
| Practice Setting | Column header contains "setting" | Optional |
| Specialty | Column header contains "specialty" | Optional |
| CGP Lab Vendor | Column header contains "cgp", "vendor", or "lab" | Optional |

**Invalid responses are automatically excluded** — responses under 15 characters, single-word answers, number-only responses, and filler responses (e.g. "Same", "OK", "Six, seven") are filtered out before analysis.

---

## Vendor colour coding

| Vendor | Colour |
|---|---|
| Foundation Medicine (FMI) | ⬤ Charcoal `#4A4A4A` |
| Guardant Health | 🟣 Purple `#9B59B6` |
| Caris Life Sciences | 🟠 Coral `#E8745A` |
| Tempus | 🟢 Mint `#52C4A0` |

Colours are applied consistently across all charts, quote cards, badges, and comparison tables.

---

## 15 CGP Themes

| Theme | Key signals |
|---|---|
| Testing Modality | NGS, liquid biopsy, tissue testing, whole genome, ctDNA |
| Physician Support Services | MSL, rep support, medical affairs, account manager |
| Test Accuracy | Accuracy, sensitivity, specificity, reliable, validated |
| Clinical Trial Matching | Trial matching, actionable variant, basket trial, biomarker match |
| Ease of Ordering | Ordering process, requisition, easy to order, streamlined |
| Assay Panel Size | Panel size, gene panel, number of genes, comprehensive panel |
| Clinical Utility | Actionable, clinically relevant, changes management, guides treatment |
| Turnaround Time | TAT, time to result, quick result, how long, within days |
| Report Clarity | Report format, easy to read, easy to interpret, clear report |
| Patient Financial Support | Out of pocket, copay, patient assistance, insurance, coverage |
| Aggregated Patient Data | Real world data, database, cohort, RWD, outcomes data |
| Other Portfolio Tests | Suite of tests, liquid, tissue, multi-test, test menu |
| Reflex Testing | Reflex, reflexing, automatic reflex, cascade testing |
| Research Support | Research collaboration, publications, peer reviewed, investigator |
| EMR/EHR Integration | EMR, EHR, Epic, Cerner, integrated, electronic ordering |

---

## Four output components

### 📊 Dashboard (sidebar tab 1)
Click any theme → instant full dashboard:
- 5-point executive summary (from data counts only)
- Segment breakdown by Setting / Specialty / CGP Vendor
- Co-theme chart (what travels with this theme)
- Driver complexity (standalone vs bundled)
- Full verbatim quotes, colour-coded by vendor
- Downloadable CSVs (full responses + segment summary)

### ❓ Questions (sidebar tab 2)
80+ pre-built CGP-specific questions across 8 categories:
- Frequency, Comparison, Drivers, Co-occurrence
- Theme Clustering, Driver Complexity, Full Responses, Vendor-Specific

Or type any question freely in the search box.

### 📊 Compare (sidebar tab 3)
Full side-by-side comparison table:
- All 15 themes × all vendors (or settings or specialties)
- % mentioning each theme per segment
- Highest value highlighted per row
- Downloadable CSV

### 🎭 Sentiment (sidebar tab 4)
**Overall view** — all 15 themes ranked by NSS in one table, broken down by Setting / Specialty / CGP Vendor.

**Per theme** — Net Sentiment Score with:
- Formula shown transparently
- Segment breakdown with calculation workings
- ⚠ Auto-flags small samples (< 5 HCPs or < 10 sentences)
- Excel download: all sentences + HCP-level NSS + segment breakdown

No quotes shown on screen — all evidence in downloadable Excel.

---

## Sentiment Methodology

**NSS Formula:** (Positive − Negative) ÷ (Pos + Neg + Neutral) × 100

| Score | Interpretation |
|---|---|
| > +10 | Net positive sentiment |
| −10 to +10 | Balanced |
| < −10 | Net negative sentiment |

**Classification:** Each response split into sentences → sentences referencing the theme identified → classified using a CGP-tuned lexicon with negation detection (e.g. "haven't had any issues" → Positive).

---

## Segment filters

All components filterable by:
- **Practice Setting** — Academic · Community · Private Practice · Teaching Hospital · VA/Military
- **Specialty** — Medical Oncology · Hematology/Oncology
- **CGP Vendor** — FMI · Tempus · Caris Life Sciences · Guardant Health

---

## Cost

- GitHub: Free
- Streamlit Cloud: Free tier — unlimited visitors, no per-query charge
- The app: Zero API calls, zero cost per use
- Safe to share with any client — no data stored between sessions

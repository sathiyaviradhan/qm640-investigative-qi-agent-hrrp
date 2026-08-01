# QM640 Capstone — Investigative Agentic QI Framework for CMS HRRP

**Student:** Sathiyaviradhan Janarthanan  
**Course:** Walsh College — QM640 Data Analytics Capstone  
**Mentor:** Sridhar S  
**Repository:** https://github.com/sathiyaviradhan/qm640-investigative-qi-agent-hrrp

## Project title

An Investigative Agentic AI Framework for CMS Hospital Excess Readmission Risk: Parallel Machine Learning, Fairness Monitoring, and Tool-Grounded Quality Improvement Case Dossiers under Human-in-the-Loop Review

## What this repo contains

| Path | Description |
|------|-------------|
| `DATASET/analytic_core/` | CMS HRRP + Hospital General Information extracts (FY2024–FY2026) |
| `QM640_Interim_Report_Analysis.ipynb` | Fully explained, executed Jupyter notebook (RQ1–RQ4) |
| `run_interim_analysis.py` | End-to-end RQ1–RQ4 analysis pipeline (script form) |
| `analysis_outputs/` | Metrics, figures, cleaned panel, sample QI dossiers |
| `_build_interim_report.py` | Regenerates the Interim Report DOCX from metrics/figures |
| `QM640_Interim_Report.docx` | Current Interim Report deliverable |
| `QM640_Synopsis_First_Submission.docx` | Approved synopsis / first submission |

## Research questions (parallel)

1. **RQ1** — Associations with excess readmission risk (ERR > 1.0)
2. **RQ2** — Out-of-time ML discrimination vs logistic baseline
3. **RQ3** — Fairness / AUROC monitoring across FY releases
4. **RQ4** — Tool-grounded Investigative QI Case Agent vs no-tool LLM vs static dashboard

## Quick start

```bash
python -m pip install -r requirements.txt
python run_interim_analysis.py
```

Outputs write to `analysis_outputs/` (`metrics.json`, `figures/`, `processed/`).

Optional report rebuild:

```bash
python _build_interim_report.py
```

## Data note

Public CMS Provider Data Catalog hospital files (not Kaggle). Core analytic files only — see `DATASET/analytic_core/dataset_metadata.json`.

- CMS Hospitals topic: https://data.cms.gov/provider-data/topics/hospitals
- HRRP program: https://www.cms.gov/medicare/payment/prospective-payment-systems/acute-inpatient-pps/hospital-readmissions-reduction-program-hrrp

## Policy boundary (RQ4)

The Investigative Agentic QI Case Agent produces **advisory-only** dossiers. It does **not** auto-approve CMS penalties, clinical orders, payment adjustments, or model deployment. Human Accept / Edit / Reject is mandatory.

## Interim headline results (executed)

- Eligible pooled N = 35,724 hospital–condition rows (non-missing ERR)
- RQ1: Ha supported (multiple significant adjusted associations)
- RQ2: Gradient boosting OOT AUROC ≈ 0.673 vs logistic ≈ 0.609 (Δ > 0.02)
- RQ3: AUROC/fairness gap largely stable across FY (persistent ownership ΔFNR; Ha for drift not supported)
- RQ4: Agent outperforms no-tool LLM on faithfulness / evidence completeness / usefulness proxy (n = 80)

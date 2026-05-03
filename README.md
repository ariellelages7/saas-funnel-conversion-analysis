# SaaS Conversion Funnel Analysis - Revenue Leakage & Prioritized Recommendations

> Identifying where users drop off, quantifying the financial impact of each bottleneck, and delivering prioritized recommendations.  
> Funnel analysis · Benchmark comparison · Revenue simulation · Product analytics

---

## Overview

This project analyzes a **5-stage SaaS conversion funnel** (17,175 user records) to answer the questions that product and growth teams deal with daily:

- Where exactly are users dropping off — and how severe is each gap?
- How does our funnel compare to SaaS industry benchmarks?
- What is the **revenue impact** of each bottleneck in dollar terms?
- Which stage should be fixed first to maximize ROI?

The project includes an **interactive revenue simulator** - adjust conversion rates per stage and see the monthly revenue impact in real time.

---

## Key Findings

| Stage | Our Rate | Benchmark | Gap | Annual Revenue at Stake |
|-------|----------|-----------|-----|------------------------|
| Homepage → Product | 100% | 45% | +55pp ✓ | — |
| Product → Cart | 50.3% | 35% | +15pp ✓ | $76,440 |
| Cart → Checkout | 29.9% | 65% | −35pp ✗ | $86,436 |
| Checkout → Purchase | 8.0% | 75% | −67pp ✗ | **$151,116** |

**Overall conversion: 0.14%** vs SaaS median of ~3% — a 20x gap driven almost entirely by the bottom half of the funnel.

---

## Prioritized Recommendations

**#1 — Fix Checkout (92% drop-off → $151K/year opportunity)**  
Implement guest checkout, show total cost upfront, reduce form fields. This is the single highest-leverage fix.

**#2 — Reduce Cart Abandonment (70% drop-off → $86K/year)**  
Add trust signals, clear returns policy, and a save-for-later option. Consider an exit-intent cart recovery flow.

**#3 — Optimize Product Page CTA (50% drop-off → $76K/year)**  
Improve call-to-action clarity, add social proof, and A/B test pricing presentation.

> If all three stages reach benchmark: ~300 buyers/month → **$14,700/month** vs current $686/month.

---

## Dataset

| Field | Detail |
|-------|--------|
| Source | [Kaggle — User Funnels Dataset](https://www.kaggle.com/datasets/amirmotefaker/user-funnels-dataset) |
| Rows | 17,175 records |
| Fields | user_id, stage, conversion |
| Stages | Homepage · Product Page · Cart · Checkout · Purchase |

---

## Methodology

### Funnel Metrics
For each stage: total users, converted users, conversion rate, drop-off rate, and cumulative conversion relative to the top of funnel.

### Benchmark Comparison
Rates compared against SaaS industry averages from Baymard Institute and HubSpot Conversion Report 2023. Color-coded by health: green = above benchmark, red = critical.

### Revenue Leakage Simulation
For each stage, I model the revenue impact of a +10pp improvement while holding all other stages constant. Assumptions: $49/month avg ticket, 10,000 monthly visitors.

**Formula:**  
`new_buyers = visitors × ∏(conv_rate_i)` where stage i uses the improved rate and all others remain at baseline.

---

## Project Structure

```
saas-funnel-conversion-analysis/
│
├── funnel_analysis.ipynb        # Full analysis — metrics, charts, benchmarks, simulation
├── user_data.csv                # Source dataset
├── funnel_executive_report.html # Standalone interactive report (open in browser)
└── README.md
```

---

## How to Run

```bash
git clone https://github.com/ariellelages7/saas-funnel-conversion-analysis.git
cd saas-funnel-conversion-analysis

pip install pandas numpy matplotlib

jupyter notebook funnel_analysis.ipynb
```

Open `funnel_executive_report.html` directly in any browser — no server needed.

---

## Tools & Stack

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-2.0-150458?style=flat&logo=pandas&logoColor=white)
![matplotlib](https://img.shields.io/badge/matplotlib-3.7-11557c?style=flat)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat&logo=jupyter&logoColor=white)

---

## About

Part of my data analytics portfolio. I specialize in helping SaaS and product teams turn raw data into clear insights, dashboards, and business recommendations.

**Areas:** Product analytics · Funnel optimization · Customer segmentation · KPI tracking · Dashboard reporting

[LinkedIn](https://linkedin.com/in/arielle-lages) · [Upwork](https://upwork.com/freelancers/~01d57a3a01eb584140)

# Olist Marketing Funnel and E-Commerce Analysis

## Project status

**In progress:** the Python analysis and validation are complete. Dashboard-ready exports, Looker Studio, and the final public portfolio links are next.

## Purpose

This project joins the Olist marketing funnel with Brazilian e-commerce activity to study:

- lead-to-deal conversion by acquisition channel and month;
- whether closed deals connect to sellers with recorded commerce activity;
- delivery performance and seller-to-customer state corridors.

The project uses Python, pandas, Matplotlib, Jupyter, and GitHub Codespaces. Raw Kaggle files stay outside Git because they are large source data; the notebook documents how they are loaded and validated.

## Why the join design matters

Marketing data is one row per `mql_id`, while commerce data contains many order items per seller. A direct join expanded 8,000 leads to 12,664 rows and would have inflated funnel KPIs. The notebook first aggregates commerce activity to seller level, then joins through `seller_id`, preserving one row per lead.

## Verified results so far

- 8,000 marketing-qualified leads
- 842 closed deals
- 10.53% lead-to-deal conversion
- 380 commerce-linked deals
- 45.13% commerce-link rate
- 97,811 eligible seller-order records across 412 state corridors
- all documented join, reconciliation, and chart-quality checks passed

## Repository guide

- `notebooks/joining-marketing-funnel-with-brazilian-e-commerce.ipynb` — full tutorial, code, checks, findings, and Python charts
- `input/` — local Kaggle source data, intentionally excluded from Git
- `data/` — sample data supplied by the original Codespaces template

## What I learned

The strongest lesson was that a correct dashboard begins with correct data grain. Counts and rates can look reasonable even when a many-to-many join has duplicated the underlying business entity. I therefore documented every KPI denominator, reconciled grouped totals to the source, kept unknown attribution visible, and separated descriptive findings from causal claims.

## Next milestones

1. Export small, verified CSV tables for dashboard use.
2. Build the interactive Looker Studio report.
3. Add dashboard screenshots and final links.
4. Complete the portfolio write-up and resume project link.

## Data sources

- Brazilian E-Commerce Public Dataset by Olist
- Marketing Funnel by Olist

Source datasets are available on Kaggle and are not redistributed in this repository.

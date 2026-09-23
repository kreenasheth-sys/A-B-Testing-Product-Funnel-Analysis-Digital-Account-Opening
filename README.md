# A/B Testing & Product Funnel Analysis

### Evaluating a Redesigned Digital Account-Opening Journey

## Overview

How do we know whether a product change actually improves user behaviour?

This project evaluates a simulated A/B test for a digital account-opening journey. I compared the existing experience (Control) with a redesigned experience (Treatment) to understand whether the redesign improved account-opening conversion.

The analysis covers the complete experimentation workflow — from experiment design and data validation to funnel analysis, statistical significance and business interpretation.

> **Note:** This project uses synthetic data created for portfolio and interview purposes. It does not represent actual Vanguard or client data.

---

## Business Question

A financial services company has redesigned its digital account-opening journey.

**Does the redesigned journey increase the percentage of users who ultimately open an account?**

- **Control (A):** Existing account-opening journey
- **Treatment (B):** Redesigned account-opening journey
- **Primary KPI:** Account-opening conversion rate

The user journey was analysed across:

**Landing -> Application -> KYC -> Funding -> Account Opened**

---

## Experiment Approach

### Hypothesis

**H₀:** There is no difference in account-opening conversion between the two experiences.

**H₁:** The redesigned journey increases account-opening conversion.

A one-sided hypothesis was used because the business question specifically focused on whether the redesign would improve conversion.

### Analysis

- Validated experiment allocation and data quality
- Measured conversion across the funnel
- Compared Control vs Treatment conversion
- Calculated absolute and relative lift
- Conducted a two-proportion Z-test
- Calculated a 95% confidence interval
- Interpreted statistical and business significance

---

## Key Findings

| Metric | Control (A) | Treatment (B) |
|---|---:|---:|
| Users | 15,052 | 14,948 |
| Accounts opened | 3,704 | 4,645 |
| Conversion rate | 24.61% | 31.07% |

### Conversion Impact

- **Absolute lift:** +6.46 percentage points
- **Relative lift:** +26.25%
- **Z-statistic:** 12.49
- **95% CI for conversion difference:** 5.45 to 7.48 percentage points
- **p-value:** < 0.001

The Treatment group showed a higher account-opening conversion rate than the Control group. The confidence interval for the difference remained above zero, and the statistical test provided strong evidence against the null hypothesis.

### Business Interpretation

The observed improvement is large enough to be relevant from a product perspective, not just statistically detectable. The next step in a real world experiment would be to validate the result across important customer segments and monitor guardrail metrics before a full rollout.

---

## Funnel Analysis

The analysis also compared user progression through the account-opening journey:

**Landing → Application Start → KYC → Funding → Account Opened**

This helps move beyond the final conversion metric and identify **where users are dropping out of the journey**.

---

## Tools & Skills

**SQL** — Data validation, funnel analysis, aggregation, experimentation and segmentation

**Python** — Data analysis and statistical exploration

**DuckDB** — SQL analysis environment

**Pandas** — Data manipulation and exploration

### Concepts

`A/B Testing` `Hypothesis Testing` `Funnel Analysis` `Statistical Significance` `Confidence Intervals` `Product Analytics` `KPI Analysis`

---

## Dataset

### `experiment_users.csv`

One row per experiment user containing experiment assignment, user attributes and funnel outcomes.

### `funnel_events.csv`

Event-level data capturing user activity throughout the account-opening journey.

### `data_dictionary.csv`

Definitions of the fields used across the datasets.

---

## Project Structure

```text
ab-testing-product-analysis/
│
├── data/
│   ├── experiment_users.csv
│   ├── funnel_events.csv
│   └── data_dictionary.csv
│
├── sql/
│   └── ab_test_analysis.sql
│
├── notebooks/
│   └── analysis.ipynb
│
└── README.md

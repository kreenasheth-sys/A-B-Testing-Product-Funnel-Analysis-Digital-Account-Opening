# A/B Testing & Product Funnel Analysis — Digital Account Opening

## Overview

How do we know whether a product change actually improves user behavior?

This project explores that question through a simulated A/B test of a digital account-opening journey. I compare an existing experience (Control) with a redesigned experience (Treatment) to determine whether the redesign improves account-opening conversion.

The analysis follows an end-to-end experimentation process, from defining the hypothesis and experiment groups, validating the data, and analyzing the conversion funnel to measuring statistical significance, evaluating the size of the impact, and translating the results into a business decision.

> **Note:** This project uses synthetic data created for portfolio and interview purposes. It does not represent actual Vanguard or client data.

---

## Business Question

A financial services company has redesigned its digital account-opening journey.

The key question is:

> **Does the redesigned journey increase the percentage of users who ultimately open an account?**

To answer this, users are randomly assigned to one of two experiences:

- **Control (A):** Existing account-opening journey
- **Treatment (B):** Redesigned account-opening journey

The primary KPI is **account-opening conversion rate**.

---

## 1. Experiment Hypothesis

The experiment begins with a hypothesis rather than the data.

### Null Hypothesis (H₀)

There is no difference in account-opening conversion between the existing and redesigned journeys.

**H₀: pB = pA**

### Alternative Hypothesis (H₁)

The redesigned journey increases account-opening conversion.

**H₁: pB > pA**

Because the business question is specifically whether the redesign **improves** conversion, the experiment uses a directional (one-sided) hypothesis.

Defining the hypothesis before analyzing the results helps ensure that the statistical test is driven by the business question rather than by the outcome observed in the data.

---

## 2. Experiment Design

| Group | Experience | Purpose |
|---|---|---|
| Control (A) | Existing journey | Baseline |
| Treatment (B) | Redesigned journey | Test variation |

### Primary Metric

**Account-opening conversion**

`Users who opened an account / Total users in the experiment group`

The experiment also tracks the journey leading to the final outcome:

**Landing → Application Started → KYC Completed → Funded → Account Opened**

---

## 3. Analysis Approach

The analysis follows this sequence:

**Hypothesis & Experiment Design**  
↓  
**Data Validation**  
↓  
**Funnel Analysis**  
↓  
**Primary KPI & Conversion Lift**  
↓  
**Statistical Significance**  
↓  
**Confidence Interval & Power**  
↓  
**Practical Significance**  
↓  
**Segment & Guardrail Analysis**  
↓  
**Business Impact**

---

## 4. What I Analyze

### Experiment & Data Quality

- Validate Control/Treatment allocation
- Check duplicate users
- Check missing values
- Validate the experiment outcome
- Confirm assumptions required for the statistical test

### Funnel Analysis

- Measure conversion at each stage
- Identify major drop-off points
- Compare funnel performance across variants

### A/B Test

- Calculate Control and Treatment conversion
- Calculate absolute lift
- Calculate relative lift
- Conduct a Z-test for proportions
- Interpret the Z-statistic and p-value
- Assess statistical significance

### Beyond Statistical Significance

- Calculate confidence intervals
- Evaluate statistical power
- Consider Type I and Type II error
- Assess practical significance
- Compare potential business impact against implementation cost
- Analyze performance across user segments
- Monitor guardrail metrics

---

## Dataset

The project uses two synthetic datasets.

### `experiment_users`

One row per experiment user containing:

- Experiment assignment
- Acquisition channel
- Device
- Age band
- Prior investor status
- Funnel outcomes
- Account-opening outcome
- Initial assets

### `funnel_events`

Event-level data capturing user activity throughout the account-opening journey.

---

## Tools & Skills

**SQL**  
Data validation, aggregation, funnel analysis, segmentation and experiment analysis

**Python**  
Statistical analysis and supporting data exploration

**DuckDB**  
SQL analysis environment

**Pandas**  
Data manipulation and analysis

### Concepts

`A/B Testing` `Hypothesis Testing` `Product Analytics` `Funnel Analysis` `Statistical Significance` `Confidence Intervals` `Statistical Power` `Segmentation` `Business Analysis`

---

## Key Findings

*Results will be added after completing the analysis.*

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

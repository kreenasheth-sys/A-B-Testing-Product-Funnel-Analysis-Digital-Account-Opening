# A/B Testing and Product Funnel Analysis - Digital Account-Opening
This project analyzes a simulated A/B test for a digital account-opening journey.  The objective is to determine whether a redesigned account-opening journey (Treatment B) improves account-opening conversion compared with the existing journey (Control A).


### Overview

How do we know whether a product change actually improves user behavior?

This project explores that question through a simulated A/B test of a digital account-opening journey. I compare an existing experience (Control) with a redesigned experience (Treatment) to determine whether the redesign improves account-opening conversion.

The analysis goes beyond simply comparing two conversion rates. It follows an end-to-end experimentation process — starting with defining the hypothesis and experiment groups, validating the data, analyzing the conversion funnel, testing statistical significance, and finally assessing whether the observed improvement is meaningful from a business perspective.

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

This distinction matters because an A/B test should be designed around the business question being investigated, rather than interpreting the result after looking at the data.

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
- Compare impact against potential implementation cost
- Analyze performance across user segments
- Monitor guardrail metrics

---

## 5. From Statistical Result to Business Decision

A statistically significant result does not automatically mean a product change should be implemented.

The final analysis therefore asks two separate questions:

**Is the observed difference statistically significant?**

and

**Is the size of the improvement meaningful enough to matter to the business?**

For example, a very small improvement may be statistically significant with a sufficiently large sample, but may not justify the engineering effort or operational cost required to implement the change.

The goal is to connect statistical evidence with the underlying business decision.

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

*This section will be updated after completing the analysis.*

The final results will summarize:

- Control vs. Treatment conversion
- Absolute and relative lift
- Statistical significance
- Confidence interval
- Statistical power
- Key funnel drop-offs
- Segment-level differences
- Business implications

---

## Project Structure

```text
ab-testing-product-analysis/
│
├── data/
│   ├── vanguard_ab_test_users.csv
│   ├── vanguard_ab_test_events.csv
│   └── data_dictionary.csv
│
├── sql/
│   └── ab_test_analysis.sql
│
├── notebooks/
│   └── analysis.ipynb
│
└── README.md

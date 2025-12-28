> End-to-end customer segmentation project using RFM analysis on real-world online retail data, with business-focused insights and machine learning extensions.

# Customer Segmentation using RFM Analysis

## Overview
This project performs **customer segmentation using RFM (Recency, Frequency, Monetary) analysis** on real-world online retail transaction data.  
The objective is to identify high-value, loyal, at-risk, and dormant customers and derive **actionable business insights**.

The analysis is implemented end-to-end with a strong focus on **interpretability, business relevance, and practical deployment**.

---

## Objectives
- Identify high-value and at-risk customers
- Enable data-driven marketing and retention strategies
- Analyze revenue concentration using the Pareto principle
- Compare rule-based segmentation with machine learning (KMeans clustering)

---

## Dataset
- Online retail transactional dataset
- Key fields used:
  - `CustomerID`
  - `InvoiceDate`
  - `InvoiceNo`
  - `Quantity`
  - `UnitPrice`

Only valid customer transactions were retained for analysis.

---

## Data Preparation
- Removed transactions with missing `CustomerID`
- Excluded cancelled invoices
- Converted date columns to datetime format
- Created `TotalPrice = Quantity × UnitPrice`

---

## RFM Feature Engineering
Each customer is represented using:
- **Recency**: Days since last purchase
- **Frequency**: Total number of transactions
- **Monetary**: Total customer spend

These metrics summarize customer engagement and value in a compact form.

---

## RFM Scoring
- Quartile-based scoring (1–4) applied independently to R, F, and M
- Higher scores indicate more desirable customer behavior
- Final RFM score created by combining individual scores

This approach is robust to outliers and easy to interpret.

---

## Customer Segmentation
Customers were assigned to business-relevant segments using rule-based logic:

- **Champions** – High R, F, and M
- **Loyal Customers** – Frequent and recent buyers
- **Potential Loyalists** – Recent but less frequent buyers
- **At Risk** – Previously valuable but disengaging
- **Hibernating** – Low engagement across all dimensions

---

## Segment Distribution Analysis
Most customers fall into low-engagement segments, while a smaller proportion contributes disproportionately to revenue.  
This highlights the importance of:
- Retention strategies for high-value customers
- Reactivation campaigns for dormant segments

---

## Revenue Concentration (Pareto Analysis)
Approximately **26% of customers contribute to 80% of total revenue**, confirming a strong Pareto effect.

**Business implications:**
- Targeted marketing yields higher ROI than broad campaigns
- Protecting high-value customers is critical for sustainability

---

## Machine Learning Extension (KMeans Clustering)
- Standardized RFM features using `StandardScaler`
- Applied KMeans clustering to explore natural customer groupings
- Compared clustering results with rule-based RFM segments

---

## RFM vs Clustering Comparison
Clustering results broadly align with RFM-based segments, validating the rule-based approach.

**RFM remains preferable due to:**
- Greater interpretability
- Easier business deployment
- Clear mapping to marketing actions

---

## Customer Action Mapping

Each customer segment is paired with a recommended business action and an
ROI intuition, translating analytical insights into deployable strategies.

This makes the segmentation directly usable for marketing, retention,
and revenue optimization teams.

---

## Methodology
RFM segmentation was chosen for its interpretability and robustness.  
Quartile-based scoring ensures consistent customer comparison and reduces sensitivity to extreme values.

---

## Limitations
- Assumes equal importance of R, F, and M
- Does not model seasonality
- No explicit time-decay mechanism

---

## Future Work
- Weighted RFM optimization
- Time-decayed RFM
- Survival analysis for churn prediction
- Predictive Customer Lifetime Value (CLV) modeling

---

## Output
The final customer segmentation is exported as:

---

## rfm_customer_segmentation_final.csv
This framework can be extended into a production-ready customer analytics pipeline.